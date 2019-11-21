---
description: 描述初始HTTP调用中用于在供应商和Audience manager之间同步用户ID的语法和参数。 ID同步可在您将数据分类发送到Audience Manager后开始。
seo-description: 描述初始HTTP调用中用于在供应商和Audience manager之间同步用户ID的语法和参数。 ID同步可在您将数据分类发送到Audience Manager后开始。
seo-title: 入站数据传输的ID同步
solution: Audience Manager
title: 入站数据传输的ID同步
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
translation-type: tm+mt
source-git-commit: b1e438a77a472c192117a2c1ddcf63f4eb25d07d

---


# 入站数据传输的ID同步{#id-synchronization-for-inbound-data-transfers}

描述初始调用中用于在供应商和Audience manager之 `HTTP` 间同步用户ID的语法和参数。 ID同步可在您将数据分类发送到Audience Manager后开始。

<!-- c_id_sync_in.xml -->

ID同步是入站异步数据传输过程中的第一步。 在此步骤中，Audience manager和供应商比较并匹配各自站点访客的ID。 例如，客户可 [!DNL Audience Manager] 能通过ID 123了解用户。 但是，您的数据合作伙伴可以识别此ID为456的用户。 同步过程允许和 [!DNL Audience Manager] 数据供应商协调这些不同的ID并识别其各自系统中的用户。 完成后， [!DNL Audience Manager] 您的第三方合作伙伴应为我们网络上看到的每个唯一用户提供相应的ID。

您可以使用以下方法将数据导入 [!DNL Audience Manager]:

* [ID同步HTTP请求](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [声明的ID事件](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [从电子邮件嵌入的图像进行ID同步](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID同步请 `HTTP` 求 {#id-sync-http}

在ID交换中，格式正确的字 [!DNL URL] 符串应当如下：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

入站 [!DNL URL] ID同步调用的变量应包含下表中所述的变量。

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
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>内容提供者的唯一ID(由 <span class="keyword"> Audience Manager分配</span>)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL（百分比）唯一用户ID的编码表示形式。 除了对保留的ASCII字符进行编码外，所有非ASCII字符都应根据UTF-8字符编码表进行百分比编码。 </p> <p>有关详细信息，请参阅 <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online网站</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>嵌入宏的编码URL重 <code> ${DD_UUID}</code> 定向。 </p> <p>注意： 仅在内容提供者启动调用时添加。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>可选。如果您使用IAB TCF的 <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager插件，请添加此参数。</a></p> <p><code> gdpr</code> 可以是0（GDPR不适用）或1（GDPR适用）。 </p> <p> <b></b> 注意：此参数只能与一起使用 <code>gdpr_consent</code>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>可选。如果您使用IAB TCF的 <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager插件，请添加此参数。</a></p> <p><code>gdpr_consent</code> 是URL安全的基本64编码的GDPR同意字符串(请参阅 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB规范</a>)。 </p> <p> <b></b> 注意：此参数只能与一起使用 <code>gdpr</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 声明的ID事件 {#declared-id-event}

有关详细信息，请参阅 [声明的ID](../../../features/declared-ids.md)。

## 从电子邮件嵌入的图像进行ID同步 {#id-sync-email-image}

通过电子邮件图像匹配ID的格式与上图所示相同。 但是，必须启用电子邮件中的图像才能使其正常工作。 这会影响通过电子邮件进行ID同步，因为默认情况下，大多数邮件系统都会禁用图像。

>[!MORELIKETHIS]
>
>* [数据收集组件](../../../reference/system-components/components-data-collection.md)

