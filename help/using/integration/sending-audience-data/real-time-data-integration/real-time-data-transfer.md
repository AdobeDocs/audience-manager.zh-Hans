---
description: 即時傳入資料擷取程式會使用使用者瀏覽器發出的一系列HTTP請求，將資料傳遞至Audience Manager。
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: 实时入站数据摄取
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 5%

---

# 实时入站数据摄取 {#real-time-inbound-data-ingestion}

即時傳入資料擷取程式會使用一系列 `HTTP` 從使用者的瀏覽器要求傳遞資料給Audience Manager。

<!-- c_rt_inbound_real_time.xml -->

傳入資料的格式應設為稱為訊號的機碼值組。 通常，每個訊號都會對應至透過使用者介面建立或管理的區段，或者 [!DNL API].

## URL字串引數和語法 {#url-string-syntax}

此 [!DNL URL] 傳入資料傳輸應包含下述變數。 記住 [建立特徵](../../../features/traits/create-onboarded-rule-based-traits.md) 和 [資料夾結構](../../../features/traits/trait-storage.md#create-trait-storage-folder) 在 [!DNL Audience Manager] 設定即時資料傳輸之前的UI。

>[!NOTE]
>
>以實際引數值取代斜體內容。

| 参数 | 描述 |
|---|---|
| `<KEY>` | 機碼值組中的唯一識別碼（例如性別、顏色、價格）。 |
| `<VAL>` | 屬於索引鍵所定義資料集的變數（例如，性別=男性，顏色=綠色，價格=100） |

### URL語法

在即時傳入資料擷取程式期間，正確格式化 [!DNL URL] 字串會使用以下語法：

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
