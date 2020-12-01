---
description: DELETE和POST方法，让您删除目标和区段映射。
seo-description: DELETE和POST方法，让您删除目标和区段映射。
seo-title: 删除目标
solution: Audience Manager
title: 删除目标
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 7%

---


# 删除目标 {#delete-destinations}

`DELETE` 以及 `POST` 用于删除目标和区段映射的方法。

<!-- r_delete_destinations_all.xml -->

## 删除目标

删除目标的`DELETE`方法。

>[!NOTE]
>
>必须先删除所有段映射，然后才能删除目标。

* 请求: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* 响应：如果成功，则返回代码`204 No Content`。

## 批量删除目标

使用此`POST`方法删除多个目标。 将目标ID(`destinationId`)与请求主体中的数组一起传递。

* 请求: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* 响应：如果成功，则返回代码`204 No Content`。

## 按段映射ID删除目标映射

一种`POST`方法，根据指定的段ID删除目标映射。

* 请求: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* 响应：如果成功，则返回代码`204 No Content`。