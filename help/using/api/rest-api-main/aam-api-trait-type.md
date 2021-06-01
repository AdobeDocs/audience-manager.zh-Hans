---
description: 可选方法，用于为用户定义的类型或类别分配特征（通常根据函数或您自己的内部报告流程）。
seo-description: 可选方法，用于为用户定义的类型或类别分配特征（通常根据函数或您自己的内部报告流程）。
seo-title: 特征类型方法
solution: Audience Manager
title: 特征类型方法
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
exl-id: d450f9ce-2abb-4a8b-b8db-2962b84fb341
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 10%

---

# 特征类型方法 {#trait-type-methods}

可选方法，用于为用户定义的类型或类别分配特征（通常根据函数或您自己的内部报告流程）。

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>特征类型方法不会将特征分配给[常用分类](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods)使用的类别。 将它们视为与常用分类不同的标签。

对于可视化引用，[!UICONTROL Trait Types]是位于&#x200B;**[!UICONTROL Traits > Create new trait > Basic Information]**&#x200B;下[!DNL UI]中的下拉控件。

## 创建新特征类型{#create-trait-type}

`POST`方法，用于创建新特征类型。

<!-- r_rest_api_create_trait_type.xml -->

### 请求

`POST https://api.demdex.com/v1/customer-trait-types`

### 示例请求

```
{
"name":"Custom trait type"
}
```

### 响应

```
{
    "pixelType": 34,
    "pid": 1099,
    "name": "Custom type",
    "description": null,
    "crUID": 694,
    "upUID": 694,
    "createTime": 1358297352000,
    "updateTime": 1358297352000
}
```

## 返回特征类型{#return-props}的属性

`GET`方法，可返回有关指定特征类型的详细信息。

<!-- r_rest_api_get_trait_type.xml -->

### 请求

`GET https://api.demdex.com/v1/customer-trait-types/`*`<customerTraitTypeId>`*

### 响应

```
{
    "pixelType": 4,
    "pid": 0,
    "name": "Delivery Event",
    "description": "Delivery Event",
    "crUID": 158,
    "upUID": 158,
    "createTime": 1299115496000,
    "updateTime": 1299115496000
}
```

## 返回所有特征类型{#return-props-all}的属性

`GET`方法，可返回有关数组中所有特征类型的详细信息。

<!-- r_rest_api_get_trait_types.xml -->

### 请求

`GET https://api.demdex.com/v1/customer-trait-types/`

### 响应

```
[
    {
        "pixelType": 200,
        "pid": 1099,
        "name": "Customer Specific Trait Type",
        "description": "Test",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1349990458000,
        "updateTime": 1349990458000
    },
    {
        "pixelType": 1,
        "pid": 0,
        "name": "User Trait",
        "description": "User Trait",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115492000,
        "updateTime": 1299115492000
    },
    {
        "pixelType": 2,
        "pid": 0,
        "name": "Site Visitor",
        "description": "Site Visitor",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115493000,
        "updateTime": 1299115493000
    }
]
```
