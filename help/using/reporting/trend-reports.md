---
description: 趋势报表可返回有关特征和区段的趋势数据。
seo-description: 趋势报表可返回有关特征和区段的趋势数据。
seo-title: 趋势报表
solution: Audience Manager
title: 趋势报表
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: 常规报表和趋势报表
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---

# 趋势报表{#trend-reports}

趋势报表可返回有关特征和区段的趋势数据。

## 概述 {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] 使 [!UICONTROL Role Based Access Control] 用([!UICONTROL RBAC])扩展报表的用户群组权 [!UICONTROL Trend] 限。用户只能在报表中查看他们有权查看的那些特征和区段。 [!UICONTROL RBAC] 功能允许您控制内部团队可以查看哪些报表数据。

例如，管理不同广告商帐户的代理可以配置用户群组权限，以便管理广告商A帐户的团队无法查看广告商B的报表数据。

在需要执行以下操作时运行[!UICONTROL Trend]报表：

* 按特征和区段查看趋势数据。
* 按1、7、14、30、60和90天间隔跟踪趋势。
* 比较特征和区段随时间变化的趋势。
* 识别性能强弱的特征和区段。
* 导出数据（.csv格式），以便进一步分析和共享。

下图提供了[!UICONTROL Trend]报表中关键元素的高级概述。

![](assets/trend_reports.png)

1. 配置以下选项：
   **报表类型：** 选择所需的报表类型（特征或区段）。
   **日期范围：** 指定报表的日期范围（开始日期和结束日期）。
   **显示间隔：** 指定显示间隔（1、7、14、30、60和90天间隔）。
1. 按名称或ID搜索特征或区段。
1. 从文件夹列表中，将要报告的特征或区段拖放到右侧的[!UICONTROL Selections]面板。
1. 生成报表以图形格式显示，或将报表导出为CSV格式。

## 运行趋势报表{#run-trend-report}

此过程说明如何运行[!UICONTROL Trend]报告。

<!-- 

t_working_with_trend_reports.xml

 -->

1. 在&#x200B;**[!UICONTROL Analytics]**&#x200B;功能板中，单击&#x200B;**[!UICONTROL Trend Reports]**。
1. 从&#x200B;**[!UICONTROL Report Type]**&#x200B;下拉列表中，选择所需的类型：**[!UICONTROL Trait]**&#x200B;或&#x200B;**[!UICONTROL Segment]**。
1. 单击日期框以显示日历，然后选择报表的开始和结束日期。
1. 指定显示间隔：1、7、14、30、60或90天。
1. 按名称或ID搜索特征或区段。
1. 从文件夹列表中，将要报告的特征或区段拖放到右侧的[!UICONTROL Selections]面板。
   * 为获得最佳性能，请一次对少于20个特征或区段运行[!UICONTROL Trend]报表。
1. 单击&#x200B;**[!UICONTROL Graph Traits]**&#x200B;或&#x200B;**[!UICONTROL Graph Segments]**，具体取决于您查看的报表类型（特征或区段）。 这些选项仅忽略单独选择的特征或区段的所有文件夹和图形。

   或

   单击&#x200B;**[!UICONTROL Export to CSV]**&#x200B;以CSV格式导出特征或区段数据以及所有文件夹，以便进一步分析和共享。 这会导出所有日期范围的[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]和[!UICONTROL Total Trait Population]。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 仅计 [!UICONTROL Rule-based Traits] 算。

1. （可选）将鼠标悬停在单个特征或区段上，可显示每个数据点的访问次数和日期。 您可以单击表中的列标题，以对结果进行升序或降序排序。

## 特征{#trend-report-results-traits}的趋势报表结果

运行[!UICONTROL Trend Report]并选择&#x200B;**[!UICONTROL Trait]**&#x200B;作为报表类型时，可以使用以下过滤器。

按[!UICONTROL Device ID]过滤结果时：

* [!UICONTROL Unique Trait Realizations] 是在选定时间范围内将特征添加到其配置文件的匿名设备访客数量。
* [!UICONTROL Total Trait Realization] 是选定时间范围内匿名鼠标特征实现的总数。
* [!UICONTROL Total Trait Population] 是您的匿名设备访客在其配置文件中具有此特征的数量。

按[!UICONTROL Cross-Device ID]过滤结果时：

* [!UICONTROL Unique Trait Realizations] 是指在选定的时间范围内，已通过身份验证的将特征添加到其配置文件的访客数。
* [!UICONTROL Total Trait Realization] 是选定时间范围内经过身份验证的特征实现的总数。
* [!UICONTROL Total Trait Population] 是已通过身份验证的访客在其配置文件中具有此特征的数量。

![trend-report-traits](assets/trend-report-traits.png)

零表示[!DNL Audience Manager]未收集当天的数据。 空白条目表示特征不存在。

请观看以下视频，详细了解跨设备量度的工作方式。

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## 区段{#segment-report-results-traits}的趋势报表结果

运行[!UICONTROL Trend Report]并选择&#x200B;**[!UICONTROL Segments]**&#x200B;作为报表类型时，可以使用以下过滤器。

* **[!UICONTROL Real-time Segment Population]**:选定时间范围内符合区段资格条件的访客数。
* **[!UICONTROL Total Segment Population]**:符合区段资格的访客总数。

![趋势报表区段](assets/trend-report-segments.png)
