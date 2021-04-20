---
description: 点击跟踪可衡量您整个活动的访客参与度，因为它记录了第三方创意人员的基于点击的活动。
seo-description: 点击跟踪可衡量您整个活动的访客参与度，因为它记录了第三方创意人员的基于点击的活动。
seo-title: 通过像素调用捕获营销活动点击数据
solution: Audience Manager
title: 通过像素调用捕获营销活动点击数据
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Adobe Campaign Integration
exl-id: 41b169bf-3727-4ed7-b74f-fea75244d2cb
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 11%

---

# 通过像素调用捕获营销活动点击数据 {#capturing-campaign-click-data-via-pixel-calls}

点击跟踪可衡量您整个活动的访客参与度，因为它记录了第三方创意人员的基于点击的活动。 与[展示集合](/help/using/integration/media-data-integration/impression-data-pixels.md)类似，事件调用被发送到[!DNL Audience Manager]数据收集服务器([!DNL DCS])以进行处理。 然后将访客重定向到预期的Web地址。

>[!NOTE]
>
>请联系您的[!DNL Audience Manager]咨询或帐户主管，了解特定于客户端域的确切[!DNL URL]。

## 要求

单击跟踪调用需要以下参数：

* `d_event=click`:将事件调用标识为单击事件的键值对。
* `d_rd=redirect URL`:包含多次编码重定向的键值对 [!DNL URL]。如果您使用的是联机编码工具，请通过编码器运行该字符串，然后再次对结果进行编码，以便重定向正常工作。

此外，调用可包含键值对，这些键值对可用于特征限定或为其他报表提供数据和元数据。

## 请求示例

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 响应

响应会将浏览器重定向到在`d_rd`参数中指定的[!DNL URL]。 响应字符串可以包括由下列任何支持的宏生成的值。

根据上述示例，浏览器将重定向到以下[!DNL URL]:

`https://adobe.com/callback?creative=123`

## 支持的宏

单击“事件”支持下表中列出的宏。 宏是自包含的小代码单位，加载广告标签以进行活动和用户跟踪时将激活。 宏将随目标[!DNL URL]一起传递，只要它们以下列格式标记：`%macro%`。 某些键没有宏，而是接受硬编码ID值。 如果要分析[Audience Optimization报告](../../reporting/audience-optimization-reports/audience-optimization-reports.md)中的数据，则需要接受硬编码值的键。

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 键 </th> 
   <th colname="col02" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_adgroup%</code> </p> </td> 
   <td colname="col2"> <p>广告服务器中的数字广告组ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>没有宏。 </p> <p>接受硬编码ID值。 </p> </td> 
   <td colname="col2"> <p>广告商 ID.</p> <p>广告商数据源的集成代码。 请注意，这与Audience Manager数据源无关。</p> <p> <span class="wintitle">Audience Optimization</span>报告必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>业务单位的数字ID。 </p> <p> <span class="wintitle">Audience Optimization</span>报告必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>广告服务器中的数字活动ID。 </p> <p> <span class="wintitle">Audience Optimization</span>报告必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>广告服务器中的数字创意ID。 </p> <p>必需. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>数据提供者ID。 </p> <p>通常与<code> d_dpuuid</code>一起使用，将数据提供程序ID链接到用户ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>由数据提供者提供的唯一用户ID。 </p> <p>通常与<code> d_dpid</code>一起使用，将用户ID链接到数据提供程序ID。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"></span> Experience Cloud ID (ECID). 有关ECID的详细信息，请参阅<a href="https://docs.adobe.com/content/help/zh-Hans/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies和Experience CloudID</a>。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>广告服务器中的数字位置ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>为请求提供服务的DCS群集的数字区域ID。 有关DCS的详细信息，请参阅<a href="../../reference/system-components/components-data-collection.md">数据收集组件</a>。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>用于缓存破坏的随机数。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>广告服务器中的数字站点ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>源的DPID，Audience Manager从中提取元数据。 </p> <p>必需. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>直接在URL中指定访客的ID，而不是依赖Demdex cookie。 </p> <p>可选。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p>与<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。 </p><p><code>gdpr</code> 可以是0（GDPR不适用）或1（GDPR适用）。</p> <p>默认值为 0。</p><p>可选。</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p>与<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p><p> 如果<code>gdpr=1</code>，则<code>${gdpr_consent_XXXX}</code>由<code>gdpr_consent</code>字符串和供应商ID替换（请参阅<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB规范</a>）。</p> <p>默认值为 0。</p><p>可选。</p></td> 
  </tr> 
 </tbody> 
</table>

## 宏示例

此示例演示如何传递创意宏、adgroup宏和放置宏。 它假定每个参数的值都传递到单击跟踪调用的非重定向部分。

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> placement=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## 请求

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd%3Dhttp%253A%252F%252Fadobe.com%252Fcallback%253Fcreative%253D%2525d_creative%2525%2526campaign%253D%2525d_campaign%2525%2526adgroup%253D%2525%0Ad_adgroup%2525%2526d_placement%253D%2525placement%2525%2526src%253D%2525d_src%2525
```

## 响应

根据上述示例，浏览器将重定向到以下[!DNL URL]:

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## 其他功能 — [!UICONTROL Audience Optimization Reports]

可以使用像素调用为[Audience Optimization报表](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md)供电。 如果您希望使用像素来为报表提供动力，请参阅[元数据文件的概述和映射](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。


>[!MORELIKETHIS]
>
>* [用于Audience Optimization报表的数据和元数据文件](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

