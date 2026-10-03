---
description: 使用GET或POST方法将数据发送到DCS API。
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: DCS API方法
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
TQID: 'https://experienceleague.adobe.com/dERIW4EM4-oMg8p33N2dtDy5BBw3jF1BCQJstW2cZTY'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
    internal-label: Data Collection Server
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 0%
---
# [!DNL DCS] [!DNL API]方法 {#dcs-api-methods}

使用`GET`或`POST`方法将数据发送到[!DNL DCS] [!DNL API]。

您可以使用`GET`或`POST`方法之一将数据发送到[!DNL DCS]。 使用[curl](https://curl.haxx.se/)查看下面的示例调用。 在所有三个示例调用中，我们将信号`c_likes = famous popstar`和`c_loves = famous actress`添加到设备配置文件`12345678901234567890123456789012345678`。

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
