---
description: 用于管理用户的REST API方法，包括创建、更新、列出、删除和返回用户对象。
seo-description: 用于管理用户的REST API方法，包括创建、更新、列出、删除和返回用户对象。
seo-title: 用户管理 API 方法
solution: Audience Manager
title: 用户管理 API 方法
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
exl-id: c015c42c-63c7-4392-9fef-f48dc787a56f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 7%

---

# 用户管理 API 方法 {#user-management-api-methods}

Rest [!DNL API]方法用于管理用户，包括创建、更新、列出、删除和返回用户对象。

<!-- c_rest_api_user_man_user.xml -->

## 创建用户{#create-user}

用于创建新用户的`POST`方法。

<!-- r_rest_api_user_create.xml -->

### 请求

`POST /api/v1/users/`

### 示例请求正文

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

如果将`isAdmin`设置为true，则创建用户作为合作伙伴管理员。 此属性还可让您知道用户是否为合作伙伴管理员。

如果用户名已采用，则返回`409 Conflict`。

## 更新用户{#update-user}

用于更新用户的`PUT`方法。

<!-- r_rest_api_user_update.xml -->

### 请求

`PUT /api/v1/users/`*`<userId>`*

### 示例请求正文

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

如果用户名已采用，则返回`409 Conflict`。

## 更新登录用户{#update-logged-in-user}

`PUT`方法，用于更新当前已登录的用户。

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>大多数[!DNL API]方法只能由合作伙伴管理员调用，而此方法可由非管理员用户调用。

### 请求

`PUT /self/update`

### 示例请求正文

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

如果用户名已采用，则返回`409 Conflict`。

## 更新登录用户密码{#update-logged-in-user-pw}

`PUT`方法，用于更新当前已登录的用户。

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>大多数[!DNL API]方法只能由合作伙伴管理员调用，而此方法可由非管理员用户调用。

### 请求

`POST /users/self/update-password`

### 示例请求正文

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

如果成功，则返回`200 OK`。 如果两个密码都出错，则返回`400 Bad Request`。

## 重置登录用户密码{#reset-logged-in-user-pw}

用于重置当前已登录用户的`PUT`方法。 [!UICONTROL Audience Management] 向用户发送系统生成的密码。

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>大多数[!DNL API]方法只能由合作伙伴管理员调用，而此方法可由非管理员用户调用。

### 请求

`POST /self/reset-password`

如果成功，则返回`200 OK`。

## 返回用户ID {#return-user-object-for-id}的用户对象

用于返回用户ID的用户对象的`Get`方法。

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

## 返回登录用户{#return-user-object-for-logged-in-user}的用户对象

`Get`方法，用于返回当前已登录用户的用户对象。

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>大多数[!DNL API]方法只能由合作伙伴管理员调用，而此方法可由非管理员用户调用。

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

## 列出用户{#list-users}

用于列出用户的`GET`方法。

<!-- r_rest_api_user_list.xml -->

### 请求

`GET /api/v1/users/`

您可以在查询参数中指定多个组ID:

`GET /api/v1/users/?groupId=343&groupdId=12`

此查询会返回指定组中所有用户的列表。

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

## 删除用户{#delete-users}

用于删除用户的`DELETE`方法。

<!-- r_rest_api_user_delete.xml -->

### 请求

`DELETE /api/v1/users/`*`<user_id>`*

如果成功，则返回`204 No Content`。 如果发生冲突，则返回`409 Conflict`。

## 批量{#delete-users-bulk}删除用户

批量删除多个用户的`POST`方法。

<!-- r_rest_api_user_delete_bulk.xml -->

### 请求

`POST /api/v1/users/bulk-delete`

### 示例请求正文

```
{[<user_id_1>, <user_id_2>, ...]}
```
