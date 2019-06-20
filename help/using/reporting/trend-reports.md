---
description: 趋势报告返回特征和区段的趋势数据。
seo-description: 趋势报告返回特征和区段的趋势数据。
seo-title: 趋势报告
solution: Audience Manager
title: 趋势报告
uuid: bdb7d4-7cbb-4403-9104-312f9230aea1
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# Trend Reports{#trend-reports}

趋势报告返回特征和区段的趋势数据。

## 概述 {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] uses [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])将用户组权限扩展到 [!UICONTROL Trend] 报告。用户只能查看报告中具有查看权限的特征和区段。[!UICONTROL RBAC] 功能允许您控制内部团队能够查看哪些报告数据。

例如，管理不同广告商帐户的代理可以配置用户组权限，以使管理Advertiser A帐户的团队无法看到Advertiser B的报告数据。

Run a [!UICONTROL Trend] report when you need to:

* 根据特征和细分评估趋势数据。
* 按1、7、14、30、60和90天的间隔跟踪趋势。
* 对比特征和细分趋势随时间推移的趋势。
* 识别强大或不良的绩效特征和细分。
* 导出数据(. csv格式)以进一步分析和共享。

The following illustration provides a high-level overview of key elements in the [!UICONTROL Trend] report.

![](assets/trend_reports.png)

1. 配置以下选项：

   **报告类型：** 选择所需的报告类型(特征或区段)。

   **日期范围：** 指定报告的日期范围(开始日期和结束日期)。

   **显示时间间隔：** 指定显示时间间隔(1、7、14、30、60和90天间隔)。

2. 按名称或ID搜索特征或区段。
3. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.
4. 生成报表以以图形格式显示数据或将报表导出为CSV格式。

## Run a Trend Report {#run-trend-report}

This procedure describes how to run a [!UICONTROL Trend] report.

<!-- 

t_working_with_trend_reports.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL Trend Reports]**.
1. From the **[!UICONTROL Report Type]** drop-down list, select the desired type: **[!UICONTROL Trait]** or **[!UICONTROL Segment]**.
1. 单击日期框以显示日历，然后选择报表的开始日期和结束日期。
1. 指定显示间隔：1、7、14、30、60或90天。
1. 按名称或ID搜索特征或区段。
1. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.

   For best performance, run a [!UICONTROL Trend] report on fewer than 20 traits or segments at a time.
1. Click **[!UICONTROL Graph Traits]** or **[!UICONTROL Graph Segments]**, depending on which type of report you are viewing (Traits or Segments).

   这些选项将忽略所有文件夹和图形，仅单独选定的特征或区段。

   或

   Click **[!UICONTROL Export to CSV]** to export the trait or segment data and all folders in CSV format for further analysis and sharing. This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 仅供计算。[!UICONTROL Rule-based Traits]

1. (可选)将鼠标悬停在单个特征或段上，以显示访问次数和每个数据点的日期。

   您可以单击表中的列标题，以按升序或降序排序结果。

[!UICONTROL Trended Trait] 对于报告，零表示 [!DNL Audience Manager] 当日没有收集数据。空白条目指示特征不存在。以下示例显示了两种类型条目的示例：

![](assets/trended_data.png)
