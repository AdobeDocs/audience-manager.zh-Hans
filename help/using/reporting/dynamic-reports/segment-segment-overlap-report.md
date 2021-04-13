---
description: 返回关于在区段之间共享的唯一用户数的数据。
seo-description: 返回关于在区段之间共享的唯一用户数的数据。
seo-title: 区段到区段重叠报表
solution: Audience Manager
title: 区段到区段重叠报表
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: 重叠报表
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 11%

---

# 区段到区段重叠报表{#segment-to-segment-overlap-report}

返回关于在区段之间共享的唯一用户数的数据。

>[!NOTE]
>
>Audience Manager中的Overlap报表遵循RBAC原则。 您只能根据您所属的[RBAC用户组](/help/using/features/administration/administration-overview.md)访问的数据源中的区段。

<!-- 

c_segment_segment_overlap.xml

 -->

## 概述

[!UICONTROL Segment-to-Segment Overlap]报告可帮助您：

* 根据您的需求确定重叠程度高或低的区段。 重叠度高的特征可为您提供目标受众，但独特访客较少。 重叠度低的特征有助于达到更大、唯一的访客集。
* 发现意外的重叠，并使用该信息构建新的高性能细分。

## 示例报告

下图提供了[!UICONTROL Segment-to-Segment Overlap]报表的高级概述。

>[!NOTE]
>
>当[!UICONTROL Segment-to-Segment Overlap]报表将同一区段与自身进行比较时，该报表返回一个空字段。

![](assets/segment-to-segment-overlap.png)

## 深入查看各个数据点

在弹出窗口中选择视图数据详细信息的单个点。 您的点击操作会自动更新报表中显示的数据。

## 定义{#fields-defined}的“段到段”重叠数据弹出字段

<!-- 

r_s2s_data_pop.xml

 -->

[!UICONTROL Segment-to-Segment Overlap]报表的弹出窗口包含以下量度。 请注意，表中的唯一值量度表示您的&#x200B;*实时用户*。

| 量度 | 描述 |
|---|---|
| **[!UICONTROL Base Segment ID]** | 报表结果中显示的区段的唯一数字ID。 显示为区段的行ID。 |
| **[!UICONTROL Base Segment Name]** | 在报表结果行中显示的区段名称。 |
| **[!UICONTROL Overlapping Segment ID]** | 运行报表时所选区段的唯一数字ID。 显示为区段的列ID。 |
| **[!UICONTROL Overlapping Segment Name]** | 运行报表时选择的区段的名称。 显示在报表结果列中。 |
| **[!UICONTROL Base Segment Uniques]** | 基本区段中的唯一访客数。 |
| **[!UICONTROL Base Segment Uniques]** | 重叠区段中的唯一访客数。 |
| **[!UICONTROL Overlapping Uniques]** | 在比较的区段之间共享的唯一访客数。 |
| **[!UICONTROL Overlap %]** | 要获取重叠%,Audience Manager使用以下公式：重叠单值/（基段单值+重叠段单值 — 重叠单值） |



>[!MORELIKETHIS]
>
>* [使用数据滑块筛选报表结果](../../reporting/dynamic-reports/data-sliders.md)
>* [交互式报表中使用的形状、颜色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [说明报表图标和工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报表：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [选定 Audience Manager 报表中的数据取样率和错误率...](../../reporting/report-sampling.md)
>* [重叠报表的 CSV 文件](../../reporting/dynamic-reports/overlap-csv-files.md)

