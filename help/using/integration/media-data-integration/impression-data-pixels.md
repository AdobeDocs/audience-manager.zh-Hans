---
description: 向Audience Manager发送媒体数据的一种方法是使用广告服务器宏将营销活动属性发送到Audience Manager。
seo-description: 向Audience Manager发送媒体数据的一种方法是使用广告服务器宏将营销活动属性发送到Audience Manager。
seo-title: 通过像素调用捕获营销活动展示数据
solution: Audience Manager
title: 通过像素调用捕获营销活动展示数据
uuid: ac44100-4c55-4992-8835-0d578 bb4 e5 c2
translation-type: tm+mt
source-git-commit: c79c2311c3ea76ce2450dc1b84a7a22b60a6edb7

---


# 通过像素调用捕获营销活动展示数据{#capturing-campaign-impression-data-via-pixel-calls}

向Audience Manager发送媒体数据的一种方法是使用广告服务器宏将营销活动属性发送到Audience Manager。

此方法通常称为“像素化创意”。Those data points are dynamically inserted into the [!DNL Audience Manager] pixel code by the third-party ad server macros, which are used to map and report all impressions and clicks based on the key reporting attributes of the campaign. 汇总数据提供了营销活动性能的统一视图，有助于识别自定义转化路径，并帮助客户改进导致转化的广告服务器事件序列。

## 事件调用语法

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）指示代码元素和选项。请参阅[代码和文本元素的样式约定](../../reference/code-style-elements.md)，以了解更多信息。

该事件调用会收集展示和转化数据，并将其发送到 [!DNL Audience Manager] [数据收集服务器](/help/using/reference/system-components/components-data-collection.md) ([!UICONTROL DCS])。此过程依赖于第三方广告服务器，这些服务器将调用置于创意中，以控制插入到代码中的内容。第三方广告服务器（例如，[!DNL DFA]）可以将此代码置于每个广告展示中。而且，广告调用不会使用 [!DNL JavaScript] 或采用禁止 iframe 的嵌套技术来访问广告标记之外的发布者数据。

事件调用由使用以下语法的键值对组成：

<pre>
http://clientname.demdex.net/event?d_event=imp&amp;d_src=datasource_id&amp;d_site=siteID&amp;
d_creative=<i>creative_id</i>&amp;d_adgroup=<i>adgroup_id</i>&amp;d_placement=<i>placement_id</i>
&amp;d_campaign=<i>campaign_id</i>[&amp;d_cid=(GAID|IDFA)%01 DPUUID]&amp;d_bust=cache buster value
</pre>

在键值对中，value变量是由广告服务器插入的ID或宏。When the ad tag loads, that `%macro%` gets replaced with the required, corresponding values. 此调用不返回回复。

## Supported Key-Value Pairs {#supported-key-value-pairs}

印象事件调用接受构成关键值对的数据。下表列出并描述用于保存这些变量的键。Many of these are required if you want to capture and analyze data in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 键值 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_ adgroup </code> </td> 
   <td colname="col2"> <p>广告服务器中的数字广告组ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ adsrc </code> </td> 
   <td colname="col2"> <p>适用于广告商的数据源ID或集成代码。 </p> <p><span class="wintitle"> 受众优化 </span> 报告所必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ bu </code> </td> 
   <td colname="col2"> <p>您的业务单位的数据源ID或集成代码。 </p> <p><span class="wintitle"> 受众优化 </span> 报告所必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bust </code> </p> </td> 
   <td colname="col2"> <p>缓存中断值。<span class="keyword"> Audience Manager </span> 自动发送受大多数浏览器和代理支持的缓存控制标头。如果要执行额外的缓存跳出，请在事件调用中包括此参数，然后在一个随机字符串中包含该参数。 </p> <p> 可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ campaign </code> </td> 
   <td colname="col2"> <p>广告服务器中的数字系列活动ID。 </p> <p><span class="wintitle"> 受众优化 </span> 报告所必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In this context, <code> d_cid </code> instantiates a key-value pair that lets you associate a mobile device type to a unique user ID (DPUUID). 固定ID决定移动设备类型。该值(即用户ID)可能会有所不同。Separate the key-value pair with <code> %01 </code>, which is a non-printing control character. 此参数接受以下键： </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914：标识Android(GID)设备。For example, <code> d_cid = 20914 %01 1234 </code> says that user 1234 is associated with an Android device. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915：标识iOS(IDFA)设备。For example, <code> d_cid = 20915 %01 5678 </code> says that user 5678 is associated with an iOS device. </li> 
    </ul> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ creative </code> </td> 
   <td colname="col2"> <p>广告服务器中的数字创意ID。 </p> <p><span class="wintitle"> 受众优化 </span> 报告所必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ event= ip </code> </td> 
   <td colname="col2"> <p>将活动调用标识为印象事件。 </p> <p>必需. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ placement </code> </td> 
   <td colname="col2"> <p>广告服务器中的数字放置ID。 </p> <p> 可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ site </code> </td> 
   <td colname="col2"> <p>广告服务器中的数字站点ID。 </p> <p><span class="wintitle"> 受众优化 </span> 报告所必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ src </code> </td> 
   <td colname="col2"> <p>提供元数据(例如，DFA、Atlas、GBM、Media Math等)的平台的数据源ID或集成代码。 </p> <p><span class="wintitle"> 受众优化 </span> 报告所必需。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code><i>gdpr</i></code>  </td> 
   <td colname="col2"> <p>与<a href="../../overview/aam-gdpr/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p> <p><code>gdpr</code> can be0(GDPR does not apply) or1(GDPR apply).</p> <p>默认值为 0。</p><p>可选。</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_ reagencement</code> </td> 
   <td colname="col2"> <p>与<a href="../../overview/aam-gdpr/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p><p> 如果 <code>gdpr=1</code>，则 <code>%gdpr_consent%</code> 将被替换为字符串 <code>gdpr_consent</code>（请参阅 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">IAB 规范</a>）。</p> <p>默认值为 0。</p><p>可选。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>请与Adobe Audience Manager咨询或帐户主管联系，获得特定于客户域的URL。

>[!MORE_ LIKE_ This]
>
>* [用于受众优化报告的数据和元数据文件](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

