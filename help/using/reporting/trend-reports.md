---
description: “趋势”报表返回有关特征和区段的趋势数据。
seo-description: “趋势”报表返回有关特征和区段的趋势数据。
seo-title: 趋势报告
solution: Audience Manager
title: 趋势报告
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# 趋势报告{#trend-reports}

“趋势”报表返回有关特征和区段的趋势数据。

## 概述 {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])将用户组权限扩展到报 [!UICONTROL Trend] 表。 用户只能在报告中看到他们有权查看的那些特征和区段。 [!UICONTROL RBAC] 功能允许您控制内部团队可以查看的报告数据。

例如，管理不同广告商帐户的代理可以配置用户组权限，以便管理广告商A帐户的团队无法看到广告商B的报告数据。

在需要 [!UICONTROL Trend] 时运行报告：

* 按特征和区段查看趋势数据。
* 按1、7、14、30、60和90天间隔跟踪趋势。
* 比较特征和区段趋势随时间变化。
* 识别强或弱的性能特征和细分。
* 导出数据（.csv格式）以进一步分析和共享。

下图提供了报告中关键元素的高级概 [!UICONTROL Trend] 述。

![](assets/trend_reports.png)

1. 配置以下选项：

   **** 报告类型：选择所需的报告类型（特征或区段）。

   **** 日期范围：指定报表的日期范围（开始日期和结束日期）。

   **** 显示间隔：指定显示间隔（1、7、14、30、60和90天间隔）。

2. 按名称或ID搜索特征或区段。
3. 从文件夹列表中，将要报告的特征或区段拖放到右 [!UICONTROL Selections] 侧的面板中。
4. 生成报告以图形格式显示，或将报告导出为CSV格式。

## Run a Trend Report {#run-trend-report}

此过程介绍如何运行报 [!UICONTROL Trend] 告。

<!-- 

t_working_with_trend_reports.xml

 -->

1. 在功能 **[!UICONTROL Analytics]** 板中，单击 **[!UICONTROL Trend Reports]**。
1. 从下 **[!UICONTROL Report Type]** 拉列表中，选择所需的类型：或 **[!UICONTROL Trait]** 者 **[!UICONTROL Segment]**。
1. 单击日期框以显示日历，然后选择报表的开始和结束日期。
1. 指定显示间隔：1、7、14、30、60或90天。
1. 按名称或ID搜索特征或区段。
1. 从文件夹列表中，将要报告的特征或区段拖放到右 [!UICONTROL Selections] 侧的面板中。

   为获得最佳性能，请 [!UICONTROL Trend] 一次运行少于20个特征或区段的报告。
1. 单击 **[!UICONTROL Graph Traits]** 或， **[!UICONTROL Graph Segments]**&#x200B;具体取决于您查看的报表类型（特征或区段）。

   这些选项只忽略单独选择的特征或区段的所有文件夹和图形。

   或

   单击 **[!UICONTROL Export to CSV]** 以导出特征或区段数据以及CSV格式的所有文件夹，以便进一步分析和共享。 这将导出 [!UICONTROL Unique Trait Realizations]所有 [!UICONTROL Total Trait Realizations]日期 [!UICONTROL Total Trait Population] 范围和日期范围。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 仅计 [!UICONTROL Rule-based Traits] 算。

1. （可选）将鼠标悬停在单个特征或区段上，以显示每个数据点的访问次数和日期。

   可以单击表中的列标题以按升序或降序对结果进行排序。

对于 [!UICONTROL Trended Trait] 报告，零表示未 [!DNL Audience Manager] 收集该日的数据。 空条目表示特征不存在。 以下示例显示了两种类型条目的示例：

![](assets/trended_data.png)
