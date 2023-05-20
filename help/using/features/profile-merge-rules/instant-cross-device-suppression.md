---
description: 当有多个设备与用户连接时，如果在其中任一设备上产生了特定体验，“即时跨设备抑制”功能会禁止这些设备上的用户。使用这项“即时跨设备抑制”功能，可为您的用户提供一致的跨设备体验。Audience Manager 中的实时取消区段功能可提供这种体验。
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: 即时跨设备抑制
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 9%

---

# 即时跨设备抑制 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 當任何裝置發生特定體驗時，能夠跨連線至使用者的多個裝置隱藏使用者。 使用 [!UICONTROL Instant Cross-Device Suppression] 可跨裝置為使用者提供一致的體驗。 Audience Manager 中的实时取消区段功能可提供这种体验。

## 概述 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 提供兩個主要使用案例：改善使用者體驗和媒體效率。

* **改善的使用者體驗**：已購買您的產品或服務的使用者所看到的創意與購買前不同。 反之，您可以針對您知道他們尚未購買的產品或服務，顯示追加銷售或交叉銷售訊息。
* **媒體效率**：透過對全部套用全域頻率上限來最佳化行銷活動支出 [!DNL DSP]s.頻率上限可針對屬於使用者的多個裝置即時執行。

即時取消細分的技術詳細資訊詳見 [設定檔合併規則與裝置取消細分程式](merge-rule-unsegment.md). 請閱讀並實際實施上述使用案例。

## 轉換後不要鎖定目標 {#do-not-target-once}

確保您已轉換的使用者（購買產品、取得訂閱等） 不會看到與轉換前相同的訊息。 您可使用取得此資訊： [!UICONTROL AND NOT] 邏輯，如下所示。

1. 使用兩個特徵建立區段，並使用 [!UICONTROL AND NOT] 邏輯，如下圖所示。 您必須使用規則型特徵來定義轉換事件，以便即時觸發取消細分動作。 深入瞭解如何 [建立規則型特徵](../traits/create-onboarded-rule-based-traits.md).
2. 將區段對應至任意數量的即時伺服器對伺服器目的地。 閱讀如何新增區段至 [伺服器對伺服器目的地](../destinations/add-edit-segments.md).

只要您的訪客尚未轉換，即符合區段的資格。 當符合轉換特徵資格時，他們就會停止遵循區段規則，並立即從區段移除。

![](assets/and_not_use_case.png)

## X次曝光後不要鎖定目標 {#do-not-target-after-x}

您可以設定造訪間隔和頻率控制，確保使用者不會受到相同創意內容的影響。 在此案例中，請依照下列步驟概述，建立具有兩個特徵的區段。

1. 使用兩個特徵建立區段，並使用 [!UICONTROL AND] 邏輯，如下圖所示。 您必須使用規則型特徵來定義曝光事件，以便即時觸發取消區段。 深入瞭解如何 [建立規則型特徵](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >您可以使用 [!UICONTROL Actionable Log Files] 或 [!UICONTROL Pixel Calls] ，以根據使用者曝光數建立特徵。 深入瞭解 [可操作的記錄檔](../../integration/media-data-integration/actionable-log-files.md) 和 [畫素呼叫](../../integration/media-data-integration/impression-data-pixels.md).
2. 將頻率控制項套用至第二個特徵。 您也可以視需要新增造訪間隔控制項。 深入瞭解 [如何套用造訪間隔和頻率控制項](../segments/recency-and-frequency.md).
3. 將區段對應至任意數量的即時伺服器對伺服器目的地。 閱讀如何新增區段至 [伺服器對伺服器目的地](../destinations/add-edit-segments.md).

在此案例中，一旦您的使用者累積超過三次曝光，他們將會從此區段中移除，並且不會再看到此特定創意。

![](assets/impressions_use_case.png)

## 需要注意的重要方面 — 處理 {#processing-notes}

請記住以下與處理相關的方面：

* 為了讓即時取消區段功能發揮作用，您必須將所需的區段對應至即時伺服器對伺服器目的地。
* 對於透過連線至裝置的裝置 [裝置圖表](profile-link-use-case.md#recommendations)，我們會強制執行有關評估與取消細分的四部裝置限制。 此限制的說明請參閱 [裝置圖表選項和裝置取消細分](merge-rule-unsegment.md#device-graph-options-unsegmentation). &#x200B;
* 對於透過裝置圖表連線的多個裝置，取消分段命令將包含在批次檔案中，每24小時傳送至目的地。
* 必須即時看見裝置(在 [Edge](../../reference/system-components/components-edge.md) 以即時提示區段評估。 針對具有 [!UICONTROL time-to-live (TTL)]  當特徵 [!DNL TTL] 符合，裝置將會透過批次檔案在24小時內自動取消分段……&#x200B; 深入瞭解如何 [設定特徵過期時間間隔](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* 如果您使用 [!UICONTROL DCS API] 若要即時取得內建規則型特徵，您可使用以下動作來觸發取消分段： [!UICONTROL AND NOT] 邏輯。 深入瞭解 [將資料傳送至DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## 需要注意的重要方面 — 時間 {#timing-notes}

請記住以下與時間相關的方面：

* 區段會儲存在 [Edge](../../reference/system-components/components-edge.md) 與裝置設定檔儲存於相同時段的 [!UICONTROL Edge]，即上次即時互動後14天。 進一步瞭解資料保留，請參閱 [資料保留常見問題集](../../faq/faq-privacy.md#data-retention-faq).
* 取消區段作業大約需要24小時才能傳播到 [!DNL DCS] 地區。 深入瞭解我們的 [!DNL DCS] 區域 [此處](../../reference/system-components/components-data-collection.md) 和 [此處](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
