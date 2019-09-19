---
description: Audience manager中的访客身份验证状态确定新特征信息是写入访客的已验证配置文件，还是写入设备配置文件（从中收集数据）。 Audience manager以相同方式处理活动调用中的访客ID身份验证状态UNKNOWN和LOGGED_OUT。
keywords: dpm.demdex.net
seo-description: Audience manager中的访客身份验证状态确定新特征信息是写入访客的已验证配置文件，还是写入设备配置文件（从中收集数据）。 Audience manager以相同方式处理活动调用中的访客ID身份验证状态UNKNOWN和LOGGED_OUT。
seo-title: Audience manager中的访客身份验证状态
solution: Audience Manager
title: Audience manager中的访客身份验证状态
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience manager中的访客身份验证状态{#visitor-authentication-states-in-audience-manager}

Audience manager中的访客身份验证状态确定新特征信息是写入访客的已验证配置文件，还是写入设备配置文件（从中收集数据）。 Audience manager以相同方式处理活动调用中的访客ID身份验证状态UNKNOWN和LOGGED_OUT。

从 [!DNL Experience Cloud] ID服务v1.5+开始，该方法 `setCustomerID` 包括可选对 `AuthState` 象。 `AuthState` 根据访客的身份验证状 [态识别访客](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)。 [!DNL Audience Manager] 根据调用中传递的身份验证状态和用于分段的配置文件合并规则 [](../features/profile-merge-rules/merge-rules-dashboard.md) ，以不同方式处理实现的特征。

## 身份验证状态：未知 {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>请求值 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>从已验证</b> 的配置文件中读取信息 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>将新特征</b> -写入已验证的配置文件 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>是，如果“已验证”选项合并规则=“上次已验证的配置文件”。 </p> </td> 
   <td colname="col3" morerows="1"> <p>否，特征数据将添加到设备配置文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>否，如果“已验证”选项合并规则=“当前已验证配置文件”或“无已验证配置文件”。 </p> </td> 
  </tr> 
 </tbody> 
</table>

示例调用（与身份验证状态对应的请求值会高亮显示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## 身份验证状态：已验证 {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>请求值 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>从已验证</b> 的配置文件中读取信息 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>将新特征</b> -写入已验证的配置文件 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>是，如果“已验证”选项合并规则=“当前已验证配置文件”或“上次已验证配置文件”。 </p> </td> 
   <td colname="col3" morerows="1"> <p>是，特征数据将添加到已验证的配置文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>否，如果“已验证”选项合并规则=“无已验证配置文件”。 </p> </td> 
  </tr> 
 </tbody> 
</table>

示例调用（与身份验证状态对应的请求值会高亮显示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## 身份验证状态：LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>请求值 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>从已验证</b> 的配置文件中读取信息 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>将新特征</b> -写入已验证的配置文件 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code>2</code> </p> </td> 
   <td colname="col2"> 是，如果已验证选项合并规则=“上次已验证配置文件” </td> 
   <td colname="col3" morerows="1"> <p>否，特征数据将写入设备配置文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> 否，如果“已验证”选项合并规则=“当前已验证配置文件”或“无已验证配置文件” </td> 
  </tr> 
 </tbody> 
</table>

示例调用（与身份验证状态对应的请求值会高亮显示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] 在所有三种情况下 [执行CID和UUID](../reference/ids-in-aam.md) 之间的ID同步。

>[!MORE_LIKE_THIS]
>
>* [客户 ID 和身份验证状态](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)

