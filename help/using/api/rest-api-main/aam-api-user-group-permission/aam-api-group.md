---
description: 用于管理组的REST API方法，包括创建、更新、列出和删除组。
seo-description: 用于管理组的REST API方法，包括创建、更新、列出和删除组。
seo-title: 组管理API方法
solution: Audience Manager
title: 组管理API方法
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# 组管理API方法 {#group-management-api-methods}

其余 [!DNL API] 方法用于管理组，包括创建、更新、列出和删除组。

<!-- c_rest_api_user_man_group.xml -->

## 创建群组 {#create-group}

用 `POST` 于创建新用户组的方法。

<!-- r_rest_api_group_create.xml -->

### 请求

`POST /api/v1/groups/`

### 示例请求主体

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

## 更新用户组 {#update-group}

一种 `PUT` 更新用户组的方法。

<!--
r_rest_api_group_update.xml
-->

### 请求

`PUT /api/v1/groups/`*`<groupId>`*

### 示例请求主体

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

## 列表组 {#list-groups}

列 `GET` 出用户组的方法。

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

一种 `DELETE` 删除用户组并从该用户组中删除所有成员的方法。

<!-- r_rest_api_group_delete.xml -->

### 请求

`DELETE /api/v1/groups/`*`<groupId>`*

成功 `204 No Content` 时返回。 如果发生冲突，请返回 `409 Conflict`。

## 批量删除组 {#delete-groups-bulk}

一种 `DELETE` 批量删除多个用户组并从该组中删除所有成员的方法。

<!-- r_rest_api_group_delete_bulk.xml -->

### 请求

`DELETE /api/v1/groups/bulk-delete`

成功 `204 No Content` 时返回。 如果发生冲突，请返回 `409 Conflict`。

## 列出用户组的所有权限 {#list-permissions-group}

列 `GET` 出组上权限对象的方法。

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

如果 `400 Bad Request` 组无法访问，则返回。

## Set Permissions for a Group {#set-permissions-group}

用于 `PUT` 更新组权限的方法。 此方法用新权限覆盖旧权限。

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

示例响应表示权限对象的更新列表。

成功 `200 OK` 时返回。 如果 `400` 任何给定权限无效，则返回。 如果已登 `403` 录用户无法访问该对象，也可以返回。