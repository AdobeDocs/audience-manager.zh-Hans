---
description: 使用這些RESTful API方法將區段對應至目的地。
seo-description: Map segments to destinations with these RESTful API methods.
seo-title: Map Segments to a Destination
solution: Audience Manager
title: 将区段映射到目标
uuid: 35358ace-3082-4e86-a6eb-d77281af6d7e
feature: API
exl-id: 906df6c5-f878-48e6-a804-eb5b4407f304
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 10%

---

# 将区段映射到目标 {#map-segments-to-a-destination}

使用下列專案將區段對應至目的地 [!DNL RESTful API] 方法。

<!-- c_api_map_seg_dest.xml -->

## 支援的目的地型別：僅限URL和Cookie

可用 `POST` 方法可让您将区段映射到 [!UICONTROL URL] 和 [!UICONTROL cookie destinations] 。 目前，您无法将区段与这些 [!DNL REST API] 方法进行 [!UICONTROL server-to-server destinations] 映射。请改用用户界面。 但是，相关的目标 `GET` 方法可让您检索有关 [!UICONTROL server-to-server destinations] 在用户界面中创建的信息。

## 将区段映射到非序列化 URL 目标 {#map-segment-non-serial}

一 `POST` 种允许您将区段映射到非串行 [!UICONTROL URL] 目标的方法。

<!-- r_map_noserial_url.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 示例请求

除非另有指示，否則所有要求值都是必要的。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-07-04"
}
```

### 响应

```
{
   "mappingId":65334,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4033,
   "elementName":"Sample games",
   "elementDescription":"Sample games pixel",
   "elementStatus":"active",
   "createTime":1338940094000,
   "updateTime":1338940094000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"https://adobe.com",
   "secureUrl":null,
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":null
}
```

## 將區段對應至序列化URL目的地 {#map-segment-serial}

A `POST` 可讓您將區段對應至序列化的方法 [!UICONTROL URL] 目的地。

<!-- r_map_serialized_url.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### 示例请求

在请求中， `traitAlias` 对应于键值对中的键。 除非另行指示，否则所有请求值都是必需的。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### 响应

```
{
   "mappingId":65335,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4034,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940401000,
   "updateTime":1338940401000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"123",
   "secureUrl":"123",
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":"123"
}
```

## 将区段映射到 Cookie 目标：单键、非序列化 {#map-segment-cookie-noserial}

A `POST` 可讓您將區段對應至單一索引鍵、非序列化的方法 [!UICONTROL cookie] 目的地。

<!-- r_map_cookie_noserial.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 示例请求

請求中的 `valueAlias` 對應到機碼值組中的值。 除非另有指示，否則所有要求值都是必要的。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "valueAlias":"123"
}
```

### 响应

```
{
   "destinationMappingId":65336,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4035,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940704000,
   "updateTime":1338940704000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":null,
   "valueAlias":"123"
}
```

## 将区段映射到 Cookie 目标：多键、非序列化 {#map-segment-cookie-multi-noserial}

一 `POST` 种允许您将区段映射到多键非序列化 [!UICONTROL cookie] 目标的方法。

<!-- r_map_cookie_multikey_noserial.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 示例请求

在请求中， `traitAlias` 并 `valueAlias` 分别在键值对中设置键和值。 除非另行指示，否则所有请求值都是必需的。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### 响应

