---
description: 域管理方法，允许您创建和管理要向其发送数据的域（仅限cookie目标）。
seo-description: 域管理方法，允许您创建和管理要向其发送数据的域（仅限cookie目标）。
seo-title: 域管理API方法
solution: Audience Manager
title: 域管理API方法
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 域管理API方法 {#domain-management-api-methods}

域管理方法，允许您创建和管理要向其发送数据的域（仅限cookie目标）。

<!-- c_partner_site.xml -->

## Create a New Domain {#create-new-domain}

一 `POST` 种方法，允许您为（仅cookie目标）创建新域。

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

成功的响应将返 `201 created` 回合作伙伴站点，包括其唯一ID。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 删除域 {#delete-domain}

一种 `DELETE` 允许您删除域（仅用于Cookie目标）的方法。

<!-- r_delete_partner_site.xml -->

### 请求

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 响应

成功的响应会返回 `204 no content`。 如果 `404 not found` 找不到合作伙伴站点，则返回。

## 返回域的属性 {#return-props-domain}

返回 `GET` 有关指定域的详细信息的方法（仅适用于cookie目标）。

<!-- r_get_partner_site.xml -->

### 请求

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 响应

成功的响应会返 `200 OK` 回数据，如下面的示例所示。 如果 `404 Not found` 未找到站点ID或合作伙伴，则返回。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 返回所有域的属性 {#return-props-all-domains}

一种 `GET` 返回有关所有域的信息的方法（仅适用于Cookie目标）。

<!-- r_get_partner_sites.xml -->

### 请求

`GET https://api.demdex.com/v1/partner-sites/`

### 可选查询参数

可以将这些可选参数与返回 [!DNL API] 对象所有属 *性的方* 法一起使用。 将查询传入请求字符串时，在请求字符串中设置这些选项 [!DNL API]。 请参阅 [可选参数](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)。

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
   <td colname="col2"> 按页码返回结果。 编号从0开始。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> 设置请求返回的响应结果数（默认为10）。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> 根据指定的JSON属性对结果进行排序和返回。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> 降序</code> </td>
   <td colname="col2"> 按降序排序和返回结果。 默认为升序。 </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> 搜索</code> </td>
   <td colname="col2">根据要用作搜索参数的指定字符串返回结果。 例如，假设您要查找所有模型的结果，这些模型在该项目的任何值字段中都有单词“Test”。 您的示例请求可能如下： <p><code> “获取”“https://api.demdex.com/v1/models/?search=Test”</code>。 </p> <p>您可以搜索“get all”方法返回的任何值。 </p> </td>
  </tr> 
 </tbody> 
</table>

### 响应

成功的响应 `200 OK` 返回数组中的数据，如下例所示。 如果 `404 Not found` 未找到站点ID或合作伙伴，则返回。

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
