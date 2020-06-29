---
description: 描述初始HTTP调用中使用的语法和参数，以在Audience Manager和第三方数据提供程序之间同步用户ID。 在尝试第一个ID同步之前，请与Adobe Audience Manager顾问联系。
seo-description: 描述初始HTTP调用中使用的语法和参数，以在Audience Manager和第三方数据提供程序之间同步用户ID。 在尝试第一个ID同步之前，请与Adobe Audience Manager顾问联系。
seo-title: 用于出站数据传输的 ID 同步
solution: Audience Manager
title: 用于出站数据传输的 ID 同步
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 12%

---


# 用于出站数据传输的 ID 同步{#id-synchronization-for-outbound-data-transfers}

描述初始调用中使用的语法 `HTTP` 和参数，以在Audience Manager和第三方数据提供程序之间同步用户ID。 在尝试第一个ID同步之前，请与Adobe Audience Manager顾问联系。

<!-- c_id_sync_out.xml -->

## ID同步的用途

ID同步是出站异步数据传输过程中的第一步。 在此步骤中， [!DNL Audience Manager] 供应商将比较和匹配各自站点访客的ID。 例如，客 [!DNL Audience Manager] 户可能通过ID 123了解用户。 但是，您的数据合作伙伴可以识别此ID为456的用户。 同步过程允许 [!DNL Audience Manager] 和数据供应商协调这些不同的ID并标识其各自系统中的用户。 完成后， [!DNL Audience Manager] 第三方数据提供者应为我们网络上看到的每个唯一用户提供相应的ID。

## URL语法

在ID交换中，格式正确的字 [!DNL URL] 符串应当如下：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL 参数

入 [!DNL URL] 站ID同步调用应包含下表所述的变量。

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
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">数据提供程序的唯一ID(由Audience Manager <span class="keyword"> 分配</span>)。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> 唯一用户ID。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">嵌入宏的编码URL重 <code> ${DD_UUID}</code> 定向。 <p><b>注意：</b> 仅在数据提供程序启动调用时添加。 </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> 可以是0（GDPR不适用）或1（GDPR适用）。</p><p><b>注意：</b> <ul><li>正在 <code>gdpr</code> 与激活 <code>gdpr_consent</code> 合作伙伴在ID同步URL中逐步转出这些和参数。 在IAB TCF的激活插件中查 <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">看支持IAB TCF的Audience Manager合作伙伴。</a></li><li>此参数只能与 <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> is the URL-safe base64-encoded GDPR consent string (see <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB specification</a>).</p><p><b>注意：</b> 此参数只能与一起使用 <code>gdpr</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [数据收集服务器 (DCS) API 方法和代码](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [数据收集组件](../../reference/system-components/components-data-collection.md)

