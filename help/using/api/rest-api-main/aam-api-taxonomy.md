---
description: 允许您查看Audience Manager常用分类的方法。此可选分类方案将特征组织到行业标准类别中。
seo-description: 允许您查看Audience Manager常用分类的方法。此可选分类方案将特征组织到行业标准类别中。
seo-title: 分类API方法
solution: Audience Manager
title: 分类API方法
uuid: 4ee29ba5-e9 ba-4498-a6 ee-7343227dd7 ba
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Taxonomic API Methods {#taxonomic-api-methods}

允许您查看Audience Manager常用分类的方法。此可选分类方案将特征组织到行业标准类别中。

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>您无法创建新分类类别或使用这些方法对特征分类。To classify a trait, specify the appropriate `categoryId` with a trait create or update method.

## Return a Specific Taxonomy {#return-specific-taxonomy}

A `GET` method that returns details about the specified taxonomic category.

<!-- r_rest_api_taxonomy.xml -->

### 请求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### 响应

A successful response returns `200 OK` and the category for the specified ID. `404 No Content` 如果ID不存在，则返回失败的请求。

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

## Return all Taxonomic Categories {#return-all-taxonomy-categories}

A `GET` method that returns a list of the top-level categories in an array.

<!-- r_rest_api_taxonomies.xml -->

### 请求

`GET https://api.demdex.com/v1/taxonomies/0/`

### 响应

简捷地截断。

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

## Return Taxonomic Sub-Categories {#return-taxonomy-sub-categories}

A `GET` method that returns sub-categories for the specified parent category in an array.

<!-- r_rest_api_taxonomy_sub.xml -->

### 请求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### 响应

A successful response returns `200 OK` and the category for the specified ID. `404 No Content` 如果ID不存在，则返回失败的请求。简捷地截断。

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
