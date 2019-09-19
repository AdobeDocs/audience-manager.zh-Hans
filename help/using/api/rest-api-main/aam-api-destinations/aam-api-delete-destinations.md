---
description: 使用DELETE和POST方法可删除目标和区段映射。
seo-description: 使用DELETE和POST方法可删除目标和区段映射。
seo-title: 删除目标
solution: Audience Manager
title: 删除目标
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# 删除目标 {#delete-destinations}

`DELETE` 以 `POST` 及用于删除目标和区段映射的方法。

<!-- r_delete_destinations_all.xml -->

## 删除目标

删 `DELETE` 除目标的方法。

>[!NOTE]
>
>必须先删除所有区段映射，然后才能删除目标。

* Request: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* 响应：如果成功， `204 No Content` 则返回代码。

## 批量删除目标

使用此方法删除多个 `POST` 目标。 将目标ID( `destinationId`)与请求主体中的数组一起传递。

* 请求: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* 响应：如果成功， `204 No Content` 则返回代码。

## 按区段映射ID删除目标映射

一种 `POST` 根据指定的段ID删除目标映射的方法。

* Request: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* 响应：如果成功， `204 No Content` 则返回代码。