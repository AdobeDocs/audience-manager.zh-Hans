---
description: 描述初始 HTTP 调用中用于同步 Audience Manager 和第三方数据提供程序之间用户 Id 的语法和参数。 在尝试首次 ID 同步之前，请联系您的 Adobe Audience Manager 顾问。
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-title: ID Synchronization for Outbound Data Transfers
solution: Audience Manager
title: 用于出站数据传输的 ID 同步
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 11%

---

# 用于出站数据传输的 ID 同步{#id-synchronization-for-outbound-data-transfers}

描述初始 `HTTP` 调用中用于同步 Audience Manager 和第三方数据提供程序之间用户 id 的语法和参数。 在尝试首次 ID 同步之前，请联系您的 Adobe Audience Manager 顾问。

<!-- c_id_sync_out.xml -->

## ID 同步的目的

ID 同步是出站异步数据传输过程中的第一步。 在此步骤中， [!DNL Audience Manager] 供应商比较并匹配各自网站访客的 id。 例如， [!DNL Audience Manager] 客户可以通过 ID 123 来了解用户。 但是，您的数据合作伙伴可以识别此用户 ID 456。 同步过程允许 [!DNL Audience Manager] 和数据供应商对这些不同的 id 进行协调，并在各自的系统中识别用户。 完成后， [!DNL Audience Manager] 第三方数据提供程序应为网络上的每个独特的用户提供相应的 id。

## URL 语法

在 ID 交换中，格式 [!DNL URL] 正确的字符串应如下所示点赞：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL 参数

[!DNL URL]入站 ID 同步调用应包含下表中所述的变量。

>[!NOTE]
>
>替换具有实际参数值的斜体内容。

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">数据提供程序的唯一 ID （由 <span class="keyword"> Audience Manager </span> 分配）。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> 唯一用户 ID。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">已编码的 URL 重定向嵌入宏 <code> ${DD_UUID}</code> 。 <p><b>注意： </b> 仅在数据提供程序初始化调用时添加。 </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> 可以是0（GDPR 不适用）或1（GDPR 适用）。</p><p><b>注意：</b> <ul><li><code>gdpr</code>使用激活合作伙伴在 ID 同步 url 中逐渐推出 and <code>gdpr_consent</code> 参数。请参阅 IAB TCF Audience Manager 插件中 <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners"> 支持 IAB TCF 的 Activation 合作伙伴。</a></li><li>此参数仅可与 <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> 是 URL 安全的 base64 编码 GDPR 同意字符串（请参阅 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB 规范 </a> ）。</p><p><b>注意： </b> 此参数仅可与 <code>gdpr</code> 一起使用。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [数据收集服务器 (DCS) API 方法和代码](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [数据收集组件](../../reference/system-components/components-data-collection.md)

