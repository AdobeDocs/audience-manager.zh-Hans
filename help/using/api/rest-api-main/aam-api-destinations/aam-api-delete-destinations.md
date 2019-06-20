---
description: 可删除目标和区段映射的DELETE和POST方法。
seo-description: 可删除目标和区段映射的DELETE和POST方法。
seo-title: 删除目标
solution: Audience Manager
title: 删除目标
uuid: 38fb2228-e564-49a3-9930-3139f8799 a8 f
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Delete Destinations {#delete-destinations}

`DELETE` 以及 `POST` 允许您删除目标和区段映射的方法。

<!-- r_delete_destinations_all.xml -->

## 删除目标

A `DELETE` method that removes a destination.

>[!NOTE]
>
>必须先删除所有区段映射，然后才能删除目标。

* Request: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Response: Returns code `204 No Content` if successful.

## 批量删除目标

Remove multiple destinations with this `POST` method. Pass in destination IDs ( `destinationId`) with an array in the request body.

* 请求: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Response: Returns code `204 No Content` if successful.

## 按区段映射ID删除目标映射

A `POST` method that removes destination mappings according to the specified segment ID.

* Request: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Response: Returns code `204 No Content` if successful.