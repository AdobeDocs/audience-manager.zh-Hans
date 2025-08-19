---
description: 描述初始HTTP调用中使用的语法和参数，以便在Audience Manager和第三方数据提供商之间同步用户ID。 在尝试首次ID同步之前，请联系您的Adobe Audience Manager顾问。
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-title: ID Synchronization for Outbound Data Transfers
solution: Audience Manager
title: 用于出站数据传输的ID同步
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 2%

---

# 用于出站数据传输的ID同步{#id-synchronization-for-outbound-data-transfers}

描述初始`HTTP`调用中使用的语法和参数，以便在Audience Manager和第三方数据提供程序之间同步用户ID。 在尝试首次ID同步之前，请联系您的Adobe Audience Manager顾问。

<!-- c_id_sync_out.xml -->

## ID同步的目的

ID同步是出站异步数据传输过程中的第一步。 在此步骤中，[!DNL Audience Manager]和供应商将比较并匹配各自站点访客的ID。 例如，[!DNL Audience Manager]客户可能通过ID 123认识用户。 但是，您的数据合作伙伴可以使用ID 456识别此用户。 同步过程允许[!DNL Audience Manager]和数据供应商协调这些不同的ID并识别其各自系统中的用户。 完成后，[!DNL Audience Manager]和第三方数据提供商应该具有在我们的网络上看到的每个唯一用户的相应ID。

## URL语法

在ID交换中，正确格式化的[!DNL URL]字符串应如下所示：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL 参数

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
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">数据提供商的唯一ID(由<span class="keyword"> Audience Manager</span>分配)。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> 独特用户ID。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">嵌入了宏<code> ${DD_UUID}</code>的编码URL重定向。 <p><b>注意：</b>仅在数据提供程序启动调用时添加。 </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> 可以为0（GDPR不适用）或1（GDPR适用）。</p><p><b>注意：</b> <ul><li><code>gdpr</code>和<code>gdpr_consent</code>参数正在与激活合作伙伴一起逐步转出到ID同步URL中。 请参阅适用于IAB TCF的<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Audience Manager插件中支持IAB TCF的激活合作伙伴。</a></li><li>此参数只能与 <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> 是URL安全的base64编码GDPR同意字符串（请参阅<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB规范</a>）。</p><p><b>注意：</b>此参数只能与<code>gdpr</code>一起使用。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [数据收集服务器(DCS) API方法和代码](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [数据收集组件](../../reference/system-components/components-data-collection.md)
