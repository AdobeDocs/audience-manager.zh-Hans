---
description: 特徵資格或特徵實現在Audience Manager中的處理方式會因特徵型別而異。 請參閱下表，瞭解特徵資格的詳細資訊。
keywords: 特徵資格、特徵實現、獨特特徵實現、UTR、總特徵人口、TTP
seo-description: Trait qualification, or trait realization, is treated differently in Audience Manager, depending on trait type. See the table below for detailed information on trait qualification.
seo-title: Trait Qualification Reference
solution: Audience Manager
title: 特征鉴定参考
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 1%

---

# 特征和区段资格参考 {#trait-qualification-reference}

特徵資格或特徵實現在Audience Manager中的處理方式會因特徵型別而異。 另請參閱 [依特徵型別的特徵資格](#trait-type) 以取得特徵型別資格的詳細資訊。

此外，另請參閱 [即時區段母體與總區段母體](#real-time-segment) 區段資格的詳細資訊。



## 依特徵型別的特徵資格 {#trait-type}

| 特徵型別 | 資格條件 |
|---|---|
| 規則型特徵 | 特徵資格會即時進行，因為使用者在其瀏覽器中符合某個特徵的資格。 您的使用者將在您之後約4小時開始符合規則型特徵的資格 [建立特徵](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 在UI中。 規則型特徵可讓您使用 [造訪間隔和頻率](../segments/recency-and-frequency.md) 廣告頻率上限和其他使用案例的控制項。 |
| 已上線的特徵 | 特徵資格會在處理傳入檔案後發生，即傳入檔案為 [已匯入至Audience Manager](../../faq/faq-inbound-data-ingestion.md) 特徵資格即是如此。 建立已上線的特徵後，您應等待約4小時，再上傳傳入檔案以供處理。 針對已上線的特徵，使用者設定檔的資格數上限為1。 |
| 演演算法特徵 | 對於演演算法特徵，使用者設定檔的資格數量上限為1。 |
| 資料夾特徵 | 資料夾特徵會加總其中包含的特徵之特徵資格。 讀取 [資料夾特徵：關於](about-folder-traits.md) 以取得詳細資訊。 |
| 活动受众特征和数据源同步特征 | 一個 [!UICONTROL Active Audience] 特徵包含Audience Manager帳戶中受管理的所有裝置。 [!UICONTROL Data Source Synced Traits] 追蹤與資料來源相關聯的所有使用者。 深入瞭解 [作用中受眾特徵與資料來源同步特徵](client-activity-synced-audience-traits.md). |

## 不重複特徵實現和特徵總人口數 {#unique-trait-realizations}

![不重複特徵實現](assets/trait-graph.png)

根據您要圖表顯示的結果型別（篩選依據） [!UICONTROL Device ID] 或 [!UICONTROL Cross-Device ID])，這些量度有不同的含義：

篩選結果依據 [!UICONTROL Device ID]：

* [!UICONTROL Unique Trait Realizations] 是在不同時間範圍內將特徵新增至其設定檔的匿名裝置訪客數量。
* [!UICONTROL Total Trait Population] 您的匿名裝置訪客在其設定檔中擁有此特徵的人數。

篩選結果依據 [!UICONTROL Cross-Device ID]：

* [!UICONTROL Unique Trait Realizations] 是在不同時間範圍內，已將該特徵新增至其設定檔的已驗證訪客數量。
* [!UICONTROL Total Trait Population] 是您的已驗證訪客在其設定檔中擁有此特徵的數量。

請以這種方式看待數字。 在上圖中，從 [特徵詳細資訊](../../features/traits/trait-details-page.md) view，90,173代表昨天造訪您屬性的作用中裝置數。 此 [!UICONTROL Total Trait Population] 55,757代表目前符合此特徵資格的使用者數量。 此 [!UICONTROL Total Trait Population] 此圖是用來顯示可用於細分/鎖定的使用者總數。 通常使用者會保留某個特徵的一部分120天。

因為我們執行兩個不同的運算工作來計算這兩個母體， [!UICONTROL Total Trait Population] 總是落後於 [!UICONTROL Unique Trait Realizations] 24小時內。 在上圖中，您可以看到大約90,400個 [!UICONTROL Unique Trait Realizations] 和 [!UICONTROL Total Trait Population] 2月5日大約90,300個。 90,400個設定檔已新增至 [!UICONTROL Total Trait Population] 於次日。

若要進一步將要點帶回家，如果您目前體驗10,000位訪客的峰值，他們將在明天的 [!UICONTROL Unique Trait Realizations]，但只會在過去24小時後顯示 [!UICONTROL Total Trait Population].

特徵實現的任何變更都會反映在區段人口中。

## 即時區段母體與總區段母體 {#real-time-segment}

![不重複特徵實現](assets/segment-graph.png)

此 [!UICONTROL Real-time Segment Population] 計算在選取的時間間隔內，符合所選區段資格且已達到您屬性的裝置數量。

此 [!UICONTROL Total Segment Population] 計算選定時間範圍內符合所選區段資格的裝置數量。 此 [!UICONTROL 1 Day] 報表代表最新的區段母體計數。

請以這種方式看待數字。 在上圖中，從 [區段詳細資料](../../features/segments/segment-summary-view.md) view，9,993代表昨天造訪您屬性且符合區段資格的使用中裝置數。 此 [!UICONTROL Total Segment Population] / 699,532代表目前符合此區段資格的裝置總數。 此 [!UICONTROL Total Segment Population] 此圖是用來顯示可用於細分/鎖定的裝置總數。

因為我們執行兩個不同的運算工作來計算這兩個母體， [!UICONTROL Total Segment Population] 總是落後於 [!UICONTROL Real-time Segment Population] 24小時內。 在上圖中，您可以看到8,116個 [!UICONTROL Real-time Segment Population] 和 [!UICONTROL Total Segment Population] 2月2日為742,000。 這8,116個設定檔已新增至 [!UICONTROL Total Segment Population] 於次日。

若要進一步將要點帶回家，如果您目前體驗10,000位訪客的峰值，他們將在明天的 [!UICONTROL Real-time Segment Population]，但只會在過去24小時後顯示 [!UICONTROL Total Segment Population].

## 特徵資格限制 {#trait-qualification-limit}

我們限制每個使用者設定檔最多150,000個特徵資格，無論其是否為已驗證的設定檔([DPUUID](../../reference/ids-in-aam.md))或裝置ID ([UUID](../../reference/ids-in-aam.md))。 請注意，雖然DPUUID對的特定執行個體而言是唯一的， [!DNL Audience Manager]，UUID可跨以下專案共用： [!DNL Audience Manager] 平台。 對象 [!UICONTROL UUID]因此，我們在儲存特徵資格時，會強制實行公平原則。 演演算法可確保相同份額的 [!UICONTROL UUID] 設定檔可用於的每個執行個體 [!DNL Audience Manager].
