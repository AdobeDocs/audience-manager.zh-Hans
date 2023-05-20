---
description: 一般報表會傳回特徵、區段和目的地的效能資料。
seo-description: A General report in Audience Manager returns performance data on traits, segments, and destinations.
seo-title: General Reports in Audience Manager
solution: Audience Manager
title: 常规报表
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: General & Trend Reports
exl-id: dc16a821-b776-4a04-af60-4b8c914253dd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 1%

---

# 常规报表{#general-reports}

A [!UICONTROL General] 報表會傳回特徵、區段和目的地的效能資料。

## 概述 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])將使用者群組許可權擴充至 [!UICONTROL General] 報表。 使用者在報告中只能看見他們有權檢視的特徵和區段。 [!UICONTROL RBAC] 功能可讓您控制內部團隊可以檢視哪些報告資料。 例如，管理不同廣告商帳戶的機構可以設定使用者群組許可權，這樣管理廣告商A帳戶的團隊就看不到廣告商B的報告資料。

執行 [!UICONTROL General] 報告您何時需要：

* 依特徵、區段或目的地檢閱績效。
* 以1、7、14、30、60和90天為間隔追蹤曝光（總計和唯一）。
* 檢閱總計和不重複載入計數。
* 比較特徵和區段效能。
* 識別效能強大或效能不佳的特徵和區段、分析需求，或將載入/引發資料與協力廠商報表進行比較。
* 匯出資料（.csv格式）以供進一步分析和共用。

下圖提供「 」中重要元素的高階概觀 [!UICONTROL General] 報告。

![](assets/general_reports.png)

1. 配置以下选项：

   * **報表型別：** 選取所需的報表型別（「特徵」、「區段」或「目的地」）。

   * **日期截止日期：** 指定報表的日期範圍。

2. 依名稱或ID搜尋特徵、區段或目的地。
3. 從資料夾清單中，拖放您要報告的特徵、區段或目的地至 [!UICONTROL Selections] 右側面板。
4. 產生報表以顯示於可匯出表格中。

## 執行一般報表 {#run-general-report}

本節說明如何執行 [!UICONTROL General] 報告並設定時間和其他效能選項。

<!-- 

t_run_general_report.xml

 -->

1. 在 **[!UICONTROL Analytics]** 儀表板，按一下 **[!UICONTROL General Reports]**.
1. 從 **[!UICONTROL Report Type]** 從下拉式清單中，選取所需的型別：特徵、區段或目的地。
1. *條件式* 按一下日期方塊以顯示行事曆，然後選取報表的結束日期（如果您要指定今天以外的日期）。
1. 依名稱或ID搜尋特徵、區段或目的地。
1. 從資料夾清單中，拖放您要報告的特徵、區段或目的地至 [!UICONTROL Selections] 右側面板。
1. 单击 **[!UICONTROL Run Report]**.

   結果會顯示在可匯出的表格中。 按一下欄標題，以遞增或遞減順序排序結果。
1. 在報表頂端選取所需的選項按鈕，以依據效能篩選資料( [!UICONTROL Unique Trait Realizations]， [!UICONTROL Total Trait Realizations]，或 [!UICONTROL Total Trait Population])，或依時間（1、7、14、30、60或90天範圍）。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 計算對象 [!UICONTROL Rule-based Traits] 僅限。

1. *可選* 按一下 **[!UICONTROL Export to CSV]**. 這會匯出 [!UICONTROL Unique Trait Realizations]， [!UICONTROL Total Trait Realizations]、和 [!UICONTROL Total Trait Population] 適用於所有日期範圍。

## 一般報表結果說明 {#general-reports-explained}

中的數字 [!UICONTROL General Reports] 直接產生自我們的 [!UICONTROL User Profile Store]. 結果反映符合以下條件的使用者數量 [!DNL Audience Manager] 產生這些報表編號時，包含在後端中。

