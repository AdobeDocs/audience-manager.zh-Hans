---
description: 返回有关区段之间共享的独特用户数量的数据。
seo-description: 返回有关区段之间共享的独特用户数量的数据。
seo-title: 区段到区段重叠报表
solution: Audience Manager
title: 区段到区段重叠报表
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: 重叠报表
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 11%

---

# 区段到区段重叠报表{#segment-to-segment-overlap-report}

返回有关区段之间共享的独特用户数量的数据。

>[!NOTE]
>
>Audience Manager中的重叠报表遵循RBAC原则。 您只能根据您所属的[RBAC用户组](/help/using/features/administration/administration-overview.md)查看您有权访问的数据源中的区段。

<!-- 

c_segment_segment_overlap.xml

 -->

## 概述

[!UICONTROL Segment-to-Segment Overlap]报表可帮助您：

* 根据您的需求，识别重叠程度高或低的区段。 重叠程度较高的特征为您提供了目标受众，但独特访客数量较少。 重叠程度较低的特征对于访问更大的独特访客集非常有用。
* 查找意外的重叠，然后使用该信息构建新的高性能区段。

## 示例报表

下图提供了[!UICONTROL Segment-to-Segment Overlap]报表的高级概述。

>[!NOTE]
>
>当[!UICONTROL Segment-to-Segment Overlap]报表将同一区段与其自身进行比较时，它会返回一个空字段。

![](assets/segment-to-segment-overlap.png)

## 深入了解单个数据点

选择单个点以在弹出窗口中查看数据详细信息。 您的点击操作会自动更新报表中显示的数据。

## 定义的区段到区段重叠数据弹出字段{#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

[!UICONTROL Segment-to-Segment Overlap]报表的弹出窗口包含以下量度。 请注意，表中的唯一值量度表示您的&#x200B;*实时用户*。

| 量度 | 描述 |
|---|---|
| **[!UICONTROL Base Segment ID]** | 报表结果中显示的区段的唯一数字ID。 显示为区段的行ID。 |
| **[!UICONTROL Base Segment Name]** | 在报表结果行中显示的区段名称。 |
| **[!UICONTROL Overlapping Segment ID]** | 运行报表时所选区段的唯一数字ID。 显示为区段的列ID。 |
| **[!UICONTROL Overlapping Segment Name]** | 运行报表时选择的区段名称。 显示在报表结果列中。 |
| **[!UICONTROL Base Segment Uniques]** | 基本区段中的独特访客数。 |
| **[!UICONTROL Base Segment Uniques]** | 重叠区段中的独特访客数。 |
| **[!UICONTROL Overlapping Uniques]** | 在比较的区段之间共享的独特访客数。 |
| **[!UICONTROL Overlap %]** | 要获取重叠%,Audience Manager使用以下公式：重叠独特值/（基本区段独特值+重叠区段独特值 — 重叠独特值） |



>[!MORELIKETHIS]
>
>* [使用数据滑块筛选报表结果](../../reporting/dynamic-reports/data-sliders.md)
* [交互式报表中使用的形状、颜色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
* [报表图标和工具说明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
* [重叠报表：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
* [选定 Audience Manager 报表中的数据取样率和错误率...](../../reporting/report-sampling.md)
* [重叠报表的 CSV 文件](../../reporting/dynamic-reports/overlap-csv-files.md)

