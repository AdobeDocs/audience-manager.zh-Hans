---
description: 点击跟踪支持在整个营销活动中测量访客参与度，因为它记录第三方创意人员基于点击的活动。
seo-description: Click tracking enables measurement of visitor engagement throughout your campaign, as it records click-based activity for third-party creatives.
seo-title: Capturing Campaign Click Data via Pixel Calls
solution: Audience Manager
title: 通过像素调用捕获营销活动点击数据
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Adobe Campaign Integration
exl-id: 41b169bf-3727-4ed7-b74f-fea75244d2cb
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 6%

---

# 通过像素调用捕获营销活动点击数据 {#capturing-campaign-click-data-via-pixel-calls}

点击跟踪支持在整个营销活动中测量访客参与度，因为它记录第三方创意人员基于点击的活动。 与[展示次数集合](/help/using/integration/media-data-integration/impression-data-pixels.md)类似，将事件调用发送到[!DNL Audience Manager]数据收集服务器([!DNL DCS])进行处理。 随后，访客将被重定向到预期网址。

>[!NOTE]
>
>请联系您的[!DNL Audience Manager]咨询或客户负责人，以获取特定于客户端域的具体[!DNL URL]。

## 要求

点击跟踪调用需要以下参数：

* `d_event=click`：将事件调用标识为点击事件的键值对。
* `d_rd=redirect URL`：包含双重编码重定向[!DNL URL]的键值对。 如果使用联机编码工具，请通过编码器运行字符串，然后再次对结果进行编码，以使重定向正常工作。

此外，调用可以包含键值对，这些键值对可用于特征资格或为其他报表提供数据和元数据。

## 请求示例

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 响应

响应将浏览器重定向到`d_rd`参数中指定的[!DNL URL]。 响应字符串可以包含由下面列出的任何受支持的宏生成的值。

基于以上示例，浏览器被重定向到以下[!DNL URL]：

`https://adobe.com/callback?creative=123`

## 支持的宏

单击事件支持下表列出的宏。 宏是自包含代码的一个小单元，在加载广告标记以进行营销活动和用户跟踪时激活。 宏将与目标[!DNL URL]一起传递，前提是它们使用以下格式进行标记： `%macro%`。 某些键没有宏，而是接受硬编码的ID值。 如果要分析[Audience Optimization报表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)中的数据，则需要接受硬编码值的键。

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
   <td colname="col2"> <p>广告服务器上的数值广告组ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>无宏。 </p> <p>接受硬编码的ID值。 </p> </td> 
   <td colname="col2"> <p>广告商ID。</p> <p>广告商数据源的集成代码。 请注意，这与Audience Manager数据源无关。</p> <p> <span class="wintitle">Audience Optimization</span>报告需要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>业务部门的数值ID。 </p> <p> <span class="wintitle">Audience Optimization</span>报告需要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>广告服务器的数字营销活动ID。 </p> <p> <span class="wintitle">Audience Optimization</span>报告需要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>广告服务器上的数字创意ID。 </p> <p>必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>数据提供程序ID。 </p> <p>通常与<code> d_dpuuid</code>一起使用将数据提供程序ID链接到用户ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>数据提供程序提供的唯一用户ID。 </p> <p>通常与<code> d_dpid</code>一起使用以将用户ID链接到数据提供程序ID。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword">Experience Cloud</span> ID (ECID)。 有关ECID的详细信息，请参阅<a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Experience CloudID</a>。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>广告服务器上的数字版面ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>为请求服务的DCS群集的数字区域ID。 有关DCS的详细信息，请参阅<a href="../../reference/system-components/components-data-collection.md">数据收集组件</a>。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>用于缓存失效的随机数。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>广告服务器上的数值网站ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>Audience Manager从中提取元数据的源的DPID。 </p> <p>必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>直接在URL中指定访客的ID，而不是依赖于Demdex Cookie。 </p> <p>可选。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p>与<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。 </p><p><code>gdpr</code> 可以为0（GDPR不适用）或1（GDPR适用）。</p> <p>默认值为 0。</p><p>可选。</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p>与<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p><p> 如果<code>gdpr=1</code>，则<code>${gdpr_consent_XXXX}</code>将被替换为字符串<code>gdpr_consent</code>和供应商ID（请参阅<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB规范</a>）。</p> <p>默认值为 0。</p><p>可选。</p></td> 
  </tr> 
 </tbody> 
</table>

## 宏示例

此示例演示了传递创意、广告组和放置宏。 它假定每个参数的值都在点击跟踪调用的非重定向部分中传递。

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

基于以上示例，浏览器被重定向到以下[!DNL URL]：

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## 其他功能 — [!UICONTROL Audience Optimization Reports]

您可以使用像素调用为[Audience Optimization报表](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md)供电。 如果要使用像素为报表供电，请参阅[元数据文件的概述和映射](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。


>[!MORELIKETHIS]
>
>* Audience Optimization报表的[数据和元数据文件](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)
