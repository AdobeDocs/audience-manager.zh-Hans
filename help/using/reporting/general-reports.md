---
description: “常规”报告返回特征、区段和目标的性能数据。
seo-description: Audience Manager中的常规报告返回特征、细分和目标的绩效数据。
seo-title: Audience Manager中的一般报告
solution: Audience Manager
title: 一般报告
uuid: cea75a0-969e-4ee3-971a-60b91111e52
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# General Reports{#general-reports}

[!UICONTROL General] 报告返回特征、区段和目标的绩效数据。

## 概述 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] uses [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])将用户组权限扩展到 [!UICONTROL General] 报告。用户只能查看报告中具有查看权限的特征和区段。[!UICONTROL RBAC] 功能允许您控制内部团队能够查看哪些报告数据。例如，管理不同广告商帐户的代理可以配置用户组权限，以使管理Advertiser A帐户的团队无法看到Advertiser B的报告数据。

Run a [!UICONTROL General] report when you need to:

* 按特征、细分或目标审查性能。
* 以1、7、14、30、60、90天和终生间隔跟踪印象(总数和唯一值)。
* 查看总计和唯一加载计数。
* 比较特征和细分性能。
* 确定强大或不良的性能特征和细分，分析需求，或将加载/触发数据与第三方报表进行比较。
* 导出数据(. csv格式)以进一步分析和共享。

The following illustration provides a high-level overview of key elements in the [!UICONTROL General] report.

![](assets/general_reports.png)

1. 配置以下选项：

   * **报告类型：** 选择所需的报告类型(特征、区段或目标)。

   * **对于日期通过：** 指定报告的日期范围。

2. 按名称或ID搜索特征、区段或目标。
3. From the folder list, drag and drop the traits, segments, or destinations you want to report to the [!UICONTROL Selections] panel on the right side.
4. 生成要在可导出表格中显示的报表。

## Run a General Report {#run-general-report}

This section describes how to run a [!UICONTROL General] report and set time and other performance options.

<!-- 

t_run_general_report.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL General Reports]**.
1. From the **[!UICONTROL Report Type]** drop-down list, select the desired type: Trait, Segment, or Destination.
1. *条件* 单击日期框以显示日历，然后如果要指定其他日期，则选择报告的结束日期。
1. 按名称或ID搜索特征、区段或目标。
1. From the folder list, drag and drop the traits, segments, or destinations you want to report to the [!UICONTROL Selections] panel on the right side.
1. 单击 **[!UICONTROL Run Report]**.

   结果显示在可导出的表中。单击列标题可按升序或降序对结果进行排序。
1. Select the desired option button at the top of the report to filter data by performance ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], or [!UICONTROL Total Trait Population]) or by time (1, 7, 14, 30, 60, 90-day range or lifetime).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 仅供计算。[!UICONTROL Rule-based Traits]

1. *可选* 单击 **[!UICONTROL Export to CSV]**。This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

## General Reports Results Explained {#general-reports-explained}

The numbers in the [!UICONTROL General Reports] are generated directly from our [!UICONTROL User Profile Store]. The results reflect the number of users that [!DNL Audience Manager] contained in the backend at the time these reporting numbers were generated.

* 这些数字不包括流量过多的访客ID。在到达后端系统之前，筛选机器人中的流量。此外，在后台运行每周清理作业时，将丢弃一些机器人程序流量。
* If you onboard data via inbound processing keyed off the [!DNL Audience Manager] UUID, and these IDs include users that are no longer active in our system, these inactive [!DNL Audience Manager] UUIDs never reach the [!UICONTROL User Profile Store] and are not reported.
* [!UICONTROL Total Trait Realizations] 仅供计算。[!UICONTROL Rule-based Traits]

## General Reports Results for Traits {#general-report-results-traits}

The metrics below are available when you run a General report and select **[!UICONTROL Trait]** as the report type:

**独特特征真实性**

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. 例如，如果用户在10/1日访问了您的主页三次，您将看到一个唯一特征实现。

**特征真实性**

此量度表示在选定时间范围内特征激发的特征总数。例如，如果某个用户访问了您的主页，然后导航到您的技术新闻和您的体育新闻部分，它们将在“常规报告”中显示为三个特征实时真实性，以及一个独特的特征实现。

**特征总数**

此量度表示当前符合特征的Audience Manager UUID的总量。使用此数字可了解可用于细分和定位的用户总数。Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). 例如，今天访问您的主页三次且永远不会返回的用户将一直作为该人口的一名用户，直到自现在起120天。在120天内，将从人群中删除这些标记。Read our [Trait Qualification Reference](../features/traits/trait-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

下图显示了为特征报告类型运行常规报告的结果。

![](assets/general_reports_metrics.png)

## General Reports Results for Segments {#general-report-results-segments}

The metrics below are available when you run a General report and select **[!UICONTROL Segment]** as the report type:

**实时细分群体**

此量度表示特定访客在指定时间范围内实时查看的实际数量，以及Audience Manager查看时获得区段的实际数量。

**总细分人口**

此量度表示在选定的回顾期内符合区段资格的Audience Manager UUID的总数。您的天总细分人口是定位定位最准确的用户群。

>[!NOTE]
>
>Select **[!UICONTROL Include Destination Mappings]** to see a breakdown of segment population for activated destinations.

下图显示了运行区段报告类型的常规报告的结果。

![](assets/general_reports_segment_metrics.png)

## General Reports Results for Destinations {#general-report-results-destinations}

The metrics below are available when you run a General report and select **[!UICONTROL Destination]** as the report type:

**实时细分群体**

此量度表示特定访客在指定时间范围内实时查看的实际数量，以及Audience Manager查看时获得区段的实际数量。

**总细分人口**

此量度表示属于返回期间内的区段的Audience Manager UI总数，该区段被发送到目标。

下图显示了运行目标报告类型的常规报告的结果。

![](assets/general_reports_destinations.png)
