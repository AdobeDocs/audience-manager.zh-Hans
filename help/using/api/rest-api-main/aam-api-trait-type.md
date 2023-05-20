---
description: 選擇性方法，可讓您將特徵指派給使用者定義的型別或類別（通常根據函式或您自己的內部報告程式）。
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
ht-degree: 9%

---

# 特征类型方法 {#trait-type-methods}

選擇性方法，可讓您將特徵指派給使用者定義的型別或類別（通常根據函式或您自己的內部報告程式）。

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>特徵型別方法不會將特徵指派給使用的類別， [通用分類法](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). 請將這些視為與通用分類法不同的標籤。

如需視覺參考， [!UICONTROL Trait Types] 是位於以下位置的下拉式清單控制項： [!DNL UI] 在 **[!UICONTROL Traits > Create new trait > Basic Information]**.

## 建立新特徵型別 {#create-trait-type}

A `POST` 可讓您建立新特徵型別的方法。

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

## 傳回特徵型別的屬性 {#return-props}

A `GET` 傳回指定特徵型別詳細資料的方法。

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

## 傳回所有特徵型別的屬性 {#return-props-all}

A `GET` 方法，可傳回陣列中所有特徵型別的詳細資訊。

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
