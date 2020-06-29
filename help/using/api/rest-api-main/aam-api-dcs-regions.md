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

用于以编程方式列表Audience Manager区 [!DNL DCS] 域的方法。

<!-- c_rest_api_regions.xml -->

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## 列表特定DCS区域 {#list-specific-dcs-region}

一种 `GET` 列表特定区域的 [!DNL DCS] 方法。

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

成功 `200 OK` 时返回。

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## 列表DCS区域 {#list-dcs-regions}

一种 `GET` 列表区域 [!DNL DCS] 的方法。

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

成功 `200 OK` 时返回。

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
