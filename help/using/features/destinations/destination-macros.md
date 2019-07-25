---
description: 描述可添加到目标URL的宏。
seo-description: 描述可添加到目标URL的宏。
seo-title: 定义目标宏
solution: Audience Manager
title: 定义目标宏
uuid: 982cab05-8a3f-4f96-b4 d0-291709712ad1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Destination Macros Defined {#destination-macros-defined}

Describes the macros you can add to a destination [!DNL URL].

<!-- destination-macros.xml -->

When creating a [!DNL URL] destination, you can insert the following macros into the [!DNL URL] string. Check with your data/destination partner about proper macro placement within the destination [!DNL URL].

>[!NOTE]
>
>除非另有说明，否则宏是可选的。*斜体*&#x200B;表示变量占位符。

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 说明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> %alias%</code> </p> </td> 
   <td colname="col2"> <p>必需. </p> <p>定义目标URL中映射区段值的位置。Usually this is the <i>Segment ID</i>, but could also be the integration code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Inserts the user's <span class="keyword"> Audience Manager</span> ID into the destination URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpd_<i>data源id</i>%</code> </p> </td> 
   <td colname="col2"> <p><i>数据源ID</i> 对应于传入宏的数据源的标识符。 </p> <p>让我们来看一下简单示例。In this case, we have an <span class="keyword"> Audience Manager</span> partner with the following IDs and conditions: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">Data source ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">An internal customer ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">Declared ID: The partner wants to pass in these values as the declared ID <code> 1:CustomerABC</code>. </li> 
    </ul> <p>To do this with the <code>%dpid_<i>data source id</i>%</code>, the <span class="keyword"> Audience Manager</span> partner would format the macro like this: </p> 
    <ul class="simplelist"> 
     <li> <code> %dpd_1%</code> </li> 
    </ul> <p>The macro will replace <code> 1</code> with <code> CustomerABC</code>. </p> <p> 
     <draft-comment>
       基于AAM-22193 
     </draft-comment> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %http_ proto%</code> </p> </td> 
   <td colname="col2"> <p>检测父网页中使用的协议，并将其插入目标URL。For example: 
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">if the webpage is <b>https</b>://aam_client.com, this macro will be replaced with <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">if the webpage is <b>http</b>://aam_client.com, this macro will be replaced with <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Inserts the <span class="keyword"> Experience Cloud</span> ID into the destination URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %区域%</code> </p> </td> 
   <td colname="col2"> <p>Inserts the <span class="wintitle"> Data Collection Server (DCS)</span> region into the destination URL. In order to minimize latency, when the visitor makes an HTTP call to <span class="keyword"> Audience Manager</span>, they are being redirected to the closest <span class="wintitle"> DCS</span> datacenter. 这是通过DNS实现的，它能够检测访客的位置并将它们引导到相应的dataenter。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>通过在目标URL中插入随机号码来执行缓存中断功能。这可防止浏览器提供缓存的内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>将UNIX时间戳插入目标URL以防止浏览器提供缓存的内容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cache Busting with Destination Macros {#destination-cache-busting}

`%rnd%``%timestamp%` 和宏在 [!DNL URL] 字符串中插入唯一值以防止浏览器缓存。

## Cache Busting with `%rnd%` and `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

浏览器在内存中缓存(保存)经常请求的内容。页面加载时，保存的内容将从缓存而非远程服务器服务。此过程有助于保持有效下载时间，因为数据在本地而非从其他位置服务。但是，由于缓存不需要服务器调用，因此可以通过人为降低唯一请求的数量来倾斜报表。

缓存中断可防止浏览器保存和重用内容。此技术使用将随机数字或时间戳插入URL字符串的代码，这使它看起来就像浏览器一样。As a result, each `HTTP` call is counted as a separate request to the server. 为每个请求强制调用新的服务器调用有助于保持报表准确性并减少错误。[!DNL Audience Manager] 提供了两个用于缓存的宏：

* `%rnd%`：将随机号码插入URL。
* `%timestamp%`：将Unix日期/时间插入URL。

## Comparing `%rnd%` and `%timestamp%` {#compare-rnd-timestamp}

Both macros prevent caching, but `%rnd%` may be more efficient. For example, with `%timestamp%`, if several users view a page simultaneously they'll get the same date/time value. As a result, the [!DNL URL] is not unique and multiple calls are counted only once. However, `%rnd%` generates a unique numeric value for each call (even when users see the same page simultaneously). This means the [!DNL URL] string contains different values and is counted as unique.

>[!MORE_ LIKE_ This]
>
>* [定义目标宏](../../features/destinations/destination-macros.md#destination-macros-defined)