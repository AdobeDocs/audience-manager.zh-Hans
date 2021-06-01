---
description: 一种GET方法，用于返回指定destinationId的目标。
seo-description: 一种GET方法，用于返回指定destinationId的目标。
seo-title: 按目标 ID 返回目标
solution: Audience Manager
title: 按目标 ID 返回目标
uuid: abce7426-55a5-4045-93a7-0487652a7189
feature: API
exl-id: c0850e71-7830-4635-b773-e9a28ab5bd68
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 9%

---

# 按目标 ID 返回目标 {#return-a-destination-by-destination-id}

`GET`方法，返回指定`destinationId`的目标。

<!-- r_get_all_destinations_order_id.xml -->

## 请求

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>要在URL中填充`mappings`字段，请传入`includeMappings=true`。

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

## 返回所有目标{#return-all-destinations}

`GET`方法，可返回指定合作伙伴的所有目标。

<!-- r_get_all_destinations.xml -->

### 请求

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *（可选）* 传入 `containsSegment=<sid>` ，以返回映射到指定区段的所有目标的数组。例如，您的查询可能类似于以下内容：`GET .../destinations/?containsSegment=4321`。
   >
   >
* 不返回完整的目标对象。 如果需要完全填充的对象，请按数据顺序获取目标。


### 可选查询参数

您可以将这些可选参数与返回对象&#x200B;*所有*&#x200B;属性的API方法结合使用。 将查询传递到[!DNL API]时，在请求字符串中设置这些选项。 请参阅[可选参数](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)。

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
   <td colname="col2"> 按页码返回结果。 编号从0开始。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> 设置请求返回的响应结果数（默认为10）。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td>
   <td colname="col2">根据指定的<span class="keyword"> JSON</span>属性对结果进行排序和返回。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 按降序排序和返回结果。 默认为升序。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">根据要用作搜索参数的指定字符串返回结果。 例如，假设您希望在该项目的任何值字段中查找包含“Test”字样的所有模型的结果。 您的示例请求可能如下所示： <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>. </p> <p>您可以搜索“get all”方法返回的任何值。 </p> </td>
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

## 返回映射ID为{#return-dest-mapping-id}的目标映射

一种`GET`方法，用于根据`mappingId`返回单个目标映射。

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

## 返回目标映射{#return-dest-mappings}

返回目标映射的`GET`方法。

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

## 返回所有可用的目标平台{#return-dest-platforms}

`GET`方法，可返回目标的所有可用设备平台。

<!-- r_get_dest_platforms.xml -->

### 请求

`GET /destinations/configurations/available-platforms/`

### 响应

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## 返回S2S和批量S2S目标作业历史记录{#return-job-history}

一种`GET`方法，可返回出站[!UICONTROL Server-to-Server]([!UICONTROL S2S])和批量[!UICONTROL S2S]目标作业历史记录信息。

<!-- r_get_job_history.xml -->

### 请求

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

必需的查询参数：`startDate` = *`epochtime`>*&#x200B;和`endDate` = *`epochtime`>*。

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
