---
description: 趋势报表会返回有关特征和区段的趋势数据。
seo-description: A Trend report returns trend data on traits and segments.
seo-title: Trend Reports
solution: Audience Manager
title: 趋势报表
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: General & Trend Reports
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# 趋势报表{#trend-reports}

趋势报表会返回有关特征和区段的趋势数据。

## 概述 {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager]使用[!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])将用户组权限扩展到[!UICONTROL Trend]报告。 用户只能在报告中看到他们有权查看的特征和区段。 通过[!UICONTROL RBAC]功能，您可以控制内部团队可以查看哪些报表数据。

例如，管理不同广告商帐户的机构可以配置用户组权限，这样管理广告商A帐户的团队将无法查看广告商B的报表数据。

在您需要以下任务时运行[!UICONTROL Trend]报告：

* 按特征和区段查看趋势数据。
* 按1、7、14、30、60和90天间隔跟踪趋势。
* 比较一段时间内特征和区段趋势。
* 识别性能强或性能低下的特征和区段。
* 导出数据（.csv格式）以供进一步分析和共享。

下图提供了[!UICONTROL Trend]报表中关键元素的高级概述。

![](assets/trend_reports.png)

1. 配置以下选项：
   **报表类型：**&#x200B;选择所需的报表类型（特征或区段）。
   **日期范围：**&#x200B;指定报表的日期范围（开始日期和结束日期）。
   **显示间隔：**&#x200B;指定显示间隔（1、7、14、30、60和90天间隔）。
1. 按名称或ID搜索特征或区段。
1. 从文件夹列表中，将要报告的特征或区段拖放到右侧的[!UICONTROL Selections]面板。
1. 生成报告以图形格式显示数据或将报告导出为CSV格式。

## 运行趋势报表 {#run-trend-report}

此过程说明如何运行[!UICONTROL Trend]报告。

<!-- 

t_working_with_trend_reports.xml

 -->

1. 在&#x200B;**[!UICONTROL Analytics]**&#x200B;仪表板中，单击&#x200B;**[!UICONTROL Trend Reports]**。
1. 从&#x200B;**[!UICONTROL Report Type]**&#x200B;下拉列表中选择所需的类型： **[!UICONTROL Trait]**&#x200B;或&#x200B;**[!UICONTROL Segment]**。
1. 单击日期框以显示日历，然后为您的报表选择开始日期和结束日期。
1. 指定显示间隔：1、7、14、30、60或90天。
1. 按名称或ID搜索特征或区段。
1. 从文件夹列表中，将要报告的特征或区段拖放到右侧的[!UICONTROL Selections]面板。
   * 为获得最佳性能，一次对少于20个特征或区段运行[!UICONTROL Trend]报表。
1. 根据您查看的报告类型（特征或区段），单击&#x200B;**[!UICONTROL Graph Traits]**&#x200B;或&#x200B;**[!UICONTROL Graph Segments]**。 这些选项忽略所有文件夹并只显示单独选定的特征或区段。

   或

   单击&#x200B;**[!UICONTROL Export to CSV]**&#x200B;可将特征或区段数据和所有文件夹导出为CSV格式，以供进一步分析和共享。 这会导出所有日期范围的[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]和[!UICONTROL Total Trait Population]。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations]仅针对[!UICONTROL Rule-based Traits]进行计算。

1. （可选）将鼠标悬停在单个特征或区段上可显示每个数据点的访问次数和日期。 您可以单击表中的列标题以对结果进行升序或降序排序。

## 特征的趋势报表结果 {#trend-report-results-traits}

当您运行[!UICONTROL Trend Report]并选择&#x200B;**[!UICONTROL Trait]**&#x200B;作为报表类型时，以下筛选器可用。

按[!UICONTROL Device ID]筛选结果时：

* [!UICONTROL Unique Trait Realizations]是在所选时间范围内将特征添加到其配置文件的匿名设备访客数。
* [!UICONTROL Total Trait Realization]是所选时间范围内匿名鼠标特征实现的总数。
* [!UICONTROL Total Trait Population]是您的匿名设备访客在其个人资料中拥有此特征的人数。

按[!UICONTROL Cross-Device ID]筛选结果时：

* [!UICONTROL Unique Trait Realizations]是在所选时间范围内将特征添加到其配置文件的经过身份验证的访客数。
* [!UICONTROL Total Trait Realization]是所选时间范围内已验证的特征实现总数。
* [!UICONTROL Total Trait Population]是您的已验证访客在其个人资料中拥有此特征的数量。

![趋势报表特征](assets/trend-report-traits.png)

零表示[!DNL Audience Manager]未收集当天的数据。 空白条目表示该特征不存在。

请观看以下视频，详细了解跨设备量度的工作方式。

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## 区段的趋势报表结果 {#segment-report-results-traits}

当您运行[!UICONTROL Trend Report]并选择&#x200B;**[!UICONTROL Segments]**&#x200B;作为报表类型时，以下筛选器可用。

* **[!UICONTROL Real-time Segment Population]**：选定时间范围内符合区段资格的访客数。
* **[!UICONTROL Total Segment Population]**：符合区段资格的访客总数。

![趋势报表区段](assets/trend-report-segments.png)
