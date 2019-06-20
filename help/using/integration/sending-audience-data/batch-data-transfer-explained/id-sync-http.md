---
description: 描述在初始HTTP调用中使用的语法和参数，以同步供应商与Audience Manager之间的用户ID。在将数据分类发送给Audience Manager之后，可以开始ID同步。
seo-description: 描述在初始HTTP调用中使用的语法和参数，以同步供应商与Audience Manager之间的用户ID。在将数据分类发送给Audience Manager之后，可以开始ID同步。
seo-title: 用于入站数据传输的ID同步
solution: Audience Manager
title: 用于入站数据传输的ID同步
uuid: 037e74a6-acfd-4cf-b693-16b7 aa8 e976
translation-type: tm+mt
source-git-commit: 0fac081c93be36d2aa40023c7323ef1886b3860a

---


# ID Synchronization for Inbound Data Transfers{#id-synchronization-for-inbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between a vendor and Audience Manager. 在将数据分类发送给Audience Manager之后，可以开始ID同步。

<!-- c_id_sync_in.xml -->

ID同步是入站、异步数据传输过程中的第一步。在此步骤中，Audience Manager和供应商比较和匹配各自站点访客的ID。For example, an [!DNL Audience Manager] customer may know a user by ID 123. 但是，您的数据合作伙伴可以识别此用户ID为456。The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and your third-party partner should have corresponding IDs for each unique user seen on our networks.

You can use the following methods to get your data into [!DNL Audience Manager]:

* [ID同步HTTP请求](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [声明的ID事件](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [通过电子邮件嵌入式图像进行ID同步](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID Synchronization `HTTP` Request {#id-sync-http}

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code><i>&lt; VADER_ ID&gt;</i></code> </td> 
   <td colname="col2"> <p>Unique ID for the content provider (assigned by <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; VADER_ UUID&gt;</i></code> </td> 
   <td colname="col2"> <p>URL(百分比)您的唯一用户ID的编码表示形式。除了对保留的ASCII字符进行编码外，任何非ASCII字符都应基于UTF-8字符编码表进行编码。 </p> <p>For more information, see the <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a> website. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL&gt;</i></code> </td> 
   <td colname="col2"> <p>An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. </p> <p>注意：仅当内容提供程序启动调用时添加。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr=&lt;0||&gt;</i></code> </td> 
   <td colname="col2"> <p>可选。Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code> gdpr</code> can be0(GDPR does not apply) or1(GDPR apply). </p> <p> <b>注意：</b> 此参数只能与 <code>gdpr_同意一起使用</code>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_ supagement=&lt; CONDELADE STRING&gt;</i></code> </td> 
   <td colname="col2"> <p>可选。Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code>gdpr_ supagement</code> 是URL安全基础64编码的GDPR同意字符串(请参阅 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB规范</a>)。 </p> <p> <b>注意：</b> 此参数只能与 <code>gdpr</code>一起使用。</p> </td> 
  </tr> 
 </tbody> 
</table>

## Declared ID Event {#declared-id-event}

For more information, see [Declared IDs](../../../features/declared-ids.md).

## ID Synchronization From an Email Embedded Image {#id-sync-email-image}

通过电子邮件图像匹配ID的格式与上面所示相同。但是请注意，必须启用电子邮件中的图像才能使用。这会影响通过电子邮件同步ID，因为大多数邮件系统默认会禁用图像。

>[!MORE_ LIKE_ This]
>
>* [数据收集组件](../../../reference/system-components/components-data-collection.md)

