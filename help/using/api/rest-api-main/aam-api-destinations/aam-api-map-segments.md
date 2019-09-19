---
description: 使用这些RESTful API方法将区段映射到目标。
seo-description: 使用这些RESTful API方法将区段映射到目标。
seo-title: 将区段映射到目标
solution: Audience Manager
title: 将区段映射到目标
uuid: 35358ace-3082-4e86-a6eb-d77281af6d7e
translation-type: tm+mt
source-git-commit: 8ab675cac67a0e6353cf5fd14944c7c5cc849e5a

---


# 将区段映射到目标 {#map-segments-to-a-destination}

使用这些方法将区段映射到 [!DNL RESTful API] 目标。

<!-- c_api_map_seg_dest.xml -->

## 支持的目标类型：仅URL和Cookie

使用可 `POST` 用的方法，您可以将区段映射到 [!UICONTROL URL] 和仅 [!UICONTROL cookie destinations] 映射。 目前，您无法使用这些方法将区 [!UICONTROL server-to-server destinations] 段映射到 [!DNL REST API] 区段。 请改用用户界面。 但是，相关的目标方 `GET` 法允许您检索有关在用户 [!UICONTROL server-to-server destinations] 界面中创建的信息。

>[!MORE_LIKE_THIS]
>
>* [目标](../../../features/destinations/destinations.md)
>* [目标序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [说明的键值对](../../../reference/key-value-pairs-explained.md)


## 将区段映射到无序列化URL目标 {#map-segment-non-serial}

一 `POST` 种方法，可让您将区段映射到非串行目 [!UICONTROL URL] 标。

<!-- r_map_noserial_url.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 示例请求

除非另有指明，否则所有请求值都是必需的。

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

## 将区段映射到序列化URL目标 {#map-segment-serial}

一种 `POST` 方法，可让您将区段映射到序列化目 [!UICONTROL URL] 标。

<!-- r_map_serialized_url.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### 示例请求

在请求中，该 `traitAlias` 键对应于键值对中的键。 除非另有指明，否则所有请求值都是必需的。

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

## 将区段映射到Cookie目标：单键、无序列号 {#map-segment-cookie-noserial}

一种 `POST` 方法，可让您将区段映射到单键、无序列化目 [!UICONTROL cookie] 标。

<!-- r_map_cookie_noserial.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 示例请求

在请求中，该 `valueAlias` 值与键值对中的值相对应。 除非另有指明，否则所有请求值都是必需的。

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

## 将区段映射到Cookie目标：多密钥、无序列号 {#map-segment-cookie-multi-noserial}

一种 `POST` 方法，可让您将区段映射到多键、无序列化目 [!UICONTROL cookie] 标。

<!-- r_map_cookie_multikey_noserial.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 示例请求

在请求中， `traitAlias` 键 `valueAlias` 值对中分别设置键和值。 除非另有指明，否则所有请求值都是必需的。

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

## 将区段映射到Cookie目标：多键、序列化 {#map-segment-cookie-multi-serial}

一种 `POST` 方法，可让您将区段映射到多键序列化 [!UICONTROL cookie destination]。

<!-- r_map_cookie_multikey_serialized.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 示例请求

在请求中， `traitAlias` 并 `valueAlias` 在键值对中设置键和值。 除非另有指明，否则所有请求值都是必需的。

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

## 将区段映射到服务器到服务器目标 {#map-segment-s2s}

一种 `POST` 方法，可让您将区段映射到现有目 [!UICONTROL server-to-server] 标。 但是，请注意，您不能使用这些当 [!UICONTROL server-to-server] 前可用的方法创建目 [!DNL API] 标。

<!-- r_map_segment_s2s.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 示例请求

在请求中，该 `traitAlias` 键对应于键值对中的键。 除非另有指明，否则所有请求值都是必需的。

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

## 批量创建目标映射 {#bulk-create}

一 `POST` 种方法，它允许您传入一组或目标 [!UICONTROL cookie] 映射 [!UICONTROL URL] 。

<!-- r_bulk_create.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### 示例请求

除非另有指明，否则所有请求值都是必需的。

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

成功的响应会返回已创建映射的数组。

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

## 将多个区段添加到目标 {#add-segments-dest}

一种 `POST` 方法，可让您将多个区段映射到目标。

<!-- r_add_segments_to_destination.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### 示例请求

在数组中创建多个目标映射。 除非另有指明，否则所有请求值都是必需的。

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

## 按目标ID更新目标 {#update-dest-data-order}

一种 `PUT` 允许您通过更新现有目标的方法 `destinationId`。

<!-- r_update_destination_data_order_id.xml -->

### 请求

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### 示例请求

除非另有指明，否则所有请求值都是必需的。

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

## 通过映射ID更新映射到目标 {#update-mapping-dest-id}

一 `PUT` 种方法，它允许您按指定更新到目标的映射 `mappingId`。

<!-- r_update_destination_trait_data_order_id.xml -->

### 请求

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### 示例请求

除非另有指明，否则所有请求值都是必需的。

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
