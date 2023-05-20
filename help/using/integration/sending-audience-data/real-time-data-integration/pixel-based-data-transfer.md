---
description: 簡單畫素（可用來讓使用者符合特徵資格）可執行即時資料傳輸。 Audience Manager介面可讓使用者端自行建立任意數量的畫素。 畫素字串包含簡單ID或索引鍵值配對。
seo-description: Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.
seo-title: Pixel-based Data Transfers
solution: Audience Manager
title: 基于像素的数据传输
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 4%

---

# 基于像素的数据传输 {#pixel-based-data-transfers}

簡單畫素（可用來讓使用者符合特徵資格）可執行即時資料傳輸。 Audience Manager介面可讓使用者端自行建立任意數量的畫素。 畫素字串包含簡單ID或索引鍵值配對。

<!-- c_rt_inbound_pixel_transfers.xml -->

若要啟用傳入資料傳輸，供應商和使用者端會：

1. 決定您希望廠商或合作夥伴引發哪些特徵。
1. 取得特徵的畫素。 在特徵清單畫面中，將游標暫留在 **[!UICONTROL Actions]** 欄並按一下 **[!UICONTROL Get trait URL]** 所需特徵的符號。
1. 提供 [!DNL URL] 至廠商或合作夥伴。

## 示例

此基本事件呼叫會將特徵ID 1234傳送至 [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

您可以在事件呼叫中序列化特徵ID，以協助減少 `HTTP` 來自頁面的流量。 將其他特徵ID附加至URL字串，如下列範例所示：

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
