---
description: 允许您将特征分配给用户定义的类型或类别的可选方法，通常根据函数或您自己的内部报告流程进行分配。
seo-description: Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.
seo-title: Trait Type Methods
solution: Audience Manager
title: 特征类型方法
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
exl-id: d450f9ce-2abb-4a8b-b8db-2962b84fb341
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 3%

---

# 特征类型方法 {#trait-type-methods}

允许您将特征分配给用户定义的类型或类别的可选方法，通常根据函数或您自己的内部报告流程进行分配。

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>特征类型方法不会将特征分配给[通用分类](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods)使用的类别。 请将其视为与通用分类法不同的标签。

对于可视化引用，[!UICONTROL Trait Types]是位于[!DNL UI]下的&#x200B;**[!UICONTROL Traits > Create new trait > Basic Information]**&#x200B;中的下拉控件。

## 创建新特征类型 {#create-trait-type}

允许您创建新特征类型的`POST`方法。

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

## 返回特征类型的属性 {#return-props}

返回有关指定特征类型的详细信息的`GET`方法。

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

## 返回所有特征类型的属性 {#return-props-all}

一个`GET`方法，可返回有关数组中所有特征类型的详细信息。

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
