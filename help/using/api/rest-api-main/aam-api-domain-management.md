---
description: 域管理方法，允许您创建和管理要向其发送数据的域（仅限cookie目标）。
seo-description: 域管理方法，允许您创建和管理要向其发送数据的域（仅限cookie目标）。
seo-title: 域管理 API 方法
solution: Audience Manager
title: 域管理 API 方法
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 6%

---


# 域管理 API 方法 {#domain-management-api-methods}

域管理方法，允许您创建和管理要向其发送数据的域（仅限cookie目标）。

<!-- c_partner_site.xml -->

## Create a New Domain {#create-new-domain}

一 `POST` 种方法，允许您为（仅Cookie目标）创建新域。

<!-- r_post_new_partner_site.xml -->

### 请求

`POST` `https://api.demdex.com/v1/partner-sites/`

### 示例请求

```
{
   "url":"example1.com"
}
```

### 响应

成功的响应会 `201 created` 返回合作伙伴站点，包括其唯一ID。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 删除域 {#delete-domain}

一种 `DELETE` 允许您删除域的方法（仅用于cookie目标）。

<!-- r_delete_partner_site.xml -->

### 请求

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 响应

返回成功的响应 `204 no content`。 如果 `404 not found` 找不到合作伙伴站点，则返回。

## 返回域的属性 {#return-props-domain}

返回 `GET` 有关指定域的详细信息的方法（仅用于cookie目标）。

<!-- r_get_partner_site.xml -->

### 请求

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 响应

成功的响应 `200 OK` 返回数据，如以下示例所示。 如果 `404 Not found` 找不到站点ID或合作伙伴，则返回。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 返回所有域的属性 {#return-props-all-domains}

返回 `GET` 有关所有域的信息的方法（仅用于cookie目标）。

<!-- r_get_partner_sites.xml -->

### 请求

`GET https://api.demdex.com/v1/partner-sites/`

### 可选查询参数

可以将这些可选参数与返 [!DNL API] 回对象所 *有属性* 的方法结合使用。 将查询传递到请求字符串时，在中设置这些选项 [!DNL API]。 请参 [阅可选参数](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)。

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td> 
   <td colname="col2"> 按页码返回结果。 开始编号为0。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> 设置请求返回的响应结果数（默认为10）。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> 根据指定的JSON属性对结果进行排序并返回。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 按降序排序和返回结果。 升序为默认值。 </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">根据要用作搜索参数的指定字符串返回结果。 例如，假设您要在该项目的任何值字段中查找带有“Test”字样的所有模型的结果。 您的示例请求可能如下所示： <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>您可以搜索“get all”方法返回的任何值。 </p> </td>
  </tr> 
 </tbody> 
</table>

### 响应

成功的响应 `200 OK` 返回数组中的数据，如以下示例所示。 如果 `404 Not found` 找不到站点ID或合作伙伴，则返回。

```
[
    {
        "pid": 1111,
        "siteId": 111,
        "url": "example1.com"
    },
    {
        "pid": 2222,
        "siteId": 222,
        "url": "example2.com"
    },
    {
        "pid": 3333,
        "siteId": 333,
        "url": "example3.com"
    }
]
```
