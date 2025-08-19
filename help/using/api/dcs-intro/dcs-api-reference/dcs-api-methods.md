---
description: 使用GET或POST方法将数据发送到DCS API。
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: DCS API方法
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---

# [!DNL DCS] [!DNL API]方法 {#dcs-api-methods}

使用[!DNL DCS]或[!DNL API]方法将数据发送到`GET` `POST`。

您可以使用[!DNL DCS]或`GET`方法之一将数据发送到`POST`。 使用[curl](https://curl.haxx.se/)查看下面的示例调用。 在所有三个示例调用中，我们将信号`c_likes = famous popstar`和`c_loves = famous actress`添加到设备配置文件`12345678901234567890123456789012345678`。

## 通过[!DNL GET]发送数据 {#send-data-via-get}

请注意，`GET`调用允许的最大大小为8K。

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## 通过[!DNL POST]发送数据 {#send-data-via-post}

请注意使用`POST`方法发送数据的要求：

* 允许的最大大小为32K。
* 将内容类型设置为`application/x-www-form-urlencoded`。

### 示例调用

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
