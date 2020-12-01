---
description: 使用GET或POST方法将数据发送到DCS API。
seo-description: 使用GET或POST方法将数据发送到DCS API。
seo-title: DCS API 方法
solution: Audience Manager
title: DCS API 方法
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 6%

---


# [!DNL DCS] [!DNL API] 方法 {#dcs-api-methods}

使用`GET`或`POST`方法将数据发送到[!DNL DCS] [!DNL API]。

可以使用`GET`或`POST`方法之一将数据发送到[!DNL DCS]。 请使用[curl](https://curl.haxx.se/)查看以下示例调用。 在所有三个示例调用中，我们将信号`c_likes = famous popstar`和`c_loves = famous actress`添加到设备用户档案`12345678901234567890123456789012345678`。

## 通过[!DNL GET] {#send-data-via-get}发送数据

请注意，`GET`调用的最大允许大小为8K。

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## 通过[!DNL POST] {#send-data-via-post}发送数据

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
