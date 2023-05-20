---
description: 用於管理群組的Rest API方法，包括建立、更新、列出和刪除群組。
seo-description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-title: Group Management API Methods
solution: Audience Manager
title: 组管理 API 方法
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 12%

---

# 组管理 API 方法 {#group-management-api-methods}

Rest [!DNL API] 管理群組的方法，包括建立、更新、列出和刪除群組。

<!-- c_rest_api_user_man_group.xml -->

## 创建群组 {#create-group}

A `POST` 建立新使用者群組的方法。

<!-- r_rest_api_group_create.xml -->

### 请求

`POST /api/v1/groups/`

### 範例要求內文

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### 响应

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## 更新群組 {#update-group}

A `PUT` 更新使用者群組的方法。

<!--
r_rest_api_group_update.xml
-->

### 请求

`PUT /api/v1/groups/`*`<groupId>`*

### 範例要求內文

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### 响应

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## 清單群組 {#list-groups}

A `GET` 列出使用者群組的方法。

<!--
r_rest_api_group_list.xml
-->

### 请求

`GET /api/v1/groups/`

### 响应

```
[
  { 
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }, ...
]
```

## 删除群组 {#delete-groups}

A `DELETE` 刪除使用者群組及從該群組移除所有成員的方法。

<!-- r_rest_api_group_delete.xml -->

### 请求

`DELETE /api/v1/groups/`*`<groupId>`*

傳回 `204 No Content` 如果成功。 在衝突的情況下返回 `409 Conflict`.

## 大量刪除群組 {#delete-groups-bulk}

A `DELETE` 大量刪除多個群組，並從該群組移除所有成員的方法。

<!-- r_rest_api_group_delete_bulk.xml -->

### 请求

`DELETE /api/v1/groups/bulk-delete`

傳回 `204 No Content` 如果成功。 在衝突的情況下返回 `409 Conflict`.

## 列出群組的所有許可權 {#list-permissions-group}

A `GET` 列出群組上許可權物件的方法。

<!-- r_rest_api_perm_list_group.xml -->

### 请求

`GET /api/v1/groups/{groupId}/permissions`

### 响应

```
[{
 "objectId" : 34,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },

{
 "objectId" : "234",
 "objectType": "TRAIT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },
 {
 "objectId" : 277,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "MAP_TO_MODELS"]
 }
]
```

傳回 `400 Bad Request` 如果群組無法存取。

## 設定群組的許可權 {#set-permissions-group}

A `PUT` 更新群組許可權的方法。 此方法會以新許可權覆寫舊許可權。

<!-- r_rest_api_perm_set.xml -->

### 请求

`PUT /api/v1/groups/{groupId}/permissions/`

### 响应

```
[ 
  { "objectType" : "SEGMENT",
    "objectId" : 563,
    "permissions" : [ "READ", "WRITE"]
  },
  { "objectType" : "SEGMENT",
    "objectId" : 2363,
    "permissions" : [ "CREATE", "WRITE"]
  },
  { "objectType" : "TRAIT",
    "objectId" : 83498,
    "permissions" : [ "READ", "MAP_TO_SEGMENTS"]
  },
  { "objectType" : "DESTINATION",
    "objectId" : 304,
    "permissions" : [ "READ", "WRITE", "CREATE"]
  }
]
```

範例回應代表更新後的許可權物件清單。

傳回 `200 OK` 如果成功。 傳回 `400` 如果任何指定的許可權無效。 也可以傳回 `403` 如果登入的使用者無法存取物件。
