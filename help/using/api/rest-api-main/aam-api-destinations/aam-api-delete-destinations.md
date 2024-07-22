---
description: 允许您删除目标和区段映射的DELETE和POST方法。
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: 删除目标
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 0%

---

# 删除目标 {#delete-destinations}

允许您删除目标和区段映射的`DELETE`和`POST`方法。

<!-- r_delete_destinations_all.xml -->

## 删除目标

删除目标的`DELETE`方法。

>[!NOTE]
>
>在删除目标之前，必须删除所有区段映射。

* 请求：`DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* 响应：如果成功，则返回代码`204 No Content`。

## 批量删除目标

使用此`POST`方法删除多个目标。 传入目标ID (`destinationId`)，请求正文中包含数组。

* 请求：`POST https://api.demdex.com/v1/destinations/bulk-delete/`
* 响应：如果成功，则返回代码`204 No Content`。

## 按区段映射ID删除目标映射

根据指定的区段ID删除目标映射的`POST`方法。

* 请求：`DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* 响应：如果成功，则返回代码`204 No Content`。
