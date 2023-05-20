---
description: 可讓您以程式設計方式列出Audience ManagerDCS區域的方法。
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: DCS 区域 API 方法
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 12%

---

# DCS 区域 API 方法 {#dcs-region-api-methods}

可讓您以程式設計方式列出Audience Manager的方法 [!DNL DCS] 地區。

<!-- c_rest_api_regions.xml -->

如需區域及其對應整數的清單，請參閱 [DCS地區ID、位置與主機名稱](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## 列出特定DCS區域 {#list-specific-dcs-region}

A `GET` 列出特定專案的方法 [!DNL DCS] 區域。

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

傳回 `200 OK` 如果成功。

如需區域及其對應整數的清單，請參閱 [DCS地區ID、位置與主機名稱](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## 列出DCS地區 {#list-dcs-regions}

A `GET` 要列出的方法 [!DNL DCS] 地區。

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

傳回 `200 OK` 如果成功。

如需區域及其對應整數的清單，請參閱 [DCS地區ID、位置與主機名稱](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
