---
description: Rest API方法用于管理对象和组的权限。
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: 权限管理API方法
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
TQID: https://experienceleague.adobe.com/E9JWh1JKhHOSd7MzeOR8csVXChyh4Q0RiCj3Y5yb2vM
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2: id: d8f681b8-67cc-42dc-85c5-a0977528a942
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 96
ht-degree: 2%

---

# 权限管理API方法 {#permissions-management-api-methods}

剩余[!DNL API]个方法用于管理对象和组的权限。

<!-- c_rest_api_perm_man.xml -->

## 列出可用的对象类型 {#list-object-types}

`GET`方法，用于列出可设置基于角色的访问控制的可用对象类型。

<!-- r_rest_api_perm_list.xml -->

### 请求

`GET /api/v1/permissionable-object-types/`

### 响应

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## 列出对象类型的可用权限 {#list-permissions-object-type}

用于列出对象类型的可用权限的`GET`方法。

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
>对象类型TAGS和DERIVED SIGNALS没有正常使用权限。 对这些对象类型的控制仅由“全部”或“无通配符”权限更改。
