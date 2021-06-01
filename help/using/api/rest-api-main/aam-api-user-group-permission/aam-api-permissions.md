---
description: 用于管理对象和组权限的REST API方法。
seo-description: 用于管理对象和组权限的REST API方法。
seo-title: 权限管理 API 方法
solution: Audience Manager
title: 权限管理 API 方法
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 15%

---

# 权限管理 API 方法 {#permissions-management-api-methods}

Rest [!DNL API]方法用于管理对象和组的权限。

<!-- c_rest_api_perm_man.xml -->

## 列出可用对象类型{#list-object-types}

一种`GET`方法，用于列出可基于角色的访问控制可以设置的可用对象类型。

<!-- r_rest_api_perm_list.xml -->

### 请求

`GET /api/v1/permissionable-object-types/`

### 响应

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## 列出对象类型{#list-permissions-object-type}的可用权限

`GET`方法，用于列出对象类型的可用权限。

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
>对象类型TAGS和DERIVED SIGNALS没有使用的常规权限。 这些对象类型的控件仅通过“全部”或“无通配符权限”进行更改。
