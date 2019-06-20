---
description: 用于管理用户的REST API方法，包括创建、更新、列出、删除和返回用户对象。
seo-description: 用于管理用户的REST API方法，包括创建、更新、列出、删除和返回用户对象。
seo-title: 用户管理API方法
solution: Audience Manager
title: 用户管理API方法
uuid: 6e1f2c35-bb9 d-4166-b7 d4-d9 c5518 a61 ad
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# User Management API Methods {#user-management-api-methods}

Rest [!DNL API] methods to manage users, including creating, updating, listing, deleting, and returning user objects.

<!-- c_rest_api_user_man_user.xml -->

## Create a User {#create-user}

A `POST` method to create a new user.

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

If `isAdmin` is set to true, the user is created as a partner admin. 此属性还允许您了解用户是否是合作伙伴管理员。

Returns `409 Conflict` if the username is already taken.

## Update a User {#update-user}

A `PUT` method to update a user.

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

Returns `409 Conflict` if the username is already taken.

## Update Logged-In User {#update-logged-in-user}

A `PUT` method to update the currently logged-in user.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

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

Returns `409 Conflict` if the username is already taken.

## Update Logged-In User Password {#update-logged-in-user-pw}

A `PUT` method to update the currently logged-in user.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

### 请求

`POST /users/self/update-password`

### 示例请求正文

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Returns `200 OK` if successful. Returns `400 Bad Request` if something is wrong with either password.

## Reset Logged-In User Password {#reset-logged-in-user-pw}

A `PUT` method to reset the currently logged-in user. [!UICONTROL Audience Management] 向用户发送系统生成的密码。

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

### 请求

`POST /self/reset-password`

Returns `200 OK` if successful.

## Return User Object for a User ID {#return-user-object-for-id}

A `Get` method to return the user object for a User ID.

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

## Return User Object for Logged-In User {#return-user-object-for-logged-in-user}

A `Get` method to return the user object for the currently logged-in user.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

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

## List Users {#list-users}

A `GET` method to list users.

<!-- r_rest_api_user_list.xml -->

### 请求

`GET /api/v1/users/`

您可以在查询参数中指定多个用户组ID：

`GET /api/v1/users/?groupId=343&groupdId=12`

此查询返回指定组中所有用户的列表。

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

A `DELETE` method to delete a user.

<!-- r_rest_api_user_delete.xml -->

### 请求

`DELETE /api/v1/users/`*`<user_id>`*

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## Delete Users in Bulk {#delete-users-bulk}

A `POST` method to delete multiple users in bulk.

<!-- r_rest_api_user_delete_bulk.xml -->

### 请求

`POST /api/v1/users/bulk-delete`

### 示例请求正文

```
{[<user_id_1>, <user_id_2>, ...]}
```
