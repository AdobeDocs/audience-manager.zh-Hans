---
description: 返回关于在区段之间共享的唯一用户数的数据。
seo-description: 返回关于在区段之间共享的唯一用户数的数据。
seo-title: 区段到区段重叠报表
solution: Audience Manager
title: 区段到区段重叠报表
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
translation-type: tm+mt
source-git-commit: a35be513c2cec40257f2df0731eaccbb98e3a000
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 3%

---


# 区段到区段重叠报表{#segment-to-segment-overlap-report}

返回关于在区段之间共享的唯一用户数的数据。

>[!NOTE]
>
>受众管理器中的Overlap报表遵循RBAC原则。 您只能根据您所属的RBAC用户组来查看您 [有权访问的](/help/using/features/administration/administration-overview.md) 数据源中的段。

<!-- 

c_segment_segment_overlap.xml

 -->

## 概述

该报 [!UICONTROL Segment-to-Segment Overlap] 告可以帮助您：

* 根据您的需求确定重叠程度高或低的细分。 重叠度高的特征为您提供目标受众，但独特访客更少。 重叠度低的特征有助于达到更大、唯一的访客集。
* 发现意外的重叠，并使用该信息构建新的高性能细分。

## 示例报告

下图提供了报告的高级概 [!UICONTROL Segment-to-Segment Overlap] 述。

>[!NOTE]
>
>当报 [!UICONTROL Segment-to-Segment Overlap] 表将同一区段与其自身进行比较时，该报表返回一个空字段。

![](assets/segment-to-segment-overlap.png)

## 深入查看单个数据点

在弹出窗口中选择单个点以视图数据详细信息。 单击操作会自动更新报告中显示的数据。

## 段到段重叠数据弹出字段已定义 {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

报告的弹出 [!UICONTROL Segment-to-Segment Overlap] 窗口包含以下指标。 请注意，表中的唯一度量表示 *您的实时用户*。

| 量度 | 描述 |
|---|---|
| **[!UICONTROL Base Segment ID]** | 报表结果中显示的区段的唯一数字ID。 显示为区段的行ID。 |
| **[!UICONTROL Base Segment Name]** | 在报表结果行中显示的区段名称。 |
| **[!UICONTROL Overlapping Segment ID]** | 运行报表时所选区段的唯一数字ID。 显示为区段的列ID。 |
| **[!UICONTROL Overlapping Segment Name]** | 运行报告时选择的区段的名称。 显示在报告结果列中。 |
| **[!UICONTROL Base Segment Uniques]** | 基本区段中的唯一访客数。 |
| **[!UICONTROL Base Segment Uniques]** | 重叠区段中的唯一访客数。 |
| **[!UICONTROL Overlapping Uniques]** | 在比较的区段之间共享的唯一访客数。 |
| **[!UICONTROL Overlap %]** | 要获得重叠%,受众管理器使用以下公式： 重叠单值/（基段单值+重叠段单值——重叠单值） |



>[!MORELIKETHIS]
>
>* [使用数据滑块过滤报告结果](../../reporting/dynamic-reports/data-sliders.md)
>* [交互式报告中使用的形状、颜色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [说明报告图标和工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报表： 更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [所选受众管理器报告中的数据采样和错误率……](../../reporting/report-sampling.md)
>* [用于重叠报告的CSV文件](../../reporting/dynamic-reports/overlap-csv-files.md)