---
description: 用于以编程方式列表Audience ManagerDCS区域的方法。
seo-description: 用于以编程方式列表Audience ManagerDCS区域的方法。
seo-title: DCS 区域 API 方法
solution: Audience Manager
title: DCS 区域 API 方法
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 14%

---


# DCS 区域 API 方法 {#dcs-region-api-methods}

用于以编程方式列表Audience Manager[!DNL DCS]区域的方法。

<!-- c_rest_api_regions.xml -->

有关列表区域及其相应整数，请参阅[DCS区域ID、位置和主机名](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

## 列表特定DCS区域{#list-specific-dcs-region}

列表特定[!DNL DCS]区域的`GET`方法。

<!-- r_rest_api_regions_list_specific.xml -->

### 请求

`GET /v1/dcs-regions/`*`<id>`*

### 示例响应

```
{ 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code>",
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  }
```

如果成功，则返回`200 OK`。

有关列表区域及其相应整数，请参阅[DCS区域ID、位置和主机名](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

## 列表DCS区域{#list-dcs-regions}

用`GET`方法列表[!DNL DCS]区域。

<!-- r_rest_api_regions_list.xml -->

### 请求

`GET /v1/dcs-regions/`

### 示例响应

```
[
  { 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code> # APSE, USE, etc,
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  },
  ...
]
```

如果成功，则返回`200 OK`。

有关列表区域及其相应整数，请参阅[DCS区域ID、位置和主机名](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。
