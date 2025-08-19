---
description: 描述可添加到目标URL的宏。
seo-description: Describes the macros you can add to a destination URL.
seo-title: Destination Macros Defined
solution: Audience Manager
title: 定义的目标宏
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
exl-id: 7be4b417-046c-4fe3-a53c-e4e0ed36acb9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 1%

---

# 定义的目标宏 {#destination-macros-defined}

描述可添加到目标[!DNL URL]的宏。

<!-- destination-macros.xml -->

创建[!DNL URL]目标时，可以将以下宏插入到[!DNL URL]字符串中。 请与您的数据/目标合作伙伴联系，了解宏在目标[!DNL URL]中的正确放置方式。

>[!NOTE]
>
>除非另有说明，否则宏是可选的。 *斜体*&#x200B;表示变量占位符。

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
   <td colname="col2"> <p>必需。 </p> <p>定义映射的区段值在目标URL中的位置。 这通常是<i>区段ID</i>，但也可能是集成代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>将用户的<span class="keyword"> Audience Manager</span> ID插入到目标URL中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p><i>数据源ID</i>对应于传递到宏的数据源的标识符。 </p> <p>让我们通过一个简单的示例来了解一下它的工作方式。 在这种情况下，我们有一个<span class="keyword">Audience Manager</span>合作伙伴，该合作伙伴具有以下ID和条件： </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">数据源ID： <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">内部客户ID： <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">声明的ID：合作伙伴希望将这些值作为声明的ID <code> 1:CustomerABC</code>传入。 </li> 
    </ul> <p>要对<code>%dpid_<i>data source id</i>%</code>执行此操作，<span class="keyword"> Audience Manager</span>合作伙伴将如下设置宏的格式： </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>宏会将<code> 1</code>替换为<code> CustomerABC</code>。 </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>指示GDPR法规是否适用于访客。 使用此宏可在发送到与IAB集成的URL目标的区段中包含同意。 有关详细信息，请参阅适用于IAB TCF的<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager插件</a>。</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>访客在您的网站上提供或拒绝同意时收集的同意字符串（包括IAB供应商ID）。 使用此宏可在发送到与IAB集成的URL目标的区段中包含同意字符串。 将<code>XXXX</code>替换为目标合作伙伴ID。 有关详细信息，请参阅适用于IAB TCF的<a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager插件</a>。 </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>检测父网页中使用的协议，并将其插入到目标URL中。 例如：
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">如果网页为<b>https</b>：//aam_client.com，则此宏将被替换为<b>https</b>：//url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">如果网页为<b>http</b>：//aam_client.com，则此宏将被替换为<b>http</b>：//url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>将<span class="keyword"> Experience Cloud</span> ID插入到目标URL中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>将<span class="wintitle">数据收集服务器(DCS)</span>区域插入到目标URL中。 为了最大限度地减少延迟，当访客对<span class="keyword"> Audience Manager</span>进行HTTP调用时，他们将被重定向到最近的<span class="wintitle"> DCS</span>数据中心。 这可以通过DNS实现，DNS能够检测访客的位置并将他们定向到适当的数据中心。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>通过在目标URL中插入随机数来执行缓存失效功能。 这样可防止浏览器提供缓存的内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>将UNIX时间戳插入到目标URL中，以防止浏览器提供缓存的内容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用目标宏进行缓存破坏 {#destination-cache-busting}

`%rnd%`和`%timestamp%`宏将唯一值插入到[!DNL URL]字符串中，以防止浏览器缓存。

## 与`%rnd%`和`%timestamp%`的缓存无效 {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

浏览器在内存中缓存（保存）频繁请求的内容。 加载页面时，保存的内容从缓存中提供，而不是从远程服务器提供。 此过程有助于保持高效的下载时间，因为数据是在本地提供的，而不是从其他位置提供。 但是，由于缓存不需要服务器调用，因此它可能会通过人为减少唯一请求数来扭曲报表。

缓存无效会阻止浏览器保存和重用内容。 此技术使用的代码会在URL字符串中插入随机数字或时间戳，这样在浏览器中看起来是唯一的。 因此，每个`HTTP`调用都计为对服务器的单独请求。 为每个请求强制执行新的服务器调用有助于保持报告准确性并减少差异。 [!DNL Audience Manager]为缓存无效提供两个宏：

* `%rnd%`：在URL中插入随机数。
* `%timestamp%`：将Unix日期/时间插入到URL中。

## 正在比较`%rnd%`和`%timestamp%` {#compare-rnd-timestamp}

这两个宏都阻止缓存，但`%rnd%`可能更有效。 例如，使用`%timestamp%`，如果多个用户同时查看一个页面，他们将获得相同的日期/时间值。 因此，[!DNL URL]不是唯一的，多个调用只被计数一次。 但是，`%rnd%`为每个调用生成一个唯一的数值（即使用户同时看到同一页面）。 这意味着[!DNL URL]字符串包含不同的值并计为唯一的。

>[!MORELIKETHIS]
>
>* [定义的目标宏](../../features/destinations/destination-macros.md#destination-macros-defined)
