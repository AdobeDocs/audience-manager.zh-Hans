---
description: 特徵存留時間(TTL)間隔對區段會籍有何影響。
seo-description: How trait time-to-live (TTL) interval affects segment membership.
seo-title: Segment and Trait Time to Live Explained
solution: Audience Manager
title: 區段存留時間說明
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 3%

---

# 区段和特征存留期说明 {#segment-time-to-live-explained}

如何特徵 [!UICONTROL time-to-live] ([!DNL TTL])間隔會影響區段成員資格。

<!-- segment-ttl-explained.xml -->

## 存留時間

[!DNL TTL] 定義網站訪客在最後一個特徵資格事件後會在區段中停留多久。 [!DNL TTL] 是针对特征而非区段设置的。如果訪客在區段結束前不符合特徵資格，就會從區段中流失 [!DNL TTL] 間隔。 預設 [!DNL TTL] 新特徵為120天。 設為0天時，特徵永不過期。 [設定TTL值](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) 當您在中建立或編輯特徵時 [!UICONTROL Advanced Options] 特徵建立介面的區段。

### 1天TTL說明

設定時 [!DNL TTL] 到1天時，TTL計時器在特徵實現後的第二天開始，不計算特徵實現當天的剩餘時數。

Audience Manager計算 [!DNL TTL] 1天特徵的有效期 [!DNL TTL] 根據下列公式：

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **範例1**：在1:00實現的特徵 [!DNL UTC]，含1天 [!DNL TTL]. [!DNL TTL] 將在24 + 24 - 1 = 47小時後過期。
* **範例2**：23:00實現的特徵 [!DNL UTC]，含1天 [!DNL TTL]. [!DNL TTL] 將在24 + 24 - 23 = 25小時後過期。

## [!DNL TTL] 和從區段中移除

如果使用者不符合區段內任何特徵的資格，則會退出區段。 [!DNL TTL] 間隔。 例如，如果您有1個特徵區段且30天 [!DNL TTL]，如果使用者在未來30天內再次不符合特徵資格，則會退出該區段。

![](assets/ttl-explained.png)

## [!DNL TTL] 和區段續約

此 [!DNL TTL] 會重設，而使用者符合該區段特徵在 [!DNL TTL] 句點。 此外，由於大部分割槽段都包含多個自身的特徵 [!DNL TTL] 間隔，使用者可以留在區段中，並重設 [!DNL TTL] 間隔，只要他們持續符合與該區段相關聯的任何特徵的資格。

例如，假設您有區段1由特徵A組成（30天） [!DNL TTL])和特徵B (15天 [!DNL TTL])。 假設訪客僅符合每個特徵一次，下圖會概述 [!DNL TTL] 續約程式與總區段內持續時間。

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL獨立於第三方TTL設定

請記住， [!DNL TTL] 設定在您的 [!DNL Audience Manager] 畫素獨立於 [!DNL TTL] 設定於第三方使用的其他畫素([!DNL DSP]s、廣告網路等)。

>[!MORELIKETHIS]
>
>* [設定特徵過期時間間隔](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

