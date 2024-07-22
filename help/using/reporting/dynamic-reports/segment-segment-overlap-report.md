---
description: 返回有关区段之间共享多少个独特用户的数据。
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
ht-degree: 6%

---

# 区段到区段重叠报表{#segment-to-segment-overlap-report}

返回有关区段之间共享多少个独特用户的数据。

>[!NOTE]
>
>Audience Manager中的重叠报表遵循RBAC原则。 您只能根据您所属的[RBAC用户组](/help/using/features/administration/administration-overview.md)，从您有权访问的数据源中查看区段。

<!-- 

c_segment_segment_overlap.xml

 -->

## 概述

[!UICONTROL Segment-to-Segment Overlap]报告可以帮助您：

* 根据您的需求，识别具有高重叠或低重叠的区段。 具有高重叠的特征可为您提供目标受众，但独特访客较少。 重叠程度较低的特征对于访问较大的独特访客集很有用。
* 找到意外的重叠，然后使用该信息构建新的高性能区段。

## 示例报告

下图提供了[!UICONTROL Segment-to-Segment Overlap]报表的高级概述。

>[!NOTE]
>
>[!UICONTROL Segment-to-Segment Overlap]报表将同一区段与其自身进行比较时返回空字段。

![](assets/segment-to-segment-overlap.png)

## 向下展开单个数据点

选择单个点以在弹出窗口中查看数据详细信息。 您的单击操作会自动更新报告中显示的数据。

## 定义的区段到区段重叠数据Pop字段 {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

[!UICONTROL Segment-to-Segment Overlap]报表的弹出窗口包含下列量度。 请注意，表中的唯一量度表示您的&#x200B;*实时用户*。

| 量度 | 描述 |
|---|---|
| **[!UICONTROL Base Segment ID]** | 显示在报告结果中的区段的唯一数值ID。 显示为区段的行ID。 |
| **[!UICONTROL Base Segment Name]** | 显示在报表结果行中的区段的名称。 |
| **[!UICONTROL Overlapping Segment ID]** | 运行报表时选择的区段的唯一数值ID。 显示为区段的列ID。 |
| **[!UICONTROL Overlapping Segment Name]** | 运行报表时选择的区段的名称。 显示在报告结果列中。 |
| **[!UICONTROL Base Segment Uniques]** | 基础区段中的独特访客数。 |
| **[!UICONTROL Base Segment Uniques]** | 重叠区段中的独特访客数。 |
| **[!UICONTROL Overlapping Uniques]** | 在比较的区段之间共享的独特访客数。 |
| **[!UICONTROL Overlap %]** | 要获得重叠百分比，Audience Manager使用以下公式：重叠唯一值/（基本区段唯一值+重叠区段唯一值 — 重叠唯一值） |



>[!MORELIKETHIS]
>
>* [使用数据滑块筛选报表结果](../../reporting/dynamic-reports/data-sliders.md)
>* [交互式报表中使用的形状、颜色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [报告图标和工具说明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报表：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [选定Audience Manager报表中的数据取样率和错误率……](../../reporting/report-sampling.md)
>* [重叠报表的 CSV 文件](../../reporting/dynamic-reports/overlap-csv-files.md)