* 這些數字不包含具有過多流量的訪客ID。 來自機器人的流量會在到達後端系統之前進行篩選。 此外，在後端每週執行清理工作時，也會捨棄某些機器人流量。
* 如果您透過輸入處理載入資料，但將 [!DNL Audience Manager] UUID，而且這些ID包含系統中不再作用中的使用者，這些非作用中的使用者 [!DNL Audience Manager] UUID永遠不會到達 [!UICONTROL User Profile Store] 和不會回報。
* [!UICONTROL Total Trait Realizations] 計算對象 [!UICONTROL Rule-based Traits] 僅限。

## 特徵的一般報表結果 {#general-report-results-traits}

當您執行「一般」報表並選取「 」時，可使用下列篩選器 **[!UICONTROL Trait]** 作為報表型別。

篩選結果依據 [!UICONTROL Device ID]：

* [!UICONTROL Unique Trait Realizations] 是在所選時間範圍內將特徵新增至其設定檔的匿名裝置訪客數量。
* [!UICONTROL Total Trait Realization] 是所選時間範圍內的匿名特徵實現總數。
* [!UICONTROL Total Trait Population] 您的匿名裝置訪客在其設定檔中擁有此特徵的人數。

![general-report-traits-device](assets/general-report-traits-deviceid.png)

篩選結果依據 [!UICONTROL Cross-Device ID]：

* [!UICONTROL Unique Trait Realizations] 在選取的時間範圍內，已驗證身分的訪客新增特徵至其設定檔的數量。
* [!UICONTROL Total Trait Realization] 是所選時間範圍內已驗證的特徵實現總數。
* [!UICONTROL Total Trait Population] 是您的已驗證訪客在其設定檔中擁有此特徵的數量。

![一般 — 報告 — 特徵 — 跨裝置](assets/general-report-traits-cross-device.png)

<!-- 
### Unique Trait Realizations

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. For example, if a user visited your homepage three times on 10/1, you would see one Unique Trait Realization.

### Total Trait Realizations

This metric represents the total amount of trait fires for the trait in your selected time range. For example, if a user visited your homepage, then navigated to your tech news and your sports news sections, they would appear in the General Report as three total trait realizations, and one unique trait realization.

### Total Trait Population

This metric represents the total amount of Audience Manager UUIDs that are currently qualified for the trait. Use this number to understand the total amount of users you could use for segmentation and targeting. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). For example, a user visiting your homepage three times today and never returning afterwards, would remain as a user in this population every day until 120 days from now. At the 120 day mark, they would be removed from the population. Read our [Trait and Segment Qualification Reference](../features/traits/trait-and-segment-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

The illustration below shows the results of running a general report for the Trait report type. -->
<!-- 
![](assets/general_reports_metrics.png) -->


## 區段的一般報表結果 {#general-report-results-segments}

當您執行「一般」報表並選取「 」時，可使用下列量度 **[!UICONTROL Segment]** 作為報表型別：

### 即時區段母體

此量度代表在指定時間範圍內即時檢視的不重複訪客的實際數量，以及在Audience Manager看到這些訪客時符合區段資格的人數。

### 總區段母體

此量度代表在您選取的回顧期間內符合區段資格的Audience ManagerUUID總數。 1天總區段母體代表您鎖定目標時最準確的使用者基礎。

>[!NOTE]
>
>選取 **[!UICONTROL Include Destination Mappings]** 檢視已啟用目的地的區段母體劃分。

下圖顯示「區段」報表型別的一般報表執行結果。

![](assets/general_reports_segment_metrics.png)

## 目的地的一般報告結果 {#general-report-results-destinations}

當您執行「一般」報表並選取「 」時，可使用下列量度 **[!UICONTROL Destination]** 作為報表型別：

**即時區段母體**

此量度代表在指定時間範圍內即時檢視的不重複訪客的實際數量，以及在Audience Manager看到這些訪客時符合區段資格的人數。

**總區段母體**

此量度代表在回顧期間內，屬於區段且已傳送至目的地的Audience ManagerUUID總數。

下圖顯示針對「目的地」報表型別執行一般報表的結果。

![](assets/general_reports_destinations.png)
