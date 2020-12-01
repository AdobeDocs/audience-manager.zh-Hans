---
description: 可选方法，允许您根据函数或您自己的内部类别流程为用户定义的类型或报告分配特征。
seo-description: 可选方法，允许您根据函数或您自己的内部类别流程为用户定义的类型或报告分配特征。
seo-title: 特征类型方法
solution: Audience Manager
title: 特征类型方法
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 9%

---


# 特征类型方法 {#trait-type-methods}

可选方法，允许您根据函数或您自己的内部类别流程为用户定义的类型或报告分配特征。

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>特征类型方法不将特征分配给[常用分类](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods)使用的类别。 将这些视为与常用分类不同的标签。

对于可视引用，[!UICONTROL Trait Types]是位于&#x200B;**[!UICONTROL Traits > Create new trait > Basic Information]**&#x200B;下[!DNL UI]的下拉控件。

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

## 特征类型{#return-props}的返回属性

一种`GET`方法，它返回有关指定特征类型的详细信息。

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

`GET`方法，返回有关数组中所有特征类型的详细信息。

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
