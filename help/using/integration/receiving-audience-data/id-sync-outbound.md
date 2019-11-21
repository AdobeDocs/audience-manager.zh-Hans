---
description: 描述初始HTTP调用中用于在Audience manager和第三方数据提供者之间同步用户ID的语法和参数。 在尝试进行第一个ID同步之前，请与Adobe Audience manager顾问联系。
seo-description: 描述初始HTTP调用中用于在Audience manager和第三方数据提供者之间同步用户ID的语法和参数。 在尝试进行第一个ID同步之前，请与Adobe Audience manager顾问联系。
seo-title: 出站数据传输的ID同步
solution: Audience Manager
title: 出站数据传输的ID同步
uuid: f3849be8-1094-47db-9296-7482f020af18
translation-type: tm+mt
source-git-commit: b1e438a77a472c192117a2c1ddcf63f4eb25d07d

---


# 出站数据传输的ID同步{#id-synchronization-for-outbound-data-transfers}

描述初始调用中用于在Audience manager和第 `HTTP` 三方数据提供者之间同步用户ID的语法和参数。 在尝试进行第一个ID同步之前，请与Adobe Audience manager顾问联系。

<!-- c_id_sync_out.xml -->

## ID同步的用途

ID同步是出站异步数据传输过程中的第一步。 在此步骤中，供 [!DNL Audience Manager] 应商将比较并匹配其各自站点访客的ID。 例如，客户可 [!DNL Audience Manager] 能通过ID 123了解用户。 但是，您的数据合作伙伴可以识别此ID为456的用户。 同步过程允许和 [!DNL Audience Manager] 数据供应商协调这些不同的ID并识别其各自系统中的用户。 完成后， [!DNL Audience Manager] 第三方数据提供者应为我们网络上看到的每个唯一用户提供相应的ID。

## URL语法

在ID交换中，格式正确的字 [!DNL URL] 符串应当如下：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL 参数

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
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">数据提供者的唯一ID(由 <span class="keyword"> Audience Manager分配</span>)。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> 唯一用户ID。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">嵌入宏的编码URL重 <code> ${DD_UUID}</code> 定向。 <p><b></b> 注意：仅在数据提供者启动调用时添加。 </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> 可以是0（GDPR不适用）或1（GDPR适用）。</p><p><b>注意：</b> <ul><li>与激 <code>gdpr</code> 活 <code>gdpr_consent</code> 合作伙伴在ID同步URL中逐步转出参数和参数。 请参阅在 <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Audience Manager Plug-in for IAB TCF中支持IAB TCF的激活合作伙伴。</a></li><li>此参数只能与 <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> 是URL安全的基本64编码的GDPR同意字符串(请参阅 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB规范</a>)。</p><p><b></b> 注意：此参数只能与一起使用 <code>gdpr</code>。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Data Collection Server(DCS)API方法和代码](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [数据收集组件](../../reference/system-components/components-data-collection.md)

