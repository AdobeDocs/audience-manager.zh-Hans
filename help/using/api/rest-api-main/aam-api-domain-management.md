---
description: 可用于创建和管理要发送数据的域的域管理方法（仅适用于 Cookie 目标）。
seo-description: Domain management methods that let you create and manage the domains to which you want to send data (for cookie destinations only).
seo-title: Domain Management API Methods
solution: Audience Manager
title: 域管理 API 方法
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 5%

---

# 域管理 API 方法 {#domain-management-api-methods}

可用于创建和管理要发送数据的域的域管理方法（仅适用于 Cookie 目标）。

<!-- c_partner_site.xml -->

## 建立新網域 {#create-new-domain}

`POST`允许您为（仅 Cookie 目标）创建新域的方法。

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

成功的响应返回 `201 created` 和合作伙伴网站，包括其唯一 ID。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 删除域 {#delete-domain}

`DELETE`允许您删除域的方法（仅适用于 Cookie 目标）。

<!-- r_delete_partner_site.xml -->

### 请求

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 响应

成功的响应返回 `204 no content` 。 傳回 `404 not found` 如果找不到合作夥伴網站。

## 返回域属性 {#return-props-domain}

`GET`返回有关指定域的详细信息的方法（仅适用于 Cookie 目标）。

<!-- r_get_partner_site.xml -->

### 请求

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 响应

成功的响应返回 `200 OK` 和数据，如以下示例所示。 如果找不到网站 ID 或合作伙伴，则返回 `404 Not found` 。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 返回所有域的属性 {#return-props-all-domains}

`GET`返回有关所有域的信息的方法（仅适用于 Cookie 目标）。

<!-- r_get_partner_sites.xml -->

### 请求

`GET https://api.demdex.com/v1/partner-sites/`

### 可选查询参数

您可以使用這些選擇性引數搭配 [!DNL API] 傳回的方法 *全部* 物件的屬性。 將查詢傳入時，在請求字串中設定這些選項 [!DNL API]. 另請參閱 [選擇性引數](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> 按页面数字返回结果。 编号从0开始。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> 设置请求返回的响应结果数（默认值为10）。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> 根据指定的 JSON 属性对结果进行排序和返回。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 按降序排序和返回结果。 "升序" 为默认值。 </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">返回基于您要用作搜索参数的指定字符串的结果。 例如，假设您要查找该项目的任何值字段中包含 "Test" 一词的所有模型的结果。 您的示例请求可能点赞如下： <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>您可以搜尋「get all」方法傳回的任何值。 </p> </td>
  </tr> 
 </tbody> 
</table>

### 响应

成功的响应返回 `200 OK` 和数组中的数据，如下面的示例所示。 如果找不到网站 ID 或合作伙伴，则返回 `404 Not found` 。

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