```
{
   "mappingId":65338,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4037,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941092000,
   "updateTime":1338941092000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## 將區段對應至Cookie目的地：多索引鍵、序列化 {#map-segment-cookie-multi-serial}

A `POST` 可讓您將區段對應至序列化多索引鍵的方法 [!UICONTROL cookie destination].

<!-- r_map_cookie_multikey_serialized.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 示例请求

請求中的 `traitAlias` 和 `valueAlias` 在機碼 — 值組中設定機碼和值。 除非另行指示，否则所有请求值都是必需的。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### 响应

```
{
   "destinationMappingId":65340,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4038,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941273000,
   "updateTime":1338941273000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":2,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## 将区段映射到服务器到服务器的目标 {#map-segment-s2s}

一 `POST` 种允许您将区段映射到现有 [!UICONTROL server-to-server] 目标的方法。 但是，请注意，您无法使用这些当前可用 [!DNL API] 的方法创建 [!UICONTROL server-to-server] 目标。

<!-- r_map_segment_s2s.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 示例请求

請求中的 `traitAlias` 對應到機碼值組中的機碼。 除非另有指示，否則所有要求值都是必要的。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### 响应

```
{
   "destinationMappingId":65341,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":566,
   "elementName":"Sample",
   "elementDescription":"",
   "elementStatus":"active",
   "createTime":1338942118000,
   "updateTime":1338942118000,
   "crUID":308,
   "upUID":308,
   "sid":84326,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "traitAlias":"123"
}
```

## 大量建立目的地對應 {#bulk-create}

A `POST` 可讓您傳入以下陣列的方法 [!UICONTROL cookie] 或 [!UICONTROL URL] 目的地對應。

<!-- r_bulk_create.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### 示例请求

除非另有指示，否則所有要求值都是必要的。

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### 响应

成功的回應會傳回已建立對應的陣列。

```
[
    {
        "mappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "mappingId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "orderId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## 將多個區段新增至目的地 {#add-segments-dest}

`POST`允许您将多个区段映射到目标的方法。

<!-- r_add_segments_to_destination.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### 示例请求

在一个数组中创建多个目标映射。 除非另行指示，否则所有请求值都是必需的。

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### 响应

返回已创建映射的数组。

```
[
    {
        "destinationMappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "traitToDataOrderId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## 依目的地ID更新目的地 {#update-dest-data-order}

A `PUT` 可讓您透過以下方式更新現有目的地的方法 `destinationId`.

<!-- r_update_destination_data_order_id.xml -->

### 请求

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### 示例请求

除非另行指示，否则所有请求值都是必需的。

```
{
   "name":"Updated URL Destination (not serialized)",
   "description":"new description",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### 响应

```
{
    "destinationType": "PUSH",
    "destinationId": 780,
    "dataSourceId": null,
    "pid": 1099,
    "name": "Updated URL Destination (not serialized)",
    "description": "new description",
    "startDate": null,
    "endDate": null,
    "status": 1,
    "createTime": 1348851790000,
    "updateTime": 1353372029000,
    "crUID": 884,
    "upUID": 1065,
    "domainRestrictions":"all_domains",
    "tagType": 0,
    "serializationEnabled": false,
    "urlFormatString": null,
    "secureUrlFormatString": null,
    "delimiter": null,
    "mappings": null
}
```

## 通过映射 ID 更新指向目标的映射 {#update-mapping-dest-id}

`PUT`允许您通过指定 `mappingId` 的方式更新目标映射的方法。

<!-- r_update_destination_trait_data_order_id.xml -->

### 请求

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### 示例请求

除非另行指示，否则所有请求值都是必需的。

```
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
}
```

### 响应

```
{
    "mappingId": 103453,
    "traitType": "SEGMENT",
    "traitValue": 0,
    "destinationId": 780,
    "elementName": "sample",
    "elementDescription": "test",
    "elementStatus": "active",
    "createTime": 1353373005000,
    "updateTime": 1353373005000,
    "crUID": 1065,
    "upUID": 1065,
    "sid": 105123,
    "startDate": "2012-11-19",
    "endDate": null,
    "priority": null,
    "url": "https://www.adobe.com/send?%ALIAS%",
    "secureUrl": null,
    "tagCode": null,
    "secureTagCode": null,
    "traitAlias": null
}
```

>[!MORELIKETHIS]
>
>* [目标](../../../features/destinations/destinations.md)
>* [目的地序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [键值对说明](../../../reference/key-value-pairs-explained.md)

