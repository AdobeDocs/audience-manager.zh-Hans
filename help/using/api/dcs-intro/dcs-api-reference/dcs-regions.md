---
description: 需要使用区域DCS服务器主机名才能调用DCS。这是因为DCS存储在地理位置接近站点访客的数据中心中的信息。如果您将其发送到错误的DCS，则您的查询将工作，但这些调用效率低下，并且可能会延迟响应。要发出DCS请求，请将区域ID与相应的区域主机名匹配，并使用适当的主机名构成查询。
seo-description: 需要使用区域DCS服务器主机名才能调用DCS。这是因为DCS存储在地理位置接近站点访客的数据中心中的信息。如果您将其发送到错误的DCS，则您的查询将工作，但这些调用效率低下，并且可能会延迟响应。要发出DCS请求，请将区域ID与相应的区域主机名匹配，并使用适当的主机名构成查询。
seo-title: DCS区域ID、位置和主机名
solution: Audience Manager
title: DCS区域ID、位置和主机名
uuid: ad150ffe-4583-472b-ac8 b-fb900 a7966 e4
translation-type: tm+mt
source-git-commit: 51a326d0ac02175e0e1452e0a00b4a3a415d88ff

---


# DCS Region IDs, Locations, and Host Names {#dcs-region-ids-locations-and-host-names}

The regional [!UICONTROL DCS] server host name is required to make calls to the [!UICONTROL DCS]. This is because the [!UICONTROL DCS] stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong [!UICONTROL DCS], but these calls are inefficient and can delay the response. To make a [!UICONTROL DCS] request, match the region ID to its corresponding regional host name and form your query with the proper host name.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS区域ID(cs_地区) </th> 
   <th colname="col2" class="entry"> 区域(和位置) </th> 
   <th colname="col3" class="entry"> 主机名 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID3 </p> </td> 
   <td colname="col2"> <p>东南亚(新加坡) </p> </td> 
   <td colname="col3"> <p> <code> apse. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID4 </p> </td> 
   <td colname="col2"> <p>南美洲(圣何塞圣保罗) </p> </td> 
   <td colname="col3"> <p> <code> sae. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID6 </p> </td> 
   <td colname="col2"> <p>欧洲(都柏林、爱尔兰) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>美国东部(弗吉尼亚州) </p> </td> 
   <td colname="col3"> <p> <code> use. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>南太平洋/渥太华(澳大利亚悉尼) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>美国西部(俄勒冈州) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>亚洲(东京、日本) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex. net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>印度 </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex. net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

You can also use [!DNL API] methods to get a list of the available [!UICONTROL DCS] regions. See [DCS Region API Methods](../../../api/rest-api-main/aam-api-dcs-regions.md).