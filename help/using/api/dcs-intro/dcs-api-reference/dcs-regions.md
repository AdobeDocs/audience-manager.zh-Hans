---
description: 对DCS进行调用时需要区域DCS服务器主机名。 这是因为DCS在地理上与站点访客较近的数据中心中存储信息。 如果将查询发送到错误的DCS，则查询将有效，但这些调用效率低下，可能会延迟响应。 要发出DCS请求，请将区域ID与其相应的区域主机名匹配，并使用正确的主机名构建查询。
seo-description: 对DCS进行调用时需要区域DCS服务器主机名。 这是因为DCS在地理上与站点访客较近的数据中心中存储信息。 如果将查询发送到错误的DCS，则查询将有效，但这些调用效率低下，可能会延迟响应。 要发出DCS请求，请将区域ID与其相应的区域主机名匹配，并使用正确的主机名构建查询。
seo-title: DCS 区域 ID、位置和主机名
solution: Audience Manager
title: DCS 区域 ID、位置和主机名
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
exl-id: 9b12946c-89f1-4f6f-adb9-961e15a0b816
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 9%

---

# DCS 区域 ID、位置和主机名 {#dcs-region-ids-locations-and-host-names}

对[!DNL DCS]进行调用时需要区域[!DNL DCS]服务器主机名。 这是因为[!DNL DCS]在地理上与站点访客接近的数据中心中存储信息。 如果将查询发送到错误的[!DNL DCS]，则查询将有效，但这些调用效率低下，可能会延迟响应。 要发出[!DNL DCS]请求，请将区域ID与其相应的区域主机名匹配，并使用正确的主机名构建查询。

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
   <td colname="col2"> <p>欧洲（爱尔兰都柏林） </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>美国东部（弗吉尼亚，美国） </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>南太平洋/大洋洲（悉尼，澳大利亚） </p> </td> 
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
