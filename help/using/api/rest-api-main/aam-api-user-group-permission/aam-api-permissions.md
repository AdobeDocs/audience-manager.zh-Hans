---
description: 用于管理对象和组权限的REST API方法。
seo-description: 用于管理对象和组权限的REST API方法。
seo-title: 权限管理 API 方法
solution: Audience Manager
title: 权限管理 API 方法
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 14%

---


# 权限管理 API 方法 {#permissions-management-api-methods}

保留[!DNL API]方法以管理对象和组的权限。

<!-- c_rest_api_perm_man.xml -->

## 列表可用对象类型{#list-object-types}

一种`GET`方法，用于列表可设置基于角色的访问控制的可用对象类型。

<!-- r_rest_api_perm_list.xml -->

### 请求

`GET /api/v1/permissionable-object-types/`

### 响应

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## 列表对象类型{#list-permissions-object-type}的可用权限

用于列表对象类型的可用权限的`GET`方法。

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
>对象类型TAGS和DERIVED SIGNALS没有常规权限可使用。 对这些对象类型的控制仅通过“全部”或“无”通配符权限进行更改。