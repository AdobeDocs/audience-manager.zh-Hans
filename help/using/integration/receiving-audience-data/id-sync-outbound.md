---
description: 描述在初始HTTP调用中使用的语法和参数，以同步Audience Manager与第三方数据提供商之间的用户ID。在尝试第一个ID同步之前，请与您的Adobe Audience Manager顾问联系。
seo-description: 描述在初始HTTP调用中使用的语法和参数，以同步Audience Manager与第三方数据提供商之间的用户ID。在尝试第一个ID同步之前，请与您的Adobe Audience Manager顾问联系。
seo-title: 用于出站数据传输的ID同步
solution: Audience Manager
title: 用于出站数据传输的ID同步
uuid: f3849be8-1094-47db-9296-7482f020af18
translation-type: tm+mt
source-git-commit: e206d3a3cba259dc215f2f4190c9b4e03264f080

---


# ID Synchronization for Outbound Data Transfers{#id-synchronization-for-outbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between Audience Manager and a third-party data provider. 在尝试第一个ID同步之前，请与您的Adobe Audience Manager顾问联系。

<!-- c_id_sync_out.xml -->

## ID同步的目的

ID同步是出站、异步数据传输过程中的第一步。In this step, [!DNL Audience Manager] and the vendor compare and match IDs for their respective site visitors. For example, an [!DNL Audience Manager] customer may know a user by ID 123. 但是，您的数据合作伙伴可以识别此用户ID为456。The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and the third-party data provider should have corresponding IDs for each unique user seen on our networks.

## URL语法

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL 参数

The [!DNL URL] for your inbound ID synchronization call should contain variables described in the table below.

>[!NOTE]
>
>将斜体内容替换为实际参数值。

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; VADER_ ID&gt;</i></code> </td> 
   <td colname="col2">Unique ID for the data provider (assigned by <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; VADER_ UUID&gt;</i></code> </td> 
   <td colname="col2"> 唯一用户ID。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL&gt;</i></code> </td> 
   <td colname="col2">An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. <p><b>注意：</b> 仅在数据提供程序启动调用时添加。 </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr=&lt;0||&gt;</i></code> </td> 
   <td colname="col2"> <p><code>gdpr</code> can be0(GDPR does not apply) or1(GDPR apply).</p><p><b>注意：</b> <ul><li><code>gdpr</code> 和 <code>gdpr_同意</code> 参数在ID同步URL与激活合作伙伴之间逐渐推出。See Activation partners that support IAB TCF in <a href="../../overview/aam-gdpr/aam-iab-plugin.md#aam-activation-partners">Audience Manager Plug-in for IAB TCF.</a></li><li>This parameter can only be used together with <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_ supagement=&lt; CONDELADE STRING&gt;</i></code> </td> 
   <td colname="col2"><p><code>gdpr_ supagement</code> 是URL安全基础64编码的GDPR同意字符串(请参阅 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB规范</a>)。</p><p><b>注意：</b> 此参数只能与 <code>gdpr</code>一起使用。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [数据收集服务器(DCS) API方法和代码](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [数据收集组件](../../reference/system-components/components-data-collection.md)

