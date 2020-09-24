---
description: 描述可添加到目标URL的宏。
seo-description: 描述可添加到目标URL的宏。
seo-title: 定义的目标宏
solution: Audience Manager
title: 定义的目标宏
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 4bf32099e964c421d943d9925c74dd0d4d6ee576
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 2%

---


# 定义的目标宏 {#destination-macros-defined}

描述可添加到目标的宏 [!DNL URL]。

<!-- destination-macros.xml -->

创建目标 [!DNL URL] 时，可以在字符串中插入以下 [!DNL URL] 宏。 请咨询您的数据／目标合作伙伴，了解在目标中的宏位置 [!DNL URL]。

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
   <td colname="col2"> <p>必需. </p> <p>定义目标URL中映射的段值的位置。 通常，这是 <i>段ID</i>，但也可能是集成代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>将用户的 <span class="keyword"> Audience Manager</span> ID插入目标URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>数 <i>据源</i> id与传入宏的数据源的标识符相对应。 </p> <p>让我们通过一个简单的示例来看看它是如何工作的。 在这种情况下，我们有一个 <span class="keyword"> Audience Manager</span> 合作伙伴，其ID和条件如下： </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">数据源ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">内部客户ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">声明的ID:合作伙伴希望将这些值作为声明的ID进行传递 <code> 1:CustomerABC</code>。 </li> 
    </ul> <p>为此，Audience Manager <code>%dpid_<i>data source id</i>%</code>合作伙 <span class="keyword"> 伴将</span> 如下格式化宏： </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>宏将替换 <code> 1</code> 为 <code> CustomerABC</code>。 </p> <p> 
     <!--
       Based on AAM-22193 https://jira.corp.adobe.com/browse/AAM-22193 
     --> </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>指示GDPR法规是否适用于访客。 使用此宏将同意包含在发送到与IAB集成的URL目标的区段中。 有关 <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">详细信息，请参阅IAB TCF的Audience Manager</a> 插件。</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>当访客在您的站点上提供或拒绝同意时收集的同意字符串（包括IAB供应商ID）。 使用此宏可在发送到与IAB集成的URL目标的区段中包含同意字符串。 替换为 <code>XXXX</code> 目标合作伙伴ID。 有关 <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">详细信息，请参阅IAB TCF的Audience Manager</a> 插件。 </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>检测父网页中使用的协议并将其插入到目标URL中。 For example:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">如果网页为 <b>https</b>://aam_client.com，则此宏将替换为 <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">如果网页 <b>为http</b>://aam_client.com，则此宏将替换为 <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>将Experience Cloud <span class="keyword"> ID</span> 插入目标URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>将数据收集 <span class="wintitle"> 服务器(DCS)区域插入</span> 到目标URL中。 为了最大限度地减少延迟，当访客对Audience Manager进行HTTP调 <span class="keyword"> 用</span>时，会将其重定向到最接近的 <span class="wintitle"> DCS</span> 。 这是通过DNS实现的，DNS能够检测访客的位置并将其定向到适当的数据中心。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>通过在目标URL中插入随机数来执行缓存破坏功能。 这会阻止浏览器提供缓存的内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>将UNIX时间戳插入目标URL，以阻止浏览器提供缓存内容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用目标宏缓存破坏 {#destination-cache-busting}

宏和 `%rnd%` 宏 `%timestamp%` 将唯一值插入字符串以 [!DNL URL] 防止浏览器缓存。

## 缓存Busting（%rnd%和%timestamp%） {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

浏览器在内存中缓存（保存）频繁请求的内容。 载入页面时，保存的内容将从缓存而非远程服务器提供服务。 此过程有助于保持有效的下载时间，因为数据是本地提供的，而不是从其他位置提供的。 但是，由于缓存不需要服务器调用，因此它可以通过人为降低唯一请求数来歪斜报告。

缓存破坏功能可防止浏览器保存和重复使用内容。 此技术使用将随机数或时间戳插入URL字符串的代码，这使它对浏览器来说是独一无二的。 因此，每个调 `HTTP` 用被计为对服务器的单独请求。 强制对每个请求进行新的服务器调用有助于保持报告准确性并减少差异。 [!DNL Audience Manager] 为缓存缓冲区提供两个宏：

* `%rnd%`:在URL中插入随机数。
* `%timestamp%`:将Unix日期／时间插入URL。

## 比较%rnd%和%timestamp% {#compare-rnd-timestamp}

这两个宏都会阻止缓存， `%rnd%` 但可能更高效。 例如，如果 `%timestamp%`多个用户同时视图页面，他们将获得相同的日期／时间值。 因此，该调用不 [!DNL URL] 是唯一的，并且只计数一次多次调用。 但是， `%rnd%` 为每个调用生成一个唯一的数值（即使用户同时看到同一页面）。 这表示该字 [!DNL URL] 符串包含不同的值，并被计为唯一值。

>[!MORELIKETHIS]
>
>* [定义的目标宏](../../features/destinations/destination-macros.md#destination-macros-defined)