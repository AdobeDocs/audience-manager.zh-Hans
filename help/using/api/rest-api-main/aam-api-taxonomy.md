---
description: 用于查看Audience Manager常用分类的方法。 此可选分类方案将特征组织为行业标准类别。
seo-description: 用于查看Audience Manager常用分类的方法。 此可选分类方案将特征组织为行业标准类别。
seo-title: 分类 API 方法
solution: Audience Manager
title: 分类 API 方法
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 8%

---

# 分类 API 方法 {#taxonomic-api-methods}

用于查看Audience Manager常用分类的方法。 此可选分类方案将特征组织为行业标准类别。

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>您无法使用这些方法创建新的分类类别或对特征进行分类。 要对特征进行分类，请使用特征创建或更新方法指定相应的`categoryId`。

## 返回特定分类{#return-specific-taxonomy}

`GET`方法，返回有关指定分类类别的详细信息。

<!-- r_rest_api_taxonomy.xml -->

### 请求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### 响应

成功的响应会返回指定ID的`200 OK`和类别。 如果ID不存在，则失败的请求会返回`404 No Content`。

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

`GET`方法，返回数组中顶级类别的列表。

<!-- r_rest_api_taxonomies.xml -->

### 请求

`GET https://api.demdex.com/v1/taxonomies/0/`

### 响应

为简短而截断。

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

`GET`方法，用于返回数组中指定父类别的子类别。

<!-- r_rest_api_taxonomy_sub.xml -->

### 请求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### 响应

成功的响应会返回指定ID的`200 OK`和类别。 如果ID不存在，则失败的请求会返回`404 No Content`。 为简短而截断。

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
