---
description: 可选方法，允许您为用户定义的类型或类别分配特征，通常根据函数或您自己的内部报告进程分配。
seo-description: 可选方法，允许您为用户定义的类型或类别分配特征，通常根据函数或您自己的内部报告进程分配。
seo-title: 特征类型方法
solution: Audience Manager
title: 特征类型方法
uuid: 082931d5-457b-4622-817b-86303f38c26a
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# 特征类型方法 {#trait-type-methods}

可选方法，允许您为用户定义的类型或类别分配特征，通常根据函数或您自己的内部报告进程分配。

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>特征类型方法不将特征指定到常用分类所使用 [的类别](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods)。 将它们视为与常用分类不同的标签。

对于可视参考， [!UICONTROL Trait Types] 是位于下面的下拉式控 [!DNL UI] 件 **[!UICONTROL Traits > Create new trait > Basic Information]**。

## 创建新特征类型 {#create-trait-type}

一种 `POST` 允许您创建新特征类型的方法。

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

## 特征类型的返回属性 {#return-props}

返回 `GET` 有关指定特征类型的详细信息的方法。

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

一种 `GET` 返回数组中所有特征类型详细信息的方法。

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
