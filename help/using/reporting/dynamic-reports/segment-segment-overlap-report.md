---
description: 返回关于在区段之间共享的唯一用户数的数据。
seo-description: 返回关于在区段之间共享的唯一用户数的数据。
seo-title: 区段到区段重叠报表
solution: Audience Manager
title: 区段到区段重叠报表
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
translation-type: tm+mt
source-git-commit: c05541df2d0dfc8753b06eaa8f2baee9bc6c2a16

---


# 区段到区段重叠报表{#segment-to-segment-overlap-report}

返回关于在区段之间共享的唯一用户数的数据。

>[!NOTE]
>
>Audience manager中的Overlap报告遵循RBAC原则。 您只能根据您所属的 [RBAC用户组来查看您有权访问的数据源中的区段](/help/using/features/administration/administration-overview.md) 。

<!-- 

c_segment_segment_overlap.xml

 -->

## 概述

该 [!UICONTROL Segment-to-Segment Overlap] 报告可以帮助您：

* 根据您的需求，识别重叠程度高或低的区段。 重叠程度高的特征可为您提供目标受众，但唯一访客数量较少。 重叠度低的特征有助于访问更大的唯一访客集。
* 发现意外的重叠，并使用该信息构建新的高性能细分。

## 示例报告

下图提供了报告的高级概 [!UICONTROL Segment-to-Segment Overlap] 述。

>[!NOTE]
>
>当报 [!UICONTROL Segment-to-Segment Overlap] 表将同一区段与自身进行比较时，该报表将返回一个空字段。

![](assets/segment-to-segment-overlap.png)

## 对单个数据点进行向下钻取

选择单个点以在弹出窗口中查看数据详细信息。 单击操作会自动更新报告中显示的数据。

## 段到段重叠数据弹出字段已定义 {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

报告的弹出窗 [!UICONTROL Segment-to-Segment Overlap] 口包含以下指标。 请注意，表中的唯一指标代表您 *的实时用户*。

| 量度 | 描述 |
|---|---|
| **[!UICONTROL Base Segment ID]** | 报告结果中显示的区段的唯一数字ID。 显示为区段的行ID。 |
| **[!UICONTROL Base Segment Name]** | 报告结果行中显示的区段名称。 |
| **[!UICONTROL Overlapping Segment ID]** | 运行报告时所选区段的唯一数字ID。 显示为区段的列ID。 |
| **[!UICONTROL Overlapping Segment Name]** | 运行报告时选择的区段的名称。 显示在报告结果列中。 |
| **[!UICONTROL Base Segment Uniques]** | 基本区段中的唯一访客数。 |
| **[!UICONTROL Base Segment Uniques]** | 重叠区段中的唯一访客数。 |
| **[!UICONTROL Overlapping Uniques]** | 在比较的区段之间共享的唯一访客数。 |
| **[!UICONTROL Overlap %]** | 要获得重叠百分比，Audience manager使用以下公式：重叠单值/（基本段单值+重叠段单值——重叠单值） |



>[!MORELIKETHIS]
>
>* [使用数据滑块过滤报告结果](../../reporting/dynamic-reports/data-sliders.md)
>* [交互式报告中使用的形状、颜色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [说明的报表图标和工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报告：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [所选Audience Manager报告中的数据采样和错误率……](../../reporting/report-sampling.md)
>* [重叠报告的CSV文件](../../reporting/dynamic-reports/overlap-csv-files.md)