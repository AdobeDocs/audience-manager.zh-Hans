---
description: 访客管理器中的受众身份验证状态确定新特征信息是写入访客已验证的用户档案还是写入设备用户档案（从中收集数据）。 受众管理器以相同方式处理访客ID身份验证状态UNKNOWN和LOGGED_OUT(在事件调用中)。
keywords: dpm.demdex.net
seo-description: 访客管理器中的受众身份验证状态确定新特征信息是写入访客已验证的用户档案还是写入设备用户档案（从中收集数据）。 受众管理器以相同方式处理访客ID身份验证状态UNKNOWN和LOGGED_OUT(在事件调用中)。
seo-title: 访客受众管理器中的身份验证状态
solution: Audience Manager
title: 访客受众管理器中的身份验证状态
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# 访客受众管理器中的身份验证状态{#visitor-authentication-states-in-audience-manager}

访客管理器中的受众身份验证状态确定新特征信息是写入访客已验证的用户档案还是写入设备用户档案（从中收集数据）。 受众管理器以相同方式处理访客ID身份验证状态UNKNOWN和LOGGED_OUT(在事件调用中)。

从ID [!DNL Experience Cloud] 服务v1.5+开始，该方 `setCustomerID` 法包括可选 `AuthState` 对象。 `AuthState` 根据访客的身份验 [证状态](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)。 [!DNL Audience Manager] 根据调用中传递的身份验证状态和用于分段的用户档案合并规 [则，以不同方式](../features/profile-merge-rules/merge-rules-dashboard.md) 处理已实现的特征。

## 身份验证状态： 未知 {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>请求值 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>从已验证</b> 的用户档案读取信息 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>将新特征</b> 写入已验证的用户档案 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>是，如果已验证选项合并规则=“上次已验证用户档案”。 </p> </td> 
   <td colname="col3" morerows="1"> <p>否，特征数据将添加到设备用户档案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>否，如果已验证选项合并规则=“当前已验证用户档案”或“无已验证用户档案”。 </p> </td> 
  </tr> 
 </tbody> 
</table>

示例调用（与身份验证状态对应的请求值会突出显示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## 身份验证状态： 已验证 {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>请求值 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>从已验证</b> 的用户档案读取信息 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>将新特征</b> 写入已验证的用户档案 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>是，如果已验证选项合并规则=“当前已验证用户档案”或“上次已验证用户档案”。 </p> </td> 
   <td colname="col3" morerows="1"> <p>是，特征数据将添加到已验证的用户档案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>否，如果已验证选项合并规则=“无已验证用户档案”。 </p> </td> 
  </tr> 
 </tbody> 
</table>

示例调用（与身份验证状态对应的请求值会突出显示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## 身份验证状态： LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>请求值 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>从已验证</b> 的用户档案读取信息 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>将新特征</b> 写入已验证的用户档案 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> 是，如果已验证选项合并规则=“上次已验证用户档案” </td> 
   <td colname="col3" morerows="1"> <p>否，特征数据将写入设备用户档案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> 否，如果已验证选项合并规则=“当前已验证用户档案”或“无已验证用户档案” </td> 
  </tr> 
 </tbody> 
</table>

示例调用（与身份验证状态对应的请求值会突出显示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] 在所有三种情况下 [在CID和UUID](../reference/ids-in-aam.md) 之间执行ID同步。

>[!MORELIKETHIS]
>
>* [客户 ID 和身份验证状态](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

