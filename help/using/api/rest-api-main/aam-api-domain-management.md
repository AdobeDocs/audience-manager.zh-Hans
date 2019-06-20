---
description: 域管理方法，允许您创建和管理要向其发送数据的域(仅限cookie目标)。
seo-description: 域管理方法，允许您创建和管理要向其发送数据的域(仅限cookie目标)。
seo-title: 域管理API方法
solution: Audience Manager
title: 域管理API方法
uuid: f2f08bc5-ea42-4171-9a43-0b20976 f0 cb0
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Domain Management API Methods {#domain-management-api-methods}

域管理方法，允许您创建和管理要向其发送数据的域(仅限cookie目标)。

<!-- c_partner_site.xml -->

## Create a New Domain {#create-new-domain}

A `POST` method that lets you create a new domain for (cookie destinations only).

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

A successful response returns `201 created` and the partner site, including its unique ID.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Delete a Domain {#delete-domain}

A `DELETE` method that lets you remove a domain (for cookie destinations only).

<!-- r_delete_partner_site.xml -->

### 请求

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 响应

A successful response returns `204 no content`. Returns `404 not found` if the partner site cannot be found.

## Return Properties for a Domain {#return-props-domain}

A `GET` method that returns details about the specified domain (for cookie destinations only).

<!-- r_get_partner_site.xml -->

### 请求

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 响应

A successful response returns `200 OK` and data as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Return Properties for all Domains {#return-props-all-domains}

A `GET` method that returns information about all your domains (for cookie destinations only).

<!-- r_get_partner_sites.xml -->

### 请求

`GET https://api.demdex.com/v1/partner-sites/`

### 可选查询参数

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. See [Optional Parameters](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> 按页码返回结果。编号从开始开始。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> 设置请求返回的响应结果数(默认为10)。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> SortBy</code> </td> 
   <td colname="col2"> 根据指定的JSON属性对结果进行排序和返回。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> 降序</code> </td>
   <td colname="col2"> 按降序排序并返回结果。默认为升序。 </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">返回基于要用作搜索参数的指定字符串的结果。例如，假设您要查找在该项目的任何值字段中具有“测试”字样的所有模型的结果。您的示例请求可能如下所示： <p><code> “GET''https://api.demdex.com/v1/models/?search=Test</code>'。 </p> <p>您可以搜索由“get all”方法返回的任何值。 </p> </td>
  </tr> 
 </tbody> 
</table>

### 响应

A successful response returns `200 OK` and data in an array as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

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
