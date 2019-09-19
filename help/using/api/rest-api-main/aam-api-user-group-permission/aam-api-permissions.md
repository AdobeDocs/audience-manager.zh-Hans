---
description: 用于管理对象和组的权限的REST API方法。
seo-description: 用于管理对象和组的权限的REST API方法。
seo-title: 权限管理API方法
solution: Audience Manager
title: 权限管理API方法
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# 权限管理API方法 {#permissions-management-api-methods}

其余 [!DNL API] 方法用于管理对象和组的权限。

<!-- c_rest_api_perm_man.xml -->

## 列出可用对象类型 {#list-object-types}

一种 `GET` 列出可设置基于角色的访问控制的可用对象类型的方法。

<!-- r_rest_api_perm_list.xml -->

### 请求

`GET /api/v1/permissionable-object-types/`

### 响应

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## 列出对象类型的可用权限 {#list-permissions-object-type}

列 `GET` 出对象类型可用权限的方法。

<!-- r_rest_api_perm_list_perms.xml -->

### 请求

`GET /api/v1/permissionable-object-types/SEGMENT/`

### 响应

```
{ 
 "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ], 
 "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ]
}
```

>[!NOTE]
>
>对象类型TAGS和DERIVED SIGNALS没有常规使用权限。 对这些对象类型的控件仅通过“全部”或“无”通配符权限进行更改。