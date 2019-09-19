---
description: 描述可添加到目标URL的宏。
seo-description: 描述可添加到目标URL的宏。
seo-title: 定义的目标宏
solution: Audience Manager
title: 定义的目标宏
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 定义的目标宏 {#destination-macros-defined}

描述可添加到目标的宏 [!DNL URL]。

<!-- destination-macros.xml -->

创建目标 [!DNL URL] 时，可以在字符串中插入以下 [!DNL URL] 宏。 请咨询您的数据／目标合作伙伴，了解目标中的宏位置 [!DNL URL]。

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
   <td colname="col2"> <p>必需. </p> <p>定义映射的区段值在目标URL中的位置。 通常，这是区 <i>段ID</i>，但也可能是集成代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>将用户的 <span class="keyword"> Audience Manager</span> ID插入目标URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>数 <i>据源ID</i> ，对应于传递到宏的数据源的标识符。 </p> <p>让我们通过一个简单的示例来看看它是如何工作的。 在这种情况下，我们有一个 <span class="keyword"> Audience Manager合作伙伴</span> ，其ID和条件如下： </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">数据源ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">内部客户ID:客 <code> 户ABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">声明的ID:合作伙伴希望将这些值作为声明的ID <code> 1:CustomerABC传递</code>。 </li> 
    </ul> <p>要使用%dpid_ <code>data source id<i>%</i>,</code><span class="keyword"></span> Audience Manager合作伙伴将如下格式化宏： </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>宏将用CustomerABC取 <code> 代</code> 1 <code> 。</code> </p> <p> 
     <draft-comment>
       基于AAM-22193 https://jira.corp.adobe.com/browse/AAM-22193 
     </draft-comment> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>检测在父网页中使用的协议，并将其插入到目标URL中。 For example: 
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">如果网页是 <b>https</b>://aam_client.com，则此宏将替换为 <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">如果网页是 <b>http</b>://aam_client.com，则此宏将替换为 <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>将 <span class="keyword"> Experience Cloud</span> ID插入目标URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>将数据收集 <span class="wintitle"> 服务器(DCS)区域插入到目标URL</span> 中。 为了最大限度地减少延迟，当访客对 <span class="keyword"> Audience Manager进行HTTP调用时</span>，会将其重定向到最接近的 <span class="wintitle"></span> DCS数据中心。 这是通过DNS实现的，DNS能够检测访客的位置并将访客定向到相应的数据中心。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>通过在目标URL中插入随机数来执行缓存破坏功能。 这会阻止浏览器提供缓存内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>在目标URL中插入UNIX时间戳，以防止浏览器提供缓存内容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用目标宏缓存破坏 {#destination-cache-busting}

宏和 `%rnd%` 宏 `%timestamp%` 将唯一值插入字符串以 [!DNL URL] 防止浏览器缓存。

## 缓存破坏( `%rnd%` 和) `%timestamp%`{#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

浏览器在内存中缓存（保存）经常请求的内容。 当页面加载时，保存的内容从缓存而不是从远程服务器提供服务。 此过程有助于保持有效的下载时间，因为数据是本地提供的，而不是从其他位置提供。 但是，由于缓存不需要服务器调用，它可以通过人为降低唯一请求数来歪斜报告。

缓存破坏阻止浏览器保存和重用内容。 此技术使用的代码将随机数或时间戳插入URL字符串中，这使其对浏览器而言是独一无二的。 因此，每个调 `HTTP` 用被计为对服务器的单独请求。 强制对每个请求进行新的服务器调用有助于保持报告的准确性并减少差异。 [!DNL Audience Manager] 为缓存破坏提供两个宏：

* `%rnd%`:在URL中插入随机数。
* `%timestamp%`:将Unix日期／时间插入URL。

## 比较 `%rnd%` 和比 `%timestamp%` 较 {#compare-rnd-timestamp}

这两个宏都会阻止缓存，但 `%rnd%` 可能会更有效。 例如，如果 `%timestamp%`多个用户同时查看页面，他们将获得相同的日期／时间值。 因此，该调用不 [!DNL URL] 是唯一的，并且只计数一次多次调用。 但是， `%rnd%` 每次调用都会生成一个唯一的数字值（即使用户同时看到同一页面）。 这表示该字 [!DNL URL] 符串包含不同的值，并被计为唯一值。

>[!MORE_LIKE_THIS]
>
>* [定义的目标宏](../../features/destinations/destination-macros.md#destination-macros-defined)