---
description: 用于管理组的REST API方法，包括创建、更新、列表、删除组。
seo-description: 用于管理组的REST API方法，包括创建、更新、列表、删除组。
seo-title: 组管理 API 方法
solution: Audience Manager
title: 组管理 API 方法
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 13%

---

# 组管理 API 方法 {#group-management-api-methods}

保留[!DNL API]方法来管理组，包括创建、更新、列表、删除组。

<!-- c_rest_api_user_man_group.xml -->

## 创建群组 {#create-group}

用于创建新用户组的`POST`方法。

<!-- r_rest_api_group_create.xml -->

### 请求

`POST /api/v1/groups/`

### 示例请求正文

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

## 更新组{#update-group}

用于更新用户组的`PUT`方法。

<!--
r_rest_api_group_update.xml
-->

### 请求

`PUT /api/v1/groups/`*`<groupId>`*

### 示例请求正文

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

## 列表组{#list-groups}

列出用户组的`GET`方法。

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

`DELETE`方法，用于删除用户组并从该组中删除所有成员。

<!-- r_rest_api_group_delete.xml -->

### 请求

`DELETE /api/v1/groups/`*`<groupId>`*

如果成功，则返回`204 No Content`。 如果发生冲突，则返回`409 Conflict`。

## 批量{#delete-groups-bulk}删除组

一种`DELETE`方法，用于批量删除多个组并从该组中删除所有成员。

<!-- r_rest_api_group_delete_bulk.xml -->

### 请求

`DELETE /api/v1/groups/bulk-delete`

如果成功，则返回`204 No Content`。 如果发生冲突，则返回`409 Conflict`。

## 列出组{#list-permissions-group}的所有权限

列出组上权限对象的`GET`方法。

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

如果无法访问组，则返回`400 Bad Request`。

## 设置组{#set-permissions-group}的权限

用于更新组权限的`PUT`方法。 此方法将使用新权限覆盖旧权限。

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

如果成功，则返回`200 OK`。 如果任何给定权限无效，则返回`400`。 如果登录用户无法访问对象，则还可以返回`403`。
