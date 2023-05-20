---
description: 可讓您檢視Audience Manager通用分類法的方法。 此選擇性分類配置會將特徵組織為符合業界標準的類別。
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: 分类 API 方法
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 6%

---

# 分类 API 方法 {#taxonomic-api-methods}

可讓您檢視Audience Manager通用分類法的方法。 此選擇性分類配置會將特徵組織為符合業界標準的類別。

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>您無法使用這些方法建立新的分類類別或分類特徵。 若要分類特徵，請指定適當的 `categoryId` 特徵建立或更新方法。

## 傳回特定分類法 {#return-specific-taxonomy}

A `GET` 傳回指定分類類別詳細資料的方法。

<!-- r_rest_api_taxonomy.xml -->

### 请求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### 响应

成功傳回回應 `200 OK` 以及指定ID的類別。 傳回失敗的請求 `404 No Content` 如果ID不存在。

```
{
    "crUID": 158,
    "name": "Arts & Entertainment",
    "upUID": 158,
    "description": "Arts & Entertainment",
    "categoryID": 1,
    "parentCategoryID": 0
}
```

## 傳回所有分類類別 {#return-all-taxonomy-categories}

A `GET` 傳回陣列中上層類別清單的方法。

<!-- r_rest_api_taxonomies.xml -->

### 请求

`GET https://api.demdex.com/v1/taxonomies/0/`

### 响应

為簡短起見，已截斷。

```
[
    {
        "crUID": 158,
        "name": "Arts & Entertainment",
        "upUID": 158,
        "description": "Arts & Entertainment",
        "categoryID": 1,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Automotive",
        "upUID": 158,
        "description": "Automotive",
        "categoryID": 2,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Business",
        "upUID": 158,
        "description": "Business",
        "categoryID": 3,
        "parentCategoryID": 0
    }
]
```

## 傳回分類子類別 {#return-taxonomy-sub-categories}

A `GET` 傳回陣列中指定父類別的子類別的方法。

<!-- r_rest_api_taxonomy_sub.xml -->

### 请求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### 响应

成功傳回回應 `200 OK` 以及指定ID的類別。 傳回失敗的請求 `404 No Content` 如果ID不存在。 為簡短起見，已截斷。

```
[
    {
        "crUID": 158,
        "name": "Books & Literature",
        "upUID": 158,
        "description": "Books & Literature",
        "categoryID": 25,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Celebrity Fan/Gossip",
        "upUID": 158,
        "description": "Celebrity Fan/Gossip",
        "categoryID": 49,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Fine Art",
        "upUID": 158,
        "description": "Fine Art",
        "categoryID": 72,
        "parentCategoryID": 1
    }
]
```
