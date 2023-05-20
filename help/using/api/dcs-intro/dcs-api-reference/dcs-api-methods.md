---
description: 使用GET或POST方法將資料傳送至DCS API。
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: DCS API 方法
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 4%

---

# [!DNL DCS] [!DNL API] 方法 {#dcs-api-methods}

將資料傳送至 [!DNL DCS] [!DNL API] 使用 `GET` 或 `POST` 方法。

您可以將資料傳送至 [!DNL DCS] 使用其中一項 `GET` 或 `POST` 方法。 使用以下範例來檢視下列呼叫： [curl](https://curl.haxx.se/). 在所有三個呼叫範例中，我們都是新增訊號 `c_likes = famous popstar` 和 `c_loves = famous actress` 至裝置設定檔 `12345678901234567890123456789012345678`.

## 傳送資料管道 [!DNL GET] {#send-data-via-get}

請注意，允許的大小上限 `GET` 通話是8K。

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## 傳送資料管道 [!DNL POST] {#send-data-via-post}

注意使用傳送資料的需求 `POST` 方法：

* 允許的大小上限為32K。
* 將內容型別設定為 `application/x-www-form-urlencoded`.

### 呼叫範例

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
