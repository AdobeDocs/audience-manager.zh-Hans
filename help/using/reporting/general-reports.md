---
description: “一般”报表返回有关特征、区段和目标的性能数据。
seo-description: Audience Manager中的“常规”报表会返回特征、区段和目标的性能数据。
seo-title: Audience Manager中的常规报告
solution: Audience Manager
title: 常规报表
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: general & trend reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 1%

---


# 常规报表{#general-reports}

报 [!UICONTROL General] 表会返回特征、区段和目标的性能数据。

## 概述 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])将用户组权限扩展到报 [!UICONTROL General] 表。 用户只能在报告中看到他们具有视图权限的那些特征和区段。 [!UICONTROL RBAC] 功能，您可以控制内部团队能够报告哪些视图数据。 例如，管理不同广告商帐户的代理可以配置用户组权限，以便管理广告商A帐户的团队无法看到广告商B的报告数据。

在需要 [!UICONTROL General] 时运行报告：

* 按特征、区段或目标查看性能。
* 按1天、7天、14天、30天、60天和90天间隔跟踪展示次数（总数和唯一数）。
* 查看总负载和唯一负载计数。
* 比较特征和区段性能。
* 确定性能特征和细分，分析需求，或将负载／火灾数据与第三方报告进行比较。
* 导出数据（.csv格式）以进一步分析和共享。

下图提供了报告中关键元素的高级概 [!UICONTROL General] 述。

![](assets/general_reports.png)

1. 配置以下选项：

   * **报告类型：** 选择所需的报表类型（特征、区段或目标）。

   * **日期至：** 指定报表的日期范围。

2. 按名称或ID搜索特征、区段或目标。
3. 在文件夹列表中，将要报告的特征、区段或目标拖放到右 [!UICONTROL Selections] 侧的面板中。
4. 生成要在可导出表中显示的报告。

## Run a General Report {#run-general-report}

本节介绍如何运行报 [!UICONTROL General] 告并设置时间和其他性能选项。

<!-- 

t_run_general_report.xml

 -->

1. 在仪表板 **[!UICONTROL Analytics]** 中，单击 **[!UICONTROL General Reports]**。
1. 从下 **[!UICONTROL Report Type]** 拉列表中，选择所需的类型： 特征、区段或目标。
1. *条件* ：单击日期框以显示日历，如果要指定非今天的日期，请选择报表的结束日期。
1. 按名称或ID搜索特征、区段或目标。
1. 在文件夹列表中，将要报告的特征、区段或目标拖放到右 [!UICONTROL Selections] 侧的面板中。
1. 单击 **[!UICONTROL Run Report]**.

   结果显示在可导出的表中。 单击列标题以按升序或降序对结果进行排序。
1. 选择报告顶部的所需选项按钮，按性能( [!UICONTROL Unique Trait Realizations]、 [!UICONTROL Total Trait Realizations]或 [!UICONTROL Total Trait Population])或时间（1、7、14、30、60或90天范围）筛选数据。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 只计 [!UICONTROL Rule-based Traits] 算。

1. *可选* ，单 **[!UICONTROL Export to CSV]**&#x200B;击。 这将导出 [!UICONTROL Unique Trait Realizations]所有 [!UICONTROL Total Trait Realizations]日期 [!UICONTROL Total Trait Population] 范围和范围。

## 一般报告结果说明 {#general-reports-explained}

中的数字 [!UICONTROL General Reports] 直接由我们生 [!UICONTROL User Profile Store]成。 结果反映生成这些报告 [!DNL Audience Manager] 号时后端包含的用户数。

* 这些数字不包括流量过多的访客ID。 在到达我们的后端系统之前，会过滤来自机器人程序的流量。 此外，在后端运行的每周清除作业期间，会丢弃一些bot通信。
* 如果通过与UUID锁定的入站处理来建立数 [!DNL Audience Manager] 据，并且这些ID包括系统中不再处于活动状态的用户，则这些不活动的 [!DNL Audience Manager] UUID将不会 [!UICONTROL User Profile Store] 到达并报告。
* [!UICONTROL Total Trait Realizations] 只计 [!UICONTROL Rule-based Traits] 算。

## 特征的常规报告结果 {#general-report-results-traits}

运行“常规”报表并选择报告类型时， **[!UICONTROL Trait]** 可使用以下过滤器。

按以下方式筛选结果时 [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] 是在所选时间范围内将特征添加到其访客的匿名设备用户档案数。
* [!UICONTROL Total Trait Realization] 是所选时间范围内的匿名特征实现总数。
* [!UICONTROL Total Trait Population] 是匿名设备访客在其用户档案上具有此特征的数量。

![一般报告特征设备](assets/general-report-traits-deviceid.png)

按以下方式筛选结果时 [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] 是在所选时间范围内已验证的访客将特征添加到其用户档案的数量。
* [!UICONTROL Total Trait Realization] 是所选时间范围内经过身份验证的特征实现的总数。
* [!UICONTROL Total Trait Population] 是已验证的访客在其用户档案上具有此特征的数量。

![通用报告特征——跨设备](assets/general-report-traits-cross-device.png)

<!-- 
### Unique Trait Realizations

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. For example, if a user visited your homepage three times on 10/1, you would see one Unique Trait Realization.

### Total Trait Realizations

This metric represents the total amount of trait fires for the trait in your selected time range. For example, if a user visited your homepage, then navigated to your tech news and your sports news sections, they would appear in the General Report as three total trait realizations, and one unique trait realization.

### Total Trait Population

This metric represents the total amount of Audience Manager UUIDs that are currently qualified for the trait. Use this number to understand the total amount of users you could use for segmentation and targeting. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). For example, a user visiting your homepage three times today and never returning afterwards, would remain as a user in this population every day until 120 days from now. At the 120 day mark, they would be removed from the population. Read our [Trait and Segment Qualification Reference](../features/traits/trait-and-segment-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

The illustration below shows the results of running a general report for the Trait report type. -->
<!-- 
![](assets/general_reports_metrics.png) -->


## 一般报告区段结果 {#general-report-results-segments}

运行“常规”报表并选择报告类型时，可 **[!UICONTROL Segment]** 以使用以下指标：

### 实时细分填充

此度量表示在指定时间范围内实时查看的唯一访客的实际数量，以及在Audience Manager看到这些数据时，哪些数据符合区段的条件。

### 区段总人口

此度量表示在您选择的回顾期内限定区段的Audience ManagerUUID总数。 1天的总细分人口是您进行定位的最准确用户群。

>[!NOTE]
>
>选择 **[!UICONTROL Include Destination Mappings]** 以查看已激活目标的细分区段填充。

下图显示了为区段报表类型运行常规报表的结果。

![](assets/general_reports_segment_metrics.png)

## 目标的常规报告结果 {#general-report-results-destinations}

运行“常规”报表并选择报告类型时，可 **[!UICONTROL Destination]** 以使用以下指标：

**实时细分填充**

此度量表示在指定时间范围内实时查看的唯一访客的实际数量，以及在Audience Manager看到这些数据时，哪些数据符合区段的条件。

**区段总人口**

此度量表示在回顾期间内属于区段的Audience ManagerUUID的总数，这些UUID被发送到目标。

下图显示了为目标报告类型运行常规报告的结果。

![](assets/general_reports_destinations.png)
