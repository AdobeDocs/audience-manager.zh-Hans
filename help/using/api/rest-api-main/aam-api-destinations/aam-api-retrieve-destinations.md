---
description: 返回指定的destinationID目标的GET方法。
seo-description: 返回指定的destinationID目标的GET方法。
seo-title: 按目标ID返回目标
solution: Audience Manager
title: 按目标ID返回目标
uuid: abe7426-55a5-4045-93a7-0487652a7189
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Return A Destination by Destination ID {#return-a-destination-by-destination-id}

`GET` 返回指定 `destinationId`的目标的方法。

<!-- r_get_all_destinations_order_id.xml -->

## 请求

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>To populate the `mappings` field pass in `includeMappings=true` in the URL.

## 响应

```
{
   "destinationType":"PUSH",
   "destinationId":314,
   "dataSourceId":null,
   "pid":1099,
   "name":"sample destination",
   "description":"Turn",
   "startDate":null,
   "endDate":null,
   "status":"active",
   "destinationType":"PUSH",
   "createTime":1281997484000,
   "updateTime":1300752888000,
   "crUID":224,
   "upUID":308,
   "domainRestrictions":"ALL_DOMAINS",
   "tagType":0,
   "serializationEnabled":false,
   "urlFormatString":null,
   "secureUrlFormatString":null,
   "delimiter":null,
   "mappings":null
}
```

## Return All Destinations {#return-all-destinations}

A `GET` method that returns all destinations for the specified partner.

<!-- r_get_all_destinations.xml -->

### 请求

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *(可选)* 传入以 `containsSegment=<sid>` 返回映射到指定区段的所有目标的数组。For example, your query could look similar to this: `GET .../destinations/?containsSegment=4321`.
   >
   >
* 不返回完整目标对象。如果需要完全填充对象，则按数据顺序获取目标。


### 可选查询参数

You can use these optional parameters with API methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. See [Optional Parameters](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th>
   <th colname="col2" class="entry"> 描述 </th>
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td>
   <td colname="col2"> 按页码返回结果。编号从开始开始。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> 设置请求返回的响应结果数(默认为10)。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> SortBy</code> </td>
   <td colname="col2">Sorts and returns results according to the specified <span class="keyword"> JSON</span> property. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> 降序</code> </td>
   <td colname="col2"> 按降序排序并返回结果。默认为升序。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">返回基于要用作搜索参数的指定字符串的结果。例如，假设您要查找在该项目的任何值字段中具有“测试”字样的所有模型的结果。您的示例请求可能如下所示： <p><code> GET</code>Social。 </p> <p>您可以搜索由“get all”方法返回的任何值。 </p> </td>
  </tr>
 </tbody>
</table>

### 响应

```
[
   {
      "destinationId":364,
      "pid":1099,
      "name":"Test",
      "description":"",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1291345192000,
      "updateTime":1291347561000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   },
   {
      "destinationId":369,
      "pid":1099,
      "name":"sample destination",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1292631706000,
      "updateTime":1292631706000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   }
]
```

## Return a Destination Mapping With the Mapping ID {#return-dest-mapping-id}

A `GET` method that returns an individual destination mapping based on the `mappingId`.

<!-- r_get_destination_trait_data_order.xml -->

### 请求

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`*`<destinationMappingId>`*

### 响应

```
{
"mappingId": 14593,
"traitType": "SEGMENT",
"traitValue": 0,
"destinationId": 314,
"elementName": "sample",
"elementDescription": "Migration Pixel",
"elementStatus": "active",
"createTime": 1281997484000,
"updateTime": 1300752888000,
"crUID": 224,
"upUID": 308,
"sid": 80920,
"startDate": "2010-11-15",
"endDate": null,
"priority": null,
"url": "https://www.adobe.com/send?%ALIAS%",
"secureUrl": "https://www.adobe.com/send?%ALIAS%",
"tagCode": null,
"secureTagCode": null,
"traitAlias": null
}
```

## Return Destination Mappings {#return-dest-mappings}

A `GET` method that returns the mappings for a destination.

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>返回的映射特定于目标类型和配置。

### 请求

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings`

>[!NOTE]
>
>支持分页参数。

### 响应

```
{
   "total":354,
   "page":0,
   "pageSize":2,
   "list":[
      {
         "destinationMappingId":14395,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":224,
         "upUID":308,
         "sid":80920,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
      {
         "destinationMappingId":15934,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":242,
         "upUID":803,
         "sid":90820,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
   ]
{
```

## Return All Available Destination Platforms {#return-dest-platforms}

A `GET` method that returns all available device platforms for destinations.

<!-- r_get_dest_platforms.xml -->

### 请求

`GET /destinations/configurations/available-platforms/`

### 响应

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## Return S2S and Bulk S2S Destination Job History {#return-job-history}

`GET` 返回出站 [!UICONTROL Server-to-Server] ( [!UICONTROL S2S])和批量 [!UICONTROL S2S] 目标作业历史记录信息的方法。

<!-- r_get_job_history.xml -->

### 请求

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Required query parameters: `startDate` = *&lt;`epochtime`&gt;* and `endDate` = *&lt;`epochtime`&gt;*.

### 响应

```
[
{
      "pushID":34090,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337292466000,
      "endTime":1337292466000,
      "dataFileName":"ftp_655_269_iter_1337229891903.sync",
      "success":true
   },
   {
      "pushID":34104,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337346397000,
      "endTime":1337346397000,
      "dataFileName":"ftp_655_269_iter_1337285714581.sync",
      "success":true
   },
   {
      "pushID":34124,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337396811000,
      "endTime":1337396812000,
      "dataFileName":"ftp_655_269_iter_1337338243600.sync",
      "success":true
   }
]
```
