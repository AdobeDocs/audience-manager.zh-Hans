---
description: 使用GET或POST方法将数据发送到DCS API。
seo-description: 使用GET或POST方法将数据发送到DCS API。
seo-title: DCS API方法
solution: Audience Manager
title: DCS API方法
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 0%

---


# DCS API方法 {#dcs-api-methods}

使用或方 [!DNL DCS] 法将 [!DNL API] 数据 `GET` 发送 `POST` 到。

您可以使用其中 [!DNL DCS] 一种或方法向 `GET` 发送 `POST` 数据。 使用curl查看下面的示例调 [用](https://curl.haxx.se/)。 在所有三个样本调用中，我们都在添加信 `c_likes = famous popstar` 号和 `c_loves = famous actress` 设备用户档案中 `12345678901234567890123456789012345678`。


## 通过GET发送数据 {#send-data-via-get}

请注意，呼叫的最大允 `GET` 许大小为8K。

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## 通过POST发送数据 {#send-data-via-post}

请注意使用以下方法发送数据 `POST` 的要求：

* 允许的最大大小为32K。
* 将内容类型设置为 `application/x-www-form-urlencoded`。

### 示例调用

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
