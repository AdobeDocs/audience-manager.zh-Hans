---
description: 'null'
seo-description: 'null'
seo-title: 通过像素调用捕获Campaign单击数据
solution: Audience Manager
title: 通过像素调用捕获Campaign单击数据
uuid: 7c3797f7-9674-493d-972b-38be0584feide
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

点击跟踪可衡量整个营销活动中的访客参与度，因为它为第三方创意人员记录基于点击的活动。与展示集合类似，活动调用会发送到Audience Manager数据收集服务器([!UICONTROL DCS])以进行处理。然后将访客重定向到预期的Web地址。

## 要求

单击跟踪调用需要以下参数：

* `d_event=click`：将事件调用标识为单击事件的键值对。
* `d_rd=redirect URL`：包含编码重定向 [!DNL URL]的键值对。

此外，该调用还可以包含可用于特征资格限定或为其他报表提供数据和元数据的键值对。

## 请求示例

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 响应

响应将浏览器重定向到参数 [!DNL URL] 中指定 `d_rd` 的位置。响应字符串可包括以下任何支持的宏生成的值。

根据以上示例，浏览器将重定向到以下内容 [!DNL URL]：

[!DNL `https://adobe.com/callback?creative=123`]

## 支持的宏

单击事件支持下表所列的宏。宏是一个小型的自助代码单元，它在加载营销活动和用户跟踪的广告标记加载时激活。宏将与目标 [!DNL URL]一起传递，只要标记采用以下格式： `%macro%`。一些键没有宏，而是接受硬编码的ID值。如果您希望在 [受众优化报告中分析数据，则接受硬编码值的键是必需的](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。

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
   <td colname="col1"> <p> <code> d_ adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ adgroup%d</code> </p> </td> 
   <td colname="col2"> <p>广告服务器中的数字广告组ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsrc</code> </p> </td> 
   <td colname="col02"> <p>无宏。 </p> <p>接受硬编码的ID值。 </p> </td> 
   <td colname="col2"> <p>广告商 ID.</p> <p>广告商的数据源的集成代码。请注意，这与Audience Manager数据源无关。</p> <p> <span class="wintitle"> 受众优化</span> 报告所必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ bu%</code> </p> </td> 
   <td colname="col2"> <p>业务单位的数字ID。 </p> <p> <span class="wintitle"> 受众优化</span> 报告所必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ campaign%</code> </p> </td> 
   <td colname="col2"> <p>广告服务器中的数字系列活动ID。 </p> <p> <span class="wintitle"> 受众优化</span> 报告所必需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ creative%</code> </p> </td> 
   <td colname="col2"> <p>广告服务器中的数字创意ID。 </p> <p>必需. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ id%</code> </p> </td> 
   <td colname="col2"> <p>数据提供者ID。 </p> <p>经常与 <code> d_ dpuuid</code> 一起使用，将数据提供程序ID链接到用户ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ dpuid%d</code> </p> </td> 
   <td colname="col2"> <p>由数据提供者提供的唯一用户ID。 </p> <p>经常与 <code> d_ dpid</code> 一起使用，将用户ID链接到数据提供者ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID (ECID). </span>For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ placement%d</code> </p> </td> 
   <td colname="col2"> <p>广告服务器中的数字放置ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_地区</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_地区%d_</code> </p> </td> 
   <td colname="col2"> <p>服务请求的DCS群集的数字区域ID。有关DCS的详细信息，请参阅 <a href="../../reference/system-components/components-data-collection.md"> 数据收集组件</a>。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_ rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_ rand</code> </p> </td> 
   <td colname="col2"> <p>用于缓存中断的随机数。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ site%d</code> </p> </td> 
   <td colname="col2"> <p>广告服务器中的数字站点ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ src%</code> </p> </td> 
   <td colname="col2"> <p>从Audience Manager提取元数据的源的DPID。 </p> <p>必需. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ uuid%</code> </p> </td> 
   <td colname="col2"> <p>直接在URL中指定访客的ID，而不是依赖Dedex cookie。 </p> <p>可选。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_ apply%</code> </p> </td> 
   <td colname="col2"> <p>与<a href="../../overview/aam-gdpr/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。 </p><p><code>gdpr</code> can be0(GDPR does not apply) or1(GDPR apply).</p> <p>默认值为 0。</p><p>可选。</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_ reagencement</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_ supagement%</code> </p> </td> 
   <td colname="col2"> <p>与<a href="../../overview/aam-gdpr/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p><p> 如果 <code>gdpr=1</code>，则 <code>%gdpr_consent%</code> 将被替换为字符串 <code>gdpr_consent</code>（请参阅 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">IAB 规范</a>）。</p> <p>默认值为 0。</p><p>可选。</p></td> 
  </tr> 
 </tbody> 
</table>

## Macromedia示例

此示例演示了如何通过创意、组和放置宏。它假定每个参数的值都传递在单击跟踪调用的非重定向部分中。

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> placation=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## 请求

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25%26campaign%3D%25d_campaign%25%26adgroup%3D%25
d_adgroup%25%26d_placement%3D%25placement%25%26src%3D%25d_src%25
```

## 响应

根据以上示例，浏览器将重定向到以下内容 [!DNL URL]：

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORE_ LIKE_ This]
>
>* [用于受众优化报告的数据和元数据文件](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

