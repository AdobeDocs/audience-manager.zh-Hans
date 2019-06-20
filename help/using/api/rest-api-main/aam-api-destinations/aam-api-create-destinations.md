---
description: 使用这些RESTful API方法创建目标。
seo-description: 使用这些RESTful API方法创建目标。
seo-title: 创建目标
solution: Audience Manager
title: 创建目标
uuid: 12f04151-ad0 e-4cb6-8f3 b-b5 c427 dc2 cf
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create Destinations {#create-destinations}

Create destinations with these [!UICONTROL RESTful API] methods.

<!-- c_create_destinations.xml -->

## 支持的目标类型：仅URL和Cookie

The available `POST` methods let you create [!UICONTROL URL] and [!UICONTROL cookie destinations] only. Currently, you cannot create [!UICONTROL server-to-server destinations] with these [!DNL REST API] methods. However, the related destination `GET` methods let you retrieve information about [!UICONTROL server-to-server destinations] created in the user interface.

>[!MORE_ LIKE_ This]
>
>* [目标](../../../features/destinations/destinations.md#destination-api-methods)
>* [目标序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [键值对解释](../../../reference/key-value-pairs-explained.md)


## Create a Non-Serial URL Destination {#create-nonserial-dest}

A `POST` method that lets you create a destination that accepts segments composed of single key-value pairs (e.g., `gender=male` or `gender=female`).

<!-- r_create_nonserial_destination.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`

### 示例请求

此请求创建单个目标。除非另外指明，否则所有请求值都是必需的。

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### 响应

A successful request returns `201 created` and the destination.

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

>[!MORE_ LIKE_ This]
>
>* [目标序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)


## Create a Serialized URL Destination {#create-serial-url-dest}

A `POST` method that lets you create a destination that accepts multiple values associated with a single key (e.g., `color=blue, red, green`).

<!-- r_create_serial_url_destination.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`

### 示例请求

Specify the secure [!DNL URL] and delimiter for the key-value pair passed in to the destination. 除非另外指明，否则所有请求值都是必需的。

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

A successful update returns response code `201 created` and the destination.

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

>[!MORE_ LIKE_ This]
>
>* [目标序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)


## Create a Cookie Destination: Single-Key, Non-Serialized {#create-cookie-dest-single}

A `POST` method that lets you create a [!UICONTROL cookie destination] that accepts segments composed of single key-value pairs (e.g., `gender=male` or `gender=female`).

<!-- r_cookie_destination_singlekey_noserial.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`

### 示例请求

除非另外指明，否则所有请求值都是必需的。

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

A successful update returns response code `201 created` and the destination.

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

>[!MORE_ LIKE_ This]
>
>* [目标序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [键值对解释](../../../reference/key-value-pairs-explained.md)


## Create a Cookie Destination: Single Key, Serialized {#create-cookie-dest-single-serial}

A `POST` method that lets you create a destination that accepts multiple values associated with a single key (e.g., `color=blue, red, green`).

<!-- r_cookie_destination_singlekey_serial.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`

### 示例请求

除非另外指明，否则所有请求值都是必需的。

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

A successful update returns response code `201 created` and the destination.

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

>[!MORE_ LIKE_ This]
>
>* [目标序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [键值对解释](../../../reference/key-value-pairs-explained.md)


## Create a Cookie Destination: Multi-Key, Non-Serialized {#create-cookie-dest-multi}

A `POST` method that lets you create a destination that accepts segments that contain multiple keys with different values (e.g., `gender=male; gender=female; color=blue; color=red`).

<!-- r_create_cookie_multikey_noserial.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`

### 示例请求

除非另外指明，否则所有请求值都是必需的。

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

A successful update returns response code `201 created` and the destination.

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

## Create a Cookie Destination: Multi-Key, Serialized {#create-cookie-dest-multi-serial}

A `POST` method that lets you create a destination that accepts segments that contain multiple keys and values (e.g., `gender=male, female; color=blue, red, green`).

<!-- r_cookie_destination_multikey_serial.xml -->

### 请求

`POST https://api.demdex.com/v1/destinations/`

### 示例请求

除非另外指明，否则所有请求值都是必需的。

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

A successful update returns response code `201 created` and the destination.

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

>[!MORE_ LIKE_ This]
>
>* [目标序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [键值对解释](../../../reference/key-value-pairs-explained.md)

