---
description: 返回在区段之间共享多少唯一用户的数据。
seo-description: 返回在区段之间共享多少唯一用户的数据。
seo-title: 区段到区段重叠报表
solution: Audience Manager
title: 区段到区段重叠报表
uuid: 0339eb6c-6355-44a3-9c46-f159484449 d1
translation-type: tm+mt
source-git-commit: 339d5550b22949862415d2abc812217e5479c993

---


# 区段到区段重叠报表{#segment-to-segment-overlap-report}

返回在区段之间共享多少唯一用户的数据。

>[!NOTE]
>
>Audience Manager中的重叠报告遵循CLUAC原则。You can only see segments from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_segment_segment_overlap.xml

 -->

## 概述

[!UICONTROL Segment-to-Segment Overlap] 此报告可帮助您：

* 根据您的需求确定高或低重叠的细分。重叠的特征可为您提供目标受众，但访客数量较少。低重叠的特征对于到达较大、独特的访客集很有用。
* 发现意外重叠并使用该信息构建新的高性能细分。

## 示例报告

The following illustration provides a high-level overview of the [!UICONTROL Segment-to-Segment Overlap] report.

>[!NOTE]
>
>[!UICONTROL Segment-to-Segment Overlap] 报表将同一区段与其自身比较时返回一个空字段。

![](assets/segment-to-segment-overlap.png)

## 深入了解各个数据点

选择单个点可在弹出窗口中查看数据详细信息。单击操作会自动更新报告中显示的数据。

## Segment-to-Segment Overlap Data Pop Fields Defined {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

[!UICONTROL Segment-to-Segment Overlap] 报告的弹出窗口包含以下指标。Note that the uniques metric in the table represents your *real-time users*.

| 量度 | 描述 |
|---|---|
| **[!UICONTROL Segment ID1]** | 报表结果中显示的区段的唯一数值ID。显示为区段的行ID。 |
| **[!UICONTROL Segment ID2]** | 运行报表时所选区段的唯一数值ID。显示为区段的列ID。 |
| **[!UICONTROL Segment Name1]** | 报告结果行中显示的区段名称。 |
| **[!UICONTROL Segment Name2]** | 运行报表时所选区段的名称。显示在报表结果列中。 |
| **[!UICONTROL Overlap %]** | 要获得重叠%，Audience Manager使用以下公式：重叠的唯一节点/(基本区段统一+重叠区段统一-重叠的唯一等式) |
| **[!UICONTROL Overlap Uniques]** | 比较区段之间的唯一访客数量。 |
| **[!UICONTROL Segment Uniques1]** | 区段中唯一访客的数量。 |
| **[!UICONTROL Segment Uniques2]** | 区段中唯一访客的数量。 |

>[!MORE_ LIKE_ This]
>
>* [使用数据滑块过滤报告结果](../../reporting/dynamic-reports/data-sliders.md)
>* [交互式报告中使用的形状、颜色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [报告图标和工具说明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报告：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [选定Audience Manager报告中的数据采样和错误率…](../../reporting/report-sampling.md)
>* [重叠报告的CSV文件](../../reporting/dynamic-reports/overlap-csv-files.md)