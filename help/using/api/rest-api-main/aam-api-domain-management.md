---
description: 域管理方法，用于创建和管理要向其发送数据的域（仅适用于Cookie目标）。
seo-description: 域管理方法，用于创建和管理要向其发送数据的域（仅适用于Cookie目标）。
seo-title: 域管理 API 方法
solution: Audience Manager
title: 域管理 API 方法
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 6%

---

# 域管理 API 方法 {#domain-management-api-methods}

域管理方法，用于创建和管理要向其发送数据的域（仅适用于Cookie目标）。

<!-- c_partner_site.xml -->

## 创建新域{#create-new-domain}

`POST`方法，允许您为（仅限Cookie目标）创建新域。

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

成功的响应会返回`201 created`和合作伙伴网站，包括其唯一ID。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 删除域{#delete-domain}

`DELETE`方法，用于删除域（仅用于Cookie目标）。

<!-- r_delete_partner_site.xml -->

### 请求

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 响应

成功的响应返回`204 no content`。 如果找不到合作伙伴网站，则返回`404 not found`。

## 返回域{#return-props-domain}的属性

`GET`方法，可返回有关指定域的详细信息（仅适用于Cookie目标）。

<!-- r_get_partner_site.xml -->

### 请求

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 响应

成功的响应会返回`200 OK`和数据，如以下示例所示。 如果找不到网站ID或合作伙伴，则返回`404 Not found`。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 返回所有域{#return-props-all-domains}的属性

一种`GET`方法，可返回有关所有域的信息（仅适用于Cookie目标）。

<!-- r_get_partner_sites.xml -->

### 请求

`GET https://api.demdex.com/v1/partner-sites/`

### 可选查询参数

您可以将这些可选参数与返回对象&#x200B;*所有*&#x200B;属性的[!DNL API]方法一起使用。 将查询传递到[!DNL API]时，在请求字符串中设置这些选项。 请参阅[可选参数](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)。

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
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 按降序排序和返回结果。 默认为升序。 </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">根据要用作搜索参数的指定字符串返回结果。 例如，假设您希望在该项目的任何值字段中查找包含“Test”字样的所有模型的结果。 您的示例请求可能如下所示： <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>您可以搜索“get all”方法返回的任何值。 </p> </td>
  </tr> 
 </tbody> 
</table>

### 响应

成功的响应会返回`200 OK`和数组中的数据，如以下示例所示。 如果找不到网站ID或合作伙伴，则返回`404 Not found`。

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
