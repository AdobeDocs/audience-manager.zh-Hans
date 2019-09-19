---
description: 用于管理用户的其余API方法，包括创建、更新、列出、删除和返回用户对象。
seo-description: 用于管理用户的其余API方法，包括创建、更新、列出、删除和返回用户对象。
seo-title: 用户管理API方法
solution: Audience Manager
title: 用户管理API方法
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 用户管理API方法 {#user-management-api-methods}

其他 [!DNL API] 管理用户的方法，包括创建、更新、列出、删除和返回用户对象。

<!-- c_rest_api_user_man_user.xml -->

## Create a User {#create-user}

用于 `POST` 创建新用户的方法。

<!-- r_rest_api_user_create.xml -->

### 请求

`POST /api/v1/users/`

### 示例请求主体

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : true | false 
}
```

### 响应

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : <"true"|"false"> 
 
}
```

如果 `isAdmin` 设置为true，则用户将创建为合作伙伴管理员。 此属性还可让您了解用户是否为合作伙伴管理员。

返回 `409 Conflict` 用户名是否已使用。

## 更新用户 {#update-user}

一种 `PUT` 用于更新用户的方法。

<!-- r_rest_api_user_update.xml -->

### 请求

`PUT /api/v1/users/`*`<userId>`*

### 示例请求主体

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
}
```

### 响应

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

返回 `409 Conflict` 用户名是否已使用。

## 更新已登录用户 {#update-logged-in-user}

用 `PUT` 于更新当前登录用户的方法。

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>虽然大 [!DNL API] 多数方法只能由合作伙伴管理员调用，但此方法可由非管理员用户调用。

### 请求

`PUT /self/update`

### 示例请求主体

```
{  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

### 响应

```
{ 
  "userId": <integer>,,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string> 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

返回 `409 Conflict` 用户名是否已使用。

## 更新登录用户密码 {#update-logged-in-user-pw}

用 `PUT` 于更新当前登录用户的方法。

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>虽然大 [!DNL API] 多数方法只能由合作伙伴管理员调用，但此方法可由非管理员用户调用。

### 请求

`POST /users/self/update-password`

### 示例请求主体

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

成功 `200 OK` 时返回。 如果 `400 Bad Request` 任一密码出错，则返回。

## 重置登录用户密码 {#reset-logged-in-user-pw}

用 `PUT` 于重置当前登录用户的方法。 [!UICONTROL Audience Management] 向用户发送系统生成的密码。

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>虽然大 [!DNL API] 多数方法只能由合作伙伴管理员调用，但此方法可由非管理员用户调用。

### 请求

`POST /self/reset-password`

成功 `200 OK` 时返回。

## 返回用户ID的用户对象 {#return-user-object-for-id}

一 `Get` 种为用户ID返回用户对象的方法。

<!-- r_rest_api_user_get_user_obj.xml -->

### 请求

`GET /api/v1/users/`*`<userId>`*

### 响应

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## 为登录用户返回用户对象 {#return-user-object-for-logged-in-user}

一 `Get` 种为当前登录用户返回用户对象的方法。

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>虽然大 [!DNL API] 多数方法只能由合作伙伴管理员调用，但此方法可由非管理员用户调用。

### 请求

`GET /api/v1/users/self`

### 响应

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## 列出用户 {#list-users}

列 `GET` 出用户的方法。

<!-- r_rest_api_user_list.xml -->

### 请求

`GET /api/v1/users/`

您可以在查询参数中指定多个组ID:

`GET /api/v1/users/?groupId=343&groupdId=12`

此查询将返回指定组中所有用户的列表。

### 响应

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

## Delete a User {#delete-users}

一种 `DELETE` 删除用户的方法。

<!-- r_rest_api_user_delete.xml -->

### 请求

`DELETE /api/v1/users/`*`<user_id>`*

成功 `204 No Content` 时返回。 如果发生冲突，请返回 `409 Conflict`。

## 批量删除用户 {#delete-users-bulk}

一种 `POST` 批量删除多个用户的方法。

<!-- r_rest_api_user_delete_bulk.xml -->

### 请求

`POST /api/v1/users/bulk-delete`

### 示例请求主体

```
{[<user_id_1>, <user_id_2>, ...]}
```
