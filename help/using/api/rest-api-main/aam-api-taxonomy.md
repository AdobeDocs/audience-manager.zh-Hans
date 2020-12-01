---
description: 用于视图Audience Manager常用分类的方法。 此可选分类方案将特征组织到行业标准类别中。
seo-description: 用于视图Audience Manager常用分类的方法。 此可选分类方案将特征组织到行业标准类别中。
seo-title: 分类 API 方法
solution: Audience Manager
title: 分类 API 方法
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 7%

---


# 分类 API 方法 {#taxonomic-api-methods}

用于视图Audience Manager常用分类的方法。 此可选分类方案将特征组织到行业标准类别中。

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>不能使用这些方法创建新的分类类别或分类特征。 要对特征进行分类，请使用特征创建或更新方法指定相应的`categoryId`。

## 返回特定分类{#return-specific-taxonomy}

`GET`方法，返回有关指定分类类别的详细信息。

<!-- r_rest_api_taxonomy.xml -->

### 请求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### 响应

成功的响应返回`200 OK`和指定ID的类别。 如果ID不存在，则不成功的请求将返回`404 No Content`。

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

## 返回所有分类类别{#return-all-taxonomy-categories}

一种`GET`方法，它返回数组中顶级类别的列表。

<!-- r_rest_api_taxonomies.xml -->

### 请求

`GET https://api.demdex.com/v1/taxonomies/0/`

### 响应

短时间截断。

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

## 返回分类子类别{#return-taxonomy-sub-categories}

`GET`方法，它为数组中指定的父类别返回子类别。

<!-- r_rest_api_taxonomy_sub.xml -->

### 请求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### 响应

成功的响应返回`200 OK`和指定ID的类别。 如果ID不存在，则不成功的请求将返回`404 No Content`。 短时间截断。

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
