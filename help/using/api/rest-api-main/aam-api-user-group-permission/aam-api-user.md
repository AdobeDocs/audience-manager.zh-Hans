---
description: 用於管理使用者的Rest API方法，包括建立、更新、列出、刪除和傳回使用者物件。
seo-description: Rest API methods to manage users, including creating, updating, listing, deleting, and returning user objects.
seo-title: User Management API Methods
solution: Audience Manager
title: 用户管理 API 方法
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
exl-id: c015c42c-63c7-4392-9fef-f48dc787a56f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 6%

---

# 用户管理 API 方法 {#user-management-api-methods}

Rest [!DNL API] 管理使用者的方法，包括建立、更新、列出、刪除和傳回使用者物件。

<!-- c_rest_api_user_man_user.xml -->

## 建立使用者 {#create-user}

A `POST` 方法來建立新使用者。

<!-- r_rest_api_user_create.xml -->

### 请求

`POST /api/v1/users/`

### 範例要求內文

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

若 `isAdmin` 若設為true，則會將使用者建立為合作夥伴管理員。 此屬性也可讓您知道使用者是否為合作夥伴管理員。

傳回 `409 Conflict` 如果使用者名稱已被使用。

## 更新使用者 {#update-user}

A `PUT` 更新使用者的方法。

<!-- r_rest_api_user_update.xml -->

### 请求

`PUT /api/v1/users/`*`<userId>`*

### 範例要求內文

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

傳回 `409 Conflict` 如果使用者名稱已被使用。

## 更新登入使用者 {#update-logged-in-user}

A `PUT` 更新目前登入使用者的方法。

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>反之，最多 [!DNL API] 方法只能由合作夥伴管理員呼叫，此方法則可由非管理員使用者呼叫。

### 请求

`PUT /self/update`

### 範例要求內文

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

傳回 `409 Conflict` 如果使用者名稱已被使用。

## 更新登入使用者密碼 {#update-logged-in-user-pw}

A `PUT` 更新目前登入使用者的方法。

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>反之，最多 [!DNL API] 方法只能由合作夥伴管理員呼叫，此方法則可由非管理員使用者呼叫。

### 请求

`POST /users/self/update-password`

### 範例要求內文

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

傳回 `200 OK` 如果成功。 傳回 `400 Bad Request` 如果任一密碼發生錯誤。

## 重設登入使用者密碼 {#reset-logged-in-user-pw}

A `PUT` 重設目前登入使用者的方法。 [!UICONTROL Audience Management] 會將系統產生的密碼傳送給使用者。

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>反之，最多 [!DNL API] 方法只能由合作夥伴管理員呼叫，此方法則可由非管理員使用者呼叫。

### 请求

`POST /self/reset-password`

傳回 `200 OK` 如果成功。

## 傳回使用者ID的使用者物件 {#return-user-object-for-id}

A `Get` 傳回使用者ID的使用者物件的方法。

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

## 傳回已登入使用者的使用者物件 {#return-user-object-for-logged-in-user}

A `Get` 方法，傳回目前登入的使用者的使用者物件。

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>反之，最多 [!DNL API] 方法只能由合作夥伴管理員呼叫，此方法則可由非管理員使用者呼叫。

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

## 列出使用者 {#list-users}

A `GET` 列出使用者的方法。

<!-- r_rest_api_user_list.xml -->

### 请求

`GET /api/v1/users/`

您可以在查詢引數中指定多個群組ID：

`GET /api/v1/users/?groupId=343&groupdId=12`

此查詢會傳回指定群組中的所有使用者清單。

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

## 刪除使用者 {#delete-users}

A `DELETE` 刪除使用者的方法。

<!-- r_rest_api_user_delete.xml -->

### 请求

`DELETE /api/v1/users/`*`<user_id>`*

傳回 `204 No Content` 如果成功。 在衝突的情況下返回 `409 Conflict`.

## 大量刪除使用者 {#delete-users-bulk}

A `POST` 大量刪除多個使用者的方法。

<!-- r_rest_api_user_delete_bulk.xml -->

### 请求

`POST /api/v1/users/bulk-delete`

### 範例要求內文

```
{[<user_id_1>, <user_id_2>, ...]}
```
