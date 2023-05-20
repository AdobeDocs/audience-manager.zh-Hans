---
description: 傳回區段之間共用多少不重複使用者的資料。
seo-description: Returns data on how many unique users are shared between your segments.
seo-title: Segment-to-Segment Overlap Report
solution: Audience Manager
title: 区段到区段重叠报表
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Overlap Reports
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 10%

---

# 区段到区段重叠报表{#segment-to-segment-overlap-report}

傳回區段之間共用多少不重複使用者的資料。

>[!NOTE]
>
>Audience Manager中的重疊報表遵循RBAC原則。 您只能根據以下專案從您有權存取的資料來源檢視區段： [rbac使用者群組](/help/using/features/administration/administration-overview.md) 您所屬的。

<!-- 

c_segment_segment_overlap.xml

 -->

## 概述

此 [!UICONTROL Segment-to-Segment Overlap] 報告可幫助您：

* 根據您的需求，識別具有高重疊或低重疊的區段。 重疊程度高的特徵會提供您目標受眾，但獨特訪客較少。 重疊程度較低的特徵對於觸及較大且不重複的訪客集相當實用。
* 找出非預期的重疊，然後使用該資訊來建立新的高效能區段。

## 範例報告

下圖提供 [!UICONTROL Segment-to-Segment Overlap] 報告。

>[!NOTE]
>
>此 [!UICONTROL Segment-to-Segment Overlap] 報表比較相同區段與本身時，會傳回空白欄位。

![](assets/segment-to-segment-overlap.png)

## 深入研究個別資料點

選取個別點，以在快顯視窗中檢視資料詳細資訊。 您的點按動作會自動更新報表中顯示的資料。

## 定義的區段對區段重疊資料快顯欄位 {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

的快顯視窗 [!UICONTROL Segment-to-Segment Overlap] 報表包含下列量度。 請注意，表格中的不重複量度代表 *即時使用者*.

| 量度 | 描述 |
|---|---|
| **[!UICONTROL Base Segment ID]** | 顯示在報表結果中的區段的不重複數值ID。 顯示為區段的列ID。 |
| **[!UICONTROL Base Segment Name]** | 顯示在報表結果列中的區段名稱。 |
| **[!UICONTROL Overlapping Segment ID]** | 您在執行報表時選取之區段的唯一數值ID。 顯示為區段的欄ID。 |
| **[!UICONTROL Overlapping Segment Name]** | 執行報表時選取的區段名稱。 顯示在報告結果欄中。 |
| **[!UICONTROL Base Segment Uniques]** | 基礎區段中的不重複訪客數量。 |
| **[!UICONTROL Base Segment Uniques]** | 重疊區段中的不重複訪客數量。 |
| **[!UICONTROL Overlapping Uniques]** | 在比較的區段之間共用的不重複訪客數量。 |
| **[!UICONTROL Overlap %]** | 若要取得重疊百分比，Audience Manager會使用下列公式：重疊不重複值/ （基本區段不重複值+重疊區段不重複值 — 重疊不重複值） |



>[!MORELIKETHIS]
>
>* [使用数据滑块筛选报表结果](../../reporting/dynamic-reports/data-sliders.md)
>* [互動式報表中使用的形狀、顏色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [說明報表圖示和工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报表：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [选定 Audience Manager 报表中的数据取样率和错误率...](../../reporting/report-sampling.md)
>* [重叠报表的 CSV 文件](../../reporting/dynamic-reports/overlap-csv-files.md)

