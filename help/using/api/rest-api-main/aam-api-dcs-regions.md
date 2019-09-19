---
description: 允许您以编程方式列出Audience Manager DCS区域的方法。
seo-description: 允许您以编程方式列出Audience Manager DCS区域的方法。
seo-title: DCS区域API方法
solution: Audience Manager
title: DCS区域API方法
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DCS区域API方法 {#dcs-region-api-methods}

允许您以编程方式列出Audience manager区域的 [!UICONTROL DCS] 方法。

<!-- c_rest_api_regions.xml -->

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## 列出特定DCS区域 {#list-specific-dcs-region}

一种 `GET` 列出特定区域的 [!UICONTROL DCS] 方法。

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

## 列出DCS区域 {#list-dcs-regions}

一种 `GET` 列出区域的 [!UICONTROL DCS] 方法。

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
