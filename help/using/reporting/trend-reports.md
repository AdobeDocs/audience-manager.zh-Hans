---
description: “趋势”报表返回有关特征和区段的趋势数据。
seo-description: “趋势”报表返回有关特征和区段的趋势数据。
seo-title: 趋势报告
solution: Audience Manager
title: 趋势报告
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
translation-type: tm+mt
source-git-commit: 760818663ff3eb32c6de876c756697e1d9034369

---


# 趋势报告{#trend-reports}

“趋势”报表返回有关特征和区段的趋势数据。

## 概述 {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])将用户组权限扩展到报 [!UICONTROL Trend] 表。 用户只能在报告中看到具有视图权限的那些特征和区段。 [!UICONTROL RBAC] 功能允许您控制内部团队能够视图的报告数据。

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
   **报告类型：** 选择所需的报告类型（特征或区段）。
   **日期范围：** 指定报表的日期范围(开始日期和结束日期)。
   **显示间隔：** 指定显示间隔（1、7、14、30、60和90天间隔）。
1. 按名称或ID搜索特征或区段。
1. 在文件夹列表中，将要报告的特征或区段拖放到右侧 [!UICONTROL Selections] 的面板中。
1. 生成报告以图形格式显示，或将报告导出为CSV格式。

## Run a Trend Report {#run-trend-report}

此过程介绍如何运行报 [!UICONTROL Trend] 告。

<!-- 

t_working_with_trend_reports.xml

 -->

1. 在仪表板 **[!UICONTROL Analytics]** 中，单击 **[!UICONTROL Trend Reports]**。
1. 从下 **[!UICONTROL Report Type]** 拉列表中，选择所需的类型：或 **[!UICONTROL Trait]** 者 **[!UICONTROL Segment]**。
1. 单击日期框以显示日历，然后选择报表的开始和结束日期。
1. 指定显示间隔：1、7、14、30、60或90天。
1. 按名称或ID搜索特征或区段。
1. 在文件夹列表中，将要报告的特征或区段拖放到右侧 [!UICONTROL Selections] 的面板中。
   * 为获得最佳性能，请 [!UICONTROL Trend] 一次运行少于20个特征或区段的报告。
1. 单击 **[!UICONTROL Graph Traits]** 或， **[!UICONTROL Graph Segments]**&#x200B;具体取决于您查看的报表类型（特征或区段）。 这些选项只忽略单独选择的特征或区段的所有文件夹和图形。

   或

   单 **[!UICONTROL Export to CSV]** 击以CSV格式导出特征或区段数据以及所有文件夹，以便进一步分析和共享。 这将导出 [!UICONTROL Unique Trait Realizations]所有 [!UICONTROL Total Trait Realizations]日期 [!UICONTROL Total Trait Population] 范围和日期范围。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 仅计 [!UICONTROL Rule-based Traits] 算。

1. （可选）将鼠标悬停在单个特征或区段上，以显示每个数据点的访问次数和日期。 可以单击表中的列标题以按升序或降序对结果进行排序。

## 特征的趋势报告结果 {#trend-report-results-traits}

当您运行并选择报告类型时， [!UICONTROL Trend Report] 以下过滤器 **[!UICONTROL Trait]** 将可用。

按以下方式筛选结果时 [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] 是在所选时间范围内将特征添加到其访客的匿名设备用户档案的数量。
* [!UICONTROL Total Trait Realization] 是所选时间范围内匿名鼠标特征实现的总数。
* [!UICONTROL Total Trait Population] 是您的匿名设备访客在其用户档案上具有此特征的数量。

按以下方式筛选结果时 [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] 是在所选时间范围内向其访客添加特征的已验证用户档案的数量。
* [!UICONTROL Total Trait Realization] 是所选时间范围内经过身份验证的特征实现的总数。
* [!UICONTROL Total Trait Population] 是已验证的访客中具有此特征的用户档案的数量。

![trend-report-traits](assets/trend-report-traits.png)

零表示没 [!DNL Audience Manager] 有收集该天的数据。 空条目表示特征不存在。

## 区段的趋势报告结果 {#segment-report-results-traits}

当您运行并选择报告类型时， [!UICONTROL Trend Report] 以下过滤器 **[!UICONTROL Segments]** 将可用。

* **[!UICONTROL Real-time Segment Population]**:选定时间范围内符合区段条件的访客数量。
* **[!UICONTROL Total Segment Population]**:符合该分部资格的访客总数。

![趋势报告段](assets/trend-report-segments.png)