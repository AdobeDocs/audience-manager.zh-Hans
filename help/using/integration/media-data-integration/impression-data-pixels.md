---
description: 将媒体数据发送到Audience Manager的一种方法使用广告服务器宏将促销活动属性发送到Audience Manager。
seo-description: One approach for sending media data to Audience Manager uses ad server macros to send campaign attributes to Audience Manager.
seo-title: Capturing Campaign Impression Data via Pixel Calls
solution: Audience Manager
title: 通过像素调用捕获营销活动展示数据
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
feature: Adobe Campaign Integration
exl-id: 04e6f1e5-5075-4221-a310-deb3717458ad
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 16%

---

# 通过像素调用捕获营销活动展示数据{#capturing-campaign-impression-data-via-pixel-calls}

将媒体数据发送到Audience Manager的一种方法使用广告服务器宏将促销活动属性发送到Audience Manager。

这种方法通常称为“将创意内容像素化”。 这些数据点由第三方广告服务器宏动态插入到[!DNL Audience Manager]像素代码中，这些宏用于根据营销活动的关键报告属性映射和报告所有展示次数和点击次数。 聚合的数据可提供促销活动性能的统一视图，有助于识别自定义转化路径，并帮助客户改进导致转化的广告服务器事件的顺序。

## 事件调用语法

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）指示代码元素和选项。请参阅[代码和文本元素的样式约定](../../reference/code-style-elements.md)，以了解更多信息。

事件调用收集展示和转化数据，并将其发送到[!DNL Audience Manager] [数据收集服务器](/help/using/reference/system-components/components-data-collection.md) ([!DNL DCS])。 此过程依赖于第三方广告服务器，这些服务器将调用置于创意中，以控制插入到代码中的内容。第三方广告服务器（例如，[!DNL DFA]）可以将此代码置于每个广告展示中。而且，广告调用不会使用 [!DNL JavaScript] 或采用禁止 iframe 的嵌套技术来访问广告标记之外的发布者数据。

事件调用包含使用以下语法的键值对：

```
https://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

在键值对中，值变量是由广告服务器插入的ID或宏。 加载广告标记时，该`%macro%`将被替换为所需的相应值。 此调用不返回响应。

## 支持的键值对 {#supported-key-value-pairs}

印象事件调用接受构成键值对的数据。 下表列出并描述了用于保存这些变量的键。 如果您要捕获和分析[Audience Optimization报表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)中的数据，则需要进行许多此类操作。

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 键 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_adgroup </code> </td> 
   <td colname="col2"> <p>广告服务器上的数值广告组ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>广告商的数据源ID或集成代码。 </p> <p><span class="wintitle">Audience Optimization</span>报告需要。 </p> <p>可选。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>业务部门的数据源ID或集成代码。 </p> <p><span class="wintitle">Audience Optimization</span>报告需要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Cache-busting值。 <span class="keyword">Audience Manager</span>自动发送大多数浏览器和代理遵循的缓存控制标头。 如果要执行额外的缓存无效，请将此参数包含在事件调用中，后跟一个随机字符串。 </p> <p> 可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>广告服务器的数字营销活动ID。 </p> <p><span class="wintitle">Audience Optimization</span>报告需要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>在此上下文中，<code> d_cid </code>实例化一个键值对，该键值对允许您将移动设备类型与唯一用户ID (DPUUID)相关联。 固定ID可确定移动设备类型。 该值（即用户ID）可能会有所不同。 使用<code> %01 </code>分隔键值对，这是非打印控制字符。 此参数接受以下键： </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914：标识Android (GAID)设备。 例如，<code> d_cid = 20914 %01 1234 </code>说用户1234与Android设备相关联。 </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915：标识iOS (IDFA)设备。 例如，<code> d_cid = 20915 %01 5678 </code>说用户5678与iOS设备相关联。 </li> 
    </ul> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>广告服务器上的数字创意ID。 </p> <p><span class="wintitle">Audience Optimization</span>报告需要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>将事件调用标识为展示事件。 </p> <p>必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>广告服务器上的数字版面ID。 </p> <p> 可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>广告服务器上的数值网站ID。 </p> <p><span class="wintitle">Audience Optimization</span>报告需要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>提供元数据的平台的数据源ID或集成代码（例如DFA、Atlas、GBM、Media Math等）。 </p> <p><span class="wintitle">Audience Optimization</span>报告需要。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p>与<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p> <p><code>gdpr</code> 可以为0（GDPR不适用）或1（GDPR适用）。</p> <p>默认值为 0。</p><p>可选。</p><p>如果<code>gdpr=1</code>，则<code>gdpr_consent</code>参数应包含IAB TC同意参数以成功处理数据。 否则，将丢弃所有数据。</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p>与<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p><p> 如果<code>gdpr=1</code>，则<code>${gdpr_consent_XXXX}</code>将被替换为字符串<code>gdpr_consent</code>和供应商ID（请参阅<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB规范</a>）。</p> <p>默认值为 0。</p><p>可选。</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>请联系您的Adobe Audience Manager咨询或客户主管，以获取特定于客户端域的确切URL。

## 其他功能 — [!DNL Audience Optimization Reports] {#additional-functionality-aor}

您可以使用像素调用为[Audience Optimization报表](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md)供电。 如果要使用像素为报表供电，请参阅[元数据文件的概述和映射](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。

>[!MORELIKETHIS]
>
>* Audience Optimization报表的[数据和元数据文件](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)
