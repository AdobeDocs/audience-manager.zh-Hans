---
description: 将媒体数据发送到Audience manager的一种方法是使用广告服务器宏将营销活动属性发送到Audience Manager。
seo-description: 将媒体数据发送到Audience manager的一种方法是使用广告服务器宏将营销活动属性发送到Audience Manager。
seo-title: 通过像素调用捕获营销活动展示数据
solution: Audience Manager
title: 通过像素调用捕获营销活动展示数据
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
translation-type: tm+mt
source-git-commit: 7f71a099157e81c8d17cf018a4c84a69e2205bb4

---


# 通过像素调用捕获营销活动展示数据{#capturing-campaign-impression-data-via-pixel-calls}

将媒体数据发送到Audience manager的一种方法是使用广告服务器宏将营销活动属性发送到Audience Manager。

这种方法通常被称为“将创意像素化”。 这些数据点通过第三方和服务器宏动态插入像素代码中，这些宏用于根据营销活动的关键报告属性映射和报告所有印象和点击。 [!DNL Audience Manager] 汇总的数据提供营销活动效果的统一视图，帮助识别自定义转化路径，并帮助客户改进导致转化的广告服务器事件的顺序。

## 事件调用语法

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）指示代码元素和选项。请参阅[代码和文本元素的样式约定](../../reference/code-style-elements.md)，以了解更多信息。

该事件调用会收集展示和转化数据，并将其发送到 [!DNL Audience Manager] [数据收集服务器](/help/using/reference/system-components/components-data-collection.md) ([!UICONTROL DCS])。此过程依赖于第三方广告服务器，这些服务器将调用置于创意中，以控制插入到代码中的内容。第三方广告服务器（例如，[!DNL DFA]）可以将此代码置于每个广告展示中。而且，广告调用不会使用 [!DNL JavaScript] 或采用禁止 iframe 的嵌套技术来访问广告标记之外的发布者数据。

事件调用由使用以下语法的键值对组成：

<pre>
http://clientname.demdex.net/event?d_event=imp&amp;d_src=datasource_id&amp;d_site=siteID&amp;d_creative=<i>creative_id</i>&amp;d_adgroup=<i>adgroup_id</i>&amp;d_placement=<i>placement_id</i>&amp;d_campaign<i></i>_id=campaign_idCampaign[&amp;d_cid=GAID|IDFA)%01 DPUUID]&amp;d_bust=缓存值
</pre>

在键值对中，值变量是广告服务器插入的ID或宏。 加载广告标签时，该标 `%macro%` 签将被所需的相应值替换。 此调用不返回响应。

## 支持的键值对 {#supported-key-value-pairs}

印象事件调用接受形成为键值对的数据。 下表列出并描述了用于保存这些变量的键。 如果您要在受众优化报告中捕获和分析数据，则需要执行 [许多操作](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。

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
   <td colname="col2"> <p>广告商的数据源ID或集成代码。 </p> <p>受众优化 <span class="wintitle"> 报告所 </span> 需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>您业务部门的数据源ID或集成代码。 </p> <p>受众优化 <span class="wintitle"> 报告所 </span> 需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>缓存破坏值。 <span class="keyword"> Audience manager会自 </span> 动发送大多数浏览器和代理都支持的缓存控制标题。 如果要执行其他缓存破坏，请在事件调用中包含此参数，后跟随机字符串。 </p> <p> 可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>广告服务器中的数字系列活动ID。 </p> <p>受众优化 <span class="wintitle"> 报告所 </span> 需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>在此上下文中， <code></code> d_cid实例化键值对，使您能够将移动设备类型与唯一用户ID(DPUUID)关联。 固定ID决定移动设备类型。 该值是用户ID，可能不同。 将键值对与 <code> %01分开 </code>，这是非打印控制字符。 此参数接受以下键： </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">二零九一四年：标识Android(GAID)设备。 例如， <code> d_cid = 20914 %01 1234表示用 </code> 户1234与Android设备关联。 </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">二零九一五年：标识iOS(IDFA)设备。 例如， <code> d_cid = 20915 %01 5678表示 </code> 用户5678与iOS设备关联。 </li> 
    </ul> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>广告服务器中的数字创意ID。 </p> <p>受众优化 <span class="wintitle"> 报告所 </span> 需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>将活动调用标识为印象事件。 </p> <p>必需. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>广告服务器中的数字放置ID。 </p> <p> 可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>广告服务器中的数字站点ID。 </p> <p>受众优化 <span class="wintitle"> 报告所 </span> 需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>提供元数据的平台的数据源ID或集成代码（例如，DFA、Atlas、GBM、媒体数学等）。 </p> <p>受众优化 <span class="wintitle"> 报告所 </span> 需。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code><i>gdpr</i></code>  </td> 
   <td colname="col2"> <p>与<a href="../../overview/aam-gdpr/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p> <p><code>gdpr</code> 可以是0（GDPR不适用）或1（GDPR适用）。</p> <p>默认值为 0。</p><p>可选。</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_connection</code> </td> 
   <td colname="col2"> <p>与<a href="../../overview/aam-gdpr/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p><p> 如果 <code>gdpr=1</code>，则 <code>%gdpr_consent%</code> 将被替换为字符串 <code>gdpr_consent</code>（请参阅 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">IAB 规范</a>）。</p> <p>默认值为 0。</p><p>可选。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>请与Adobe Audience Manager咨询或客户潜在客户联系，获取特定于客户域的确切URL。

>[!MORE_LIKE_THIS]
>
>* [受众优化报告的数据和元数据文件](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

