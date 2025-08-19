---
description: 描述初始HTTP调用中使用的语法和参数，以便在供应商和Audience Manager之间同步用户ID。 将数据分类发送到Audience Manager后，可以开始ID同步。
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between a vendor and Audience Manager. ID synchronization can begin after you send your data taxonomy to Audience Manager.
seo-title: ID Synchronization for Inbound Data Transfers
solution: Audience Manager
title: 用于入站数据传输的ID同步
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Inbound Data Transfers
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 1%

---

# 用于入站数据传输的ID同步 {#id-synchronization-for-inbound-data-transfers}

描述初始`HTTP`调用中使用的语法和参数，以便在供应商和[!DNL Audience Manager]之间同步用户ID。 将数据分类发送到[!DNL Audience Manager]后，可以开始ID同步。

ID同步是入站异步数据传输过程中的第一步。 在此步骤中，[!DNL Audience Manager]和供应商将比较并匹配各自站点访客的ID。 例如，[!DNL Audience Manager]客户可能通过ID 123认识用户。 但是，您的数据合作伙伴可以使用ID 456识别此用户。 同步过程允许[!DNL Audience Manager]和数据供应商协调这些不同的ID并识别其各自系统中的用户。 完成后，[!DNL Audience Manager]和您的第三方合作伙伴应该为我们在网络上看到的每个独特用户拥有相应的ID。

您可以使用以下方法将数据导入[!DNL Audience Manager]：

* [ID同步HTTP请求](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [声明的ID事件](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [从电子邮件嵌入图像进行ID同步](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID同步`HTTP`请求 {#id-sync-http}

在ID交换中，正确格式化的[!DNL URL]字符串应如下所示：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

入站ID同步调用的[!DNL URL]应包含下表所述的变量。

>[!NOTE]
>
>将斜体化的内容替换为实际参数值。

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>内容提供商的唯一ID(由<span class="keyword"> Audience Manager</span>分配)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>独特用户ID的URL（百分比）编码表示形式。 除了编码保留的ASCII字符外，任何非ASCII字符都应根据UTF-8字符编码表进行百分比编码。 </p> <p>有关详细信息，请参阅联机<a href="https://www.url-encode-decode.com" format="http" scope="external">上的</a> URL编码/解码网站。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>嵌入了宏<code> ${DD_UUID}</code>的编码URL重定向。 </p> <p>注意：仅在内容提供程序启动调用时添加。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>可选。如果您使用的是适用于IAB TCF的<a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager插件，请添加此参数。</a></p> <p><code> gdpr</code> 可以为0（GDPR不适用）或1（GDPR适用）。 </p> <p> <b>注意：</b>此参数只能与<code>gdpr_consent</code>一起使用。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>可选。如果您使用的是适用于IAB TCF的<a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager插件，请添加此参数。</a></p> <p><code>gdpr_consent</code> 是URL安全的base64编码GDPR同意字符串（请参阅<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB规范</a>）。 </p> <p> <b>注意：</b>此参数只能与<code>gdpr</code>一起使用。</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID]事件 {#declared-id-event}

有关详细信息，请参阅[声明的ID](../../../features/declared-ids.md)。

## 从电子邮件嵌入图像进行ID同步 {#id-sync-email-image}

通过电子邮件图像匹配ID的格式与上面所示的格式相同。 但请注意，必须启用电子邮件中的图像才能使此功能正常工作。 这可能会影响通过电子邮件进行的ID同步，因为大多数邮件系统默认会禁用图像。

>[!MORELIKETHIS]
>
>* [数据收集组件](../../../reference/system-components/components-data-collection.md)
