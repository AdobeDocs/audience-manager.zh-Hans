---
description: Audience Manager中的访客身份验证状态决定了新特征信息是否写入访客的身份验证配置文件，或将新特征信息写入从中收集数据的设备配置文件中。Audience Manager以相同方式处理访客ID身份验证状态UNKNOWN和LOGED_ OUT。
keywords: dpm.demdex.net
seo-description: Audience Manager中的访客身份验证状态决定了新特征信息是否写入访客的身份验证配置文件，或将新特征信息写入从中收集数据的设备配置文件中。Audience Manager以相同方式处理访客ID身份验证状态UNKNOWN和LOGED_ OUT。
seo-title: Audience Manager中的访客身份验证状态
solution: Audience Manager
title: Audience Manager中的访客身份验证状态
uuid: d748c0c 3-5833-fb9-ab3 e-793f5 f252 e47
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Visitor Authentication States in Audience Manager{#visitor-authentication-states-in-audience-manager}

Audience Manager中的访客身份验证状态决定了新特征信息是否写入访客的身份验证配置文件，或将新特征信息写入从中收集数据的设备配置文件中。Audience Manager以相同方式处理访客ID身份验证状态UNKNOWN和LOGED_ OUT。

Beginning with [!DNL Experience Cloud] ID service v1.5+, the `setCustomerID` method includes the optional `AuthState` object. `AuthState` 根据访客 [身份验证状态识别访客](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)。[!DNL Audience Manager] 根据调用中传递的身份验证状态和用于分段的 [配置文件合并规则](../features/profile-merge-rules/merge-rules-dashboard.md) ，以不同方式处理已实现的特征。

## Authentication Status: UNKNOWN {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>请求值 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>从已验证的配置文件读取</b> 信息 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>为已验证的配置文件写入</b> 新特性 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>是，如果身份验证选项合并规则=“上一个身份验证配置文件”。 </p> </td> 
   <td colname="col3" morerows="1"> <p>否，特征数据会添加到设备配置文件中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>否，如果身份验证选项合并规则=“当前身份验证配置文件”或“无身份验证配置文件”。 </p> </td> 
  </tr> 
 </tbody> 
</table>

示例调用(与身份验证状态对应的请求值会高亮显示)：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentication Status: AUTHENTICATED {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>请求值 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>从已验证的配置文件读取</b> 信息 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>为已验证的配置文件写入</b> 新特性 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>是，如果身份验证选项合并规则=“当前身份验证配置文件”或“上次验证配置文件”。 </p> </td> 
   <td colname="col3" morerows="1"> <p>是，特征数据会添加到经过身份验证的配置文件中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>否，如果身份验证选项合并规则=“无身份验证配置文件”。 </p> </td> 
  </tr> 
 </tbody> 
</table>

示例调用(与身份验证状态对应的请求值会高亮显示)：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentication Status: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>请求值 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>从已验证的配置文件读取</b> 信息 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>为已验证的配置文件写入</b> 新特性 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code>2</code> </p> </td> 
   <td colname="col2"> 是，如果身份验证选项合并规则=“上一个身份验证配置文件” </td> 
   <td colname="col3" morerows="1"> <p>否，特征数据会写入设备配置文件中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> 否，如果身份验证选项合并规则=“当前身份验证配置文件”或“无身份验证配置文件” </td> 
  </tr> 
 </tbody> 
</table>

示例调用(与身份验证状态对应的请求值会高亮显示)：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] 在所有三种情况下，在 [CID和UUID](../reference/ids-in-aam.md) 之间执行ID同步。

>[!MORE_ LIKE_ This]
>
>* [客户 ID 和身份验证状态](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)

