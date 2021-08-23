---
description: 一种将媒体数据发送到Audience Manager的方法是使用广告服务器宏将促销活动属性发送到Audience Manager。
seo-description: 一种将媒体数据发送到Audience Manager的方法是使用广告服务器宏将促销活动属性发送到Audience Manager。
seo-title: 通过像素调用捕获营销活动展示数据
solution: Audience Manager
title: 通过像素调用捕获营销活动展示数据
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
feature: Adobe Campaign集成
exl-id: 04e6f1e5-5075-4221-a310-deb3717458ad
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 20%

---

# 通过像素调用捕获营销活动展示数据{#capturing-campaign-impression-data-via-pixel-calls}

一种将媒体数据发送到Audience Manager的方法是使用广告服务器宏将促销活动属性发送到Audience Manager。

这种方法通常被称为“对创意进行像素化”。 这些数据点通过第三方广告服务器宏动态插入到[!DNL Audience Manager]像素代码中，用于根据营销活动的关键报告属性映射和报告所有展示次数和点击次数。 汇总数据提供营销活动效果的统一视图，帮助识别自定义转化路径，并帮助客户改进导致转化的广告服务器事件顺序。

## 事件调用语法

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）指示代码元素和选项。请参阅[代码和文本元素的样式约定](../../reference/code-style-elements.md)，以了解更多信息。

该事件调用会收集展示和转化数据，并将其发送到 [!DNL Audience Manager] [数据收集服务器](/help/using/reference/system-components/components-data-collection.md) ([!DNL DCS])。此过程依赖于第三方广告服务器，这些服务器将调用置于创意中，以控制插入到代码中的内容。第三方广告服务器（例如，[!DNL DFA]）可以将此代码置于每个广告展示中。而且，广告调用不会使用 [!DNL JavaScript] 或采用禁止 iframe 的嵌套技术来访问广告标记之外的发布者数据。

事件调用由使用以下语法的键值对组成：

```
https://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

在键值对中，值变量是广告服务器插入的ID或宏。 加载广告标记时，该`%macro%`将被替换为所需的相应值。 此调用不返回响应。

## 支持的键值对 {#supported-key-value-pairs}

展示事件调用接受形成键值对的数据。 下表列出并描述了用于保存这些变量的键。 如果要捕获并分析[Audience Optimization报表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)中的数据，则需要使用其中的许多数据。

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 键值 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_adgroup </code> </td> 
   <td colname="col2"> <p>广告服务器中的数字广告组ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>广告商的数据源ID或集成代码。 </p> <p><span class="wintitle">Audience Optimization</span>报表必需。 </p> <p>可选。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>您业务部门的数据源ID或集成代码。 </p> <p><span class="wintitle">Audience Optimization</span>报表必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>缓存嵌套值。 <span class="keyword"> Audience Manager </span> 会自动发送大多数浏览器和代理都接受的缓存控制标头。如果要执行其他缓存嵌套，请将此参数包含在事件调用中，然后添加随机字符串。 </p> <p> 可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>广告服务器中的数字促销活动ID。 </p> <p><span class="wintitle">Audience Optimization</span>报表必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>在此上下文中， <code> d_cid </code>实例化一个键值对，以便将移动设备类型与唯一用户ID(DPUUID)关联。 固定ID可确定移动设备类型。 值（即用户ID）可能会有所不同。 将键值对与<code> %01 </code>分开，后者是非打印控制字符。 此参数接受以下键： </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914:标识Android(GAID)设备。 例如， <code> d_cid = 20914 %01 1234 </code>表示用户1234与Android设备关联。 </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915:标识iOS(IDFA)设备。 例如， <code> d_cid = 20915 %01 5678 </code>表示用户5678与iOS设备相关联。 </li> 
    </ul> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>广告服务器中的数字创作ID。 </p> <p><span class="wintitle">Audience Optimization</span>报表必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>将事件调用标识为展示事件。 </p> <p>必需. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>广告服务器中的数字版面ID。 </p> <p> 可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>广告服务器中的网站ID数字。 </p> <p><span class="wintitle">Audience Optimization</span>报表必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>提供元数据的平台的数据源ID或集成代码（例如DFA、Atlas、GBM、媒体数学等）。 </p> <p><span class="wintitle">Audience Optimization</span>报表必需。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p>与<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p> <p><code>gdpr</code> 可以是0（GDPR不适用）或1（GDPR适用）。</p> <p>默认值为 0。</p><p>可选。</p><p>如果为<code>gdpr=1</code>，则<code>gdpr_consent</code>参数应包含IAB TC同意参数以成功处理数据。 否则，将删除所有数据。</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p>与<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p><p> 如果为<code>gdpr=1</code>，则<code>${gdpr_consent_XXXX}</code>将被替换为<code>gdpr_consent</code>字符串和供应商ID（请参阅<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB规范</a>）。</p> <p>默认值为 0。</p><p>可选。</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>有关特定于客户端域的确切URL，请联系您的Adobe Audience Manager咨询人员或客户主管。

## 其他功能 — [!DNL Audience Optimization Reports] {#additional-functionality-aor}

您可以使用像素调用为[Audience Optimization报表](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md)供电。 如果您希望使用像素来为报表供电，请参阅[元数据文件的概述和映射](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。

>[!MORELIKETHIS]
>
>* [Audience Optimization报表的数据和元数据文件](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

