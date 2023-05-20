---
description: 說明在您的Audience Manager帳戶中，透過裝置相關變數來鎖定所有屬性中的使用者，可使用哪些常見的平台層級索引鍵值配對。
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: 使用平台级别关键值定位设备
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 5%

---

# 使用平台级别关键值定位设备 {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google已更新 [!DNL Google Chrome] 和所有 [!DNL Chromium] — 型瀏覽器，可透過將收集到的資訊減至最少 `User-Agent` 標頭。
>自2023年3月起，Audience Manager開始運用以下工具支援這些更新 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en). 若要繼續使用透過 `User-Agent` 標頭，您必須使用 [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 並啟用 [高平均資訊量使用者代理使用者端提示](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en).
>不支援這些更新 [DIL](../../../using/dil/dil-overview.md)，因此Audience Manager使用的客戶 [!DNL DIL] 將無法透過以下方式收集特徵資訊： `User-Agent` 標頭。

說明在您的Audience Manager帳戶中，透過裝置相關變數來鎖定所有屬性中的使用者，可使用哪些常見的平台層級索引鍵值配對。

## 平台層級變數的用途 {#platform-variables}

<!-- c_tb_device_targeting.xml -->

平台層級變數可讓您擷取從特定網站傳入的資料，並使其可用於在 [!DNL Audience Manager] 帳戶。 這些變數的構成方式 [機碼值組](../../reference/key-value-pairs-explained.md) 將索引鍵加上前置詞 `d_` 如下所示。

## 使用者代理程式定義的平台層級金鑰 {#keys-user-agent}

此 [!UICONTROL Data Collection Servers] 從以下專案擷取這些鍵的值： [使用者代理標題](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) 在 `HTTP` 要求。 值代表來自的裝置層級資訊 [!UICONTROL Device Atlas] 資料庫。 下表中的訊號可供使用，例如從使用者代理程式範例擷取的訊號。 [下載最常用索引鍵的清單](assets/device_keys.csv)，根據 [!UICONTROL Device Atlas] 測量。

| [!DNL Signal] | [!DNL Type] | [!DNL Example] |
|---|---|---|
| `d_device_vendor` | [!DNL VENDOR] | [!DNL apple] |
| `d_device_hardware_type` | [!DNL HARDWARE] | [!DNL mobile phone] |
| `d_device_os_version` | [!DNL OS VERSION] | [!DNL 5_0] |
| `d_device_os_name` | [!DNL OS NAME] | [!DNL ios] |
| `d_device_model` | [!DNL MODEL] | [!DNL iphone] |
| `d_device_marketing_name` | [!DNL MARKETING NAME] | [!DNL iphone] |
| `d_device_manufacturer` | [!DNL MANUFACTURER] | [!DNL apple] |

```
 Mozilla/5.0 (iPhone; CPU iPhone OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3
```

>[!NOTE]
>
>即使無法從使用者代理程式標頭中擷取一或多個訊號，其他訊號仍會傳遞至 [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)

