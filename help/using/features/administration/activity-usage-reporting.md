---
description: 活動使用情況報告可幫助您檢視和追蹤Audience Manager例項的活動使用情況，以便您可以將實際使用情況與合約承諾進行比較。
keywords: 活動，使用量，報告，承諾
seo-description: Activity Usage Reporting helps you view and track the activity usage for your Audience Manager instance, so you can compare your actual usage to your contractual commitment.
seo-title: Activity Usage Reporting
solution: Audience Manager
title: 活动使用情况报表
feature: Usage and Billing
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 5%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## 概述 {#overview}

通过 [!UICONTROL Activity Usage Report]，您可以查看和跟踪 Audience Manager 实例的活动使用情况，从而清楚地了解实际的活动使用情况与合同承诺之间存在的差异。

此外，您也可以下載 [!UICONTROL Activity Usage Report] 需要時，隨時保留記錄及進行自訂分析。

## 注意事项 {#considerations}

此 [!UICONTROL Activity Usage Report] 可供所有Audience Manager使用者使用 [管理員許可權](edit-account-settings.md).

>[!IMPORTANT]
>
>此 [!UICONTROL Activity Usage Report] 顯示Audience Manager執行個體的活動使用狀況統計資料。 如有任何與活動使用情況相關的計費問題，請聯絡您的Adobe代表。

## 用例 {#use-cases}

有兩個主要使用案例 [!UICONTROL Activity Usage Report]：

* **根據您的活動使用量承諾追蹤實際執行個體活動使用量**：大多數客戶會有每個Audience Manager執行個體的每月估計活動承諾，然後累計至所有執行個體的每年活動承諾。 雖然此報告不是計費報告，但可提供關於您是否超過認可活動使用量的實用指引。
* **驗證實作變更**：如果您最近曾更新實作，例如設定 [!DNL Adobe Analytics] 伺服器端轉送，或變更您的 [!DNL Adobe Target] 伺服器呼叫設定，此報表可協助您檢查新活動磁碟區是否與預期活動磁碟區一致。

## 使用 [!UICONTROL Activity Usage Report] {#using}

若要檢視 [!UICONTROL Activity Usage Report]，登入您的Audience Manager帳戶，然後前往 **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

接下來，使用 **[!UICONTROL Reporting Interval]** 篩選以選取產生報表的時間間隔。 您可以選擇30、60、90天或自訂日期範圍。

報告載入後，您就能看到以下專案的劃分 [!UICONTROL Activities] 於所選期間。

[!UICONTROL Activities] 定義與Audience Manager的所有站上和站外互動的總計，分為下列類別：

* **[!UICONTROL Server Calls]**：從網站、伺服器、電子郵件、行動應用程式或其他系統傳送給Audience Manager的任何資料收集或擷取事件。
* **[!UICONTROL Pixel Calls](先前稱為 [!UICONTROL Impression Server Calls])**：從廣告收集的資料（例如來自目標平台的曝光量）或向Audience Manager發出的電子郵件曝光呼叫。 這需要 `d_event` 查詢字串中的引數。
* **[!UICONTROL On-Boarded Records]**：從您自己的客戶關係管理系統(CRM)或其他離線資料檔案擷取的不重複記錄，例如客服中心記錄、裝置ID和來自外部資料提供者的自訂資料摘要。
* **[!UICONTROL Log File Records]**：從目標平台擷取到Audience Manager之記錄檔的不重複記錄。

>[!NOTE]
>
>唯一記錄會定義Adobe代表Audience Manager客戶儲存之檔案中的每筆資料記錄。

此外，您可以使用 [!UICONTROL Activity Usage Trends] 圖表型別，以便在兩種圖表型別之間切換。

![aur-ui-graph](assets/aur-ui-graphs.png)

您也可以將游標暫留在時間軸中的特定日期上，以檢視該日期的詳細使用情形。

![Aur-hover](assets/aur-hover.png)

## 匯出 [!UICONTROL Activity Usage Reports] {#export}

如需Audience Manager活動使用層級的更佳概觀，您可以匯出 [!UICONTROL Activity Usage Report] 根據您要包含的記錄型別。

![自動匯出](assets/aur-export.png)

此 **[!UICONTROL Onboarded Records Breakdown]** 和 **[!UICONTROL Onsite Server Calls Breakdown]** 報表可提供這些活動可用來源資料的最精細分析。 歸因到這些劃分的磁碟區會根據您的實作。

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

此報表包含依資料來源劃分的已上線記錄。

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

此報表包含來自三個來源的伺服器呼叫劃分： [!UICONTROL Analytics]， [!UICONTROL Target]、和 [!UICONTROL Other].

* **[!UICONTROL Analytics]**：這些是從所有伺服器呼叫（以計費方式傳遞） [!UICONTROL Adobe Analytics] Audience Manager的執行個體，包括伺服器端轉送。 次要伺服器呼叫或重複伺服器呼叫（例如來自多個報表套裝的伺服器端轉送）無法記帳活動，因此不會包含在此劃分中。
* **[!UICONTROL Target]**：這些是來自的伺服器端呼叫 [!UICONTROL Adobe Target] 若要Audience Manager，則擷取Audience Manager區段資料，作為伺服器對伺服器整合的一部分。
* **[!UICONTROL Other]**：包含來自任何其他網站或系統（合作夥伴網站、直接伺服器呼叫等）的呼叫，以及透過以下方式進行的行動瀏覽器/應用程式呼叫： [!DNL SDK]， [!DNL DIL]、事件呼叫和 [!DNL DCS] 呼叫。 也包含來自的呼叫 [!DNL Target] 若已設定為Cookie整合（而非伺服器對伺服器）。
