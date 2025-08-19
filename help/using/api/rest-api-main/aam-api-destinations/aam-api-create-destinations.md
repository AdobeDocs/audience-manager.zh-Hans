---
description: 使用这些RESTful API方法创建目标。
seo-description: Create destinations with these RESTful API methods.
seo-title: Create Destinations
solution: Audience Manager
title: 创建目标
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
feature: API
exl-id: bae0f304-0ff3-4c5f-b432-19aef61d9d10
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 6%

---

# 创建目标 {#create-destinations}

使用这些[!UICONTROL RESTful API]方法创建目标。

<!-- c_create_destinations.xml -->

## 支持的目标类型：仅URL和Cookie

可用的`POST`方法仅允许您创建[!UICONTROL URL]和[!UICONTROL cookie destinations]。 目前，无法使用这些[!UICONTROL server-to-server destinations]方法创建[!DNL REST API]。 但是，相关目标`GET`方法允许您检索有关在用户界面中创建的[!UICONTROL server-to-server destinations]的信息。

## 创建非串行URL目标 {#create-nonserial-dest}

一种`POST`方法，可让您创建接受由单个键值对（如`gender=male`或`gender=female`）组成的区段的目标。

<!-- r_create_nonserial_destination.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`

### 示例请求

此请求创建一个目标。 除非另有说明，否则所有请求值都是必需的。

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### 响应

成功的请求返回`201 created`和目标。

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4033, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (not serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"ACTIVE", 
   "destinationType":"PUSH", 
   "createTime":1338937116000, 
   "updateTime":1338937116000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":false, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "delimiter":null,
   "mappings":null
} 
```

## 创建序列化URL目标 {#create-serial-url-dest}

一种`POST`方法，可让您创建接受与单个键（如`color=blue, red, green`）关联的多个值的目标。

<!-- r_create_serial_url_destination.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`

### 示例请求

为传递到目标的键值对指定安全[!DNL URL]和分隔符。 除非另有说明，否则所有请求值都是必需的。

```
{ 
   "name":"Sample URL Destination (Serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":true,
   "urlFormatString":"https://www.adobe.com/send?data=%ALIAS%",
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%",
   "delimiter":","
}
```

### 响应

成功更新将返回响应代码`201 created`和目标。

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4034, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (Serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"active", 
   "destinationType":"PUSH", 
   "createTime":1338937420000, 
   "updateTime":1338937420000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":true, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%", 
   "delimiter":"-", 
   "mappings":null 
}
```

## 创建Cookie目标：单键，非序列化 {#create-cookie-dest-single}

一种`POST`方法，可让您创建接受由单键值对（如[!UICONTROL cookie destination]或`gender=male`）组成的区段的`gender=female`。

<!-- r_cookie_destination_singlekey_noserial.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`

### 示例请求

除非另有说明，否则所有请求值都是必需的。

```
{ 
   "name":"Cookie Destination Single Key Not Serialized",
   "destinationType":"ADS",
   "adServerTypeID":1,
   "cookieName":"adobe",
   "cnameDomain":"adobe.com",
   "maxSize":"2048",
   "ttl":"0",
   "domainRestrictions":"inclusion",
   "siteIDs":[
      312
   ],
   "formatType":"single_key",
   "singleKey":"key",
   "keySeparator":"=",
   "valueSeparator":",",
   "serializationEnabled":false
}
```

### 响应

成功更新将返回响应代码`201 created`和目标。

```
{ 
   "destinationType":"ADS", 
   "destinationId":4035, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Not Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338937984000, 
   "updateTime":1338937984000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"inclusion", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"key", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
      312 
   ], 
   "uparamEnabled":false
} 
```

## 创建Cookie目标：单键，序列化 {#create-cookie-dest-single-serial}

一种`POST`方法，可让您创建接受与单个键（如`color=blue, red, green`）关联的多个值的目标。

<!-- r_cookie_destination_singlekey_serial.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`

### 示例请求

除非另有说明，否则所有请求值都是必需的。

```
{ 
   "name":"Cookie Destination Single Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
 
   ], 
   "formatType":"single_key", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### 响应

成功更新将返回响应代码`201 created`和目标。

```
{ 
   "destinationType":"ADS", 
   "destinationId":4036, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938329000, 
   "updateTime":1338938329000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false
}
```

## 创建Cookie目标：多键，非序列化 {#create-cookie-dest-multi}

一种`POST`方法，可让您创建一个目标，以接受包含具有不同值（例如，`gender=male; gender=female; color=blue; color=red`）的多个键的区段。

<!-- r_create_cookie_multikey_noserial.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`

### 示例请求

除非另有说明，否则所有请求值都是必需的。

```
{ 
   "name":"Ad Server Multi-Key Not Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
  
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":false 
}
```

### 响应

成功更新将返回响应代码`201 created`和目标。

```
{ 
   "destinationType":"ADS", 
   "destinationId":4037, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Not Serialized", 
   "status":1, 
   "destinationType":"ADS", 
   "createTime":1338938666000, 
   "updateTime":1338938666000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
  
   ], 
   "uparamEnabled":false 
}
```

## 创建Cookie目标：多键，序列化 {#create-cookie-dest-multi-serial}

一种`POST`方法，可让您创建接受包含多个键和值（如`gender=male, female; color=blue, red, green`）的区段的目标。

<!-- r_cookie_destination_multikey_serial.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`

### 示例请求

除非另有说明，否则所有请求值都是必需的。

```
{ 
   "name":"Cookie Destination Multi-Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains",
   "siteIDs":[ 
 
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### 响应

成功更新将返回响应代码`201 created`和目标。

```
{ 
   "destinationType":"ADS", 
   "destinationId":4038, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938872000, 
   "updateTime":1338938872000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false 
}
```

>[!MORELIKETHIS]
>
>* [目标](../../../features/destinations/destinations.md)
>* [目标序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [键值对说明](../../../reference/key-value-pairs-explained.md)
