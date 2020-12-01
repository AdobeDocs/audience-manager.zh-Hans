---
description: 对DCS进行调用时，需要使用区域DCS服务器主机名。 这是因为DCS将信息存储在地理位置接近站点访客的数据中心中。 如果将查询发送到错误的DCS，则这些调用将正常工作，但这些调用效率低下，可能会延迟响应。 要发出DCS请求，请将区域ID与其相应的区域主机名匹配，并使用正确的主机名组成查询。
seo-description: 对DCS进行调用时，需要使用区域DCS服务器主机名。 这是因为DCS将信息存储在地理位置接近站点访客的数据中心中。 如果将查询发送到错误的DCS，则这些调用将正常工作，但这些调用效率低下，可能会延迟响应。 要发出DCS请求，请将区域ID与其相应的区域主机名匹配，并使用正确的主机名组成查询。
seo-title: DCS 区域 ID、位置和主机名
solution: Audience Manager
title: DCS 区域 ID、位置和主机名
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 9%

---


# DCS 区域 ID、位置和主机名 {#dcs-region-ids-locations-and-host-names}

对[!DNL DCS]进行调用时，区域[!DNL DCS]服务器主机名是必需的。 这是因为[!DNL DCS]在地理上接近站点访客的数据中心中存储信息。 如果将查询发送到错误的[!DNL DCS]，则这些调用将正常工作，但这些调用效率低下，可能会延迟响应。 要发出[!DNL DCS]请求，请将区域ID与其相应的区域主机名匹配，并用正确的主机名组成查询。

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS区域ID(dcs_region) </th> 
   <th colname="col2" class="entry"> 区域（和位置） </th> 
   <th colname="col3" class="entry"> 主机名 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID3 </p> </td> 
   <td colname="col2"> <p>东南亚（新加坡） </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID4 </p> </td> 
   <td colname="col2"> <p>南美洲（巴西圣保罗） </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID6 </p> </td> 
   <td colname="col2"> <p>欧洲（都柏林、爱尔兰） </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>美国东部（美国弗吉尼亚州） </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>南太平洋／大洋洲（澳大利亚悉尼） </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>美国西部（俄勒冈州，美国） </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>亚洲（日本东京） </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>印度 </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

您还可以使用[!DNL API]方法获取可用[!DNL DCS]区域的列表。 请参阅[DCS区域API方法](../../../api/rest-api-main/aam-api-dcs-regions.md)。