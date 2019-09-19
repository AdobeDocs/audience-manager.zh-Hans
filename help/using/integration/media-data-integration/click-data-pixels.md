---
description: 'null'
seo-description: 'null'
seo-title: 通过像素调用捕获营销活动点击数据
solution: Audience Manager
title: 通过像素调用捕获营销活动点击数据
uuid: 7c3797f7-9674-493d-972b-38be0584fede
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

点击跟踪可衡量整个营销活动中的访客参与度，因为它记录了第三方创意人员的基于点击的活动。 与印象收集类似，事件调用会发送到Audience manager数据收集服务器([!UICONTROL DCS])以进行处理。 然后，访客会被重定向到预期的Web地址。

## 要求

单击跟踪调用需要以下参数：

* `d_event=click`:将事件调用标识为单击事件的键值对。
* `d_rd=redirect URL`:包含编码重定向的键值对 [!DNL URL]。

此外，该调用可包含键值对，这些键值对可用于特征鉴定或为其他报告提供数据和元数据。

## 请求示例

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 响应

响应会将浏览器重定向到 [!DNL URL] 参数中指定的 `d_rd` 位置。 响应字符串可以包括由下列任何支持的宏生成的值。

根据上述示例，浏览器将被重定向到以下位置 [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=123`]

## 支持的宏

单击事件支持下表中列出的宏。 宏是自包含的小代码单元，加载广告标签时激活该代码以用于营销活动和用户跟踪。 只要用以下格式标记宏， [!DNL URL]宏就会与目标一起传递： `%macro%`. 某些键没有宏，而是接受硬编码ID值。 如果要分析受众优化报告中的数据，则需要接受硬编码值 [的键](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。

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
   <td colname="col02"> <p>无宏。 </p> <p>接受硬编码ID值。 </p> </td> 
   <td colname="col2"> <p>广告商 ID.</p> <p>广告商数据源的集成代码。 请注意，这与Audience manager数据源无关。</p> <p> 受众优化 <span class="wintitle"> 报告所需</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>业务单位的数字ID。 </p> <p> 受众优化 <span class="wintitle"> 报告所需</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>广告服务器中的数字系列活动ID。 </p> <p> 受众优化 <span class="wintitle"> 报告所需</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>广告服务器中的数字创意ID。 </p> <p>必需. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>数据提供者ID。 </p> <p>通常与 <code> d_dpuuid一起使用</code> ，将数据提供者ID链接到用户ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>数据提供者提供的唯一用户ID。 </p> <p>通常与 <code> d_dpid一起使用</code> ，将用户ID链接到数据提供者ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID (ECID). </span>For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>广告服务器中的数字放置ID。 </p> <p>可选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>为请求提供服务的DCS群集的数字区域ID。 有关DCS的详细信息，请参阅数 <a href="../../reference/system-components/components-data-collection.md"> 据收集组件</a>。 </p> <p>可选。 </p> </td> 
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
   <td colname="col2"> <p>Audience manager从中提取元数据的源的DPID。 </p> <p>必需. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>直接在URL中指定访客的ID，而不是依赖Demdex cookie。 </p> <p>可选。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_applies%</code> </p> </td> 
   <td colname="col2"> <p>与<a href="../../overview/aam-gdpr/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。 </p><p><code>gdpr</code> 可以是0（GDPR不适用）或1（GDPR适用）。</p> <p>默认值为 0。</p><p>可选。</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_connection</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_connection%</code> </p> </td> 
   <td colname="col2"> <p>与<a href="../../overview/aam-gdpr/aam-iab-plugin.md">适用于 IAB TCF 的 Audience Manager 插件</a>有关。</p><p> 如果 <code>gdpr=1</code>，则 <code>%gdpr_consent%</code> 将被替换为字符串 <code>gdpr_consent</code>（请参阅 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">IAB 规范</a>）。</p> <p>默认值为 0。</p><p>可选。</p></td> 
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
d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25%26campaign%3D%25d_campaign%25%26adgroup%3D%25
d_adgroup%25%26d_placement%3D%25placement%25%26src%3D%25d_src%25
```

## 响应

根据上述示例，浏览器将被重定向到以下位置 [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORE_LIKE_THIS]
>
>* [受众优化报告的数据和元数据文件](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

