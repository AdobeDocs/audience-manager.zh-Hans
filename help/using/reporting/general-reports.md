---
description: “常规”报表返回有关特征、区段和目标的性能数据。
seo-description: Audience Manager中的“常规”报表返回有关特征、区段和目标的性能数据。
seo-title: 一般报告Audience Manager
solution: Audience Manager
title: 常规报表
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: 一般和趋势报表
exl-id: dc16a821-b776-4a04-af60-4b8c914253dd
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 1%

---

# 常规报表{#general-reports}

[!UICONTROL General]报表返回有关特征、区段和目标的性能数据。

## 概述 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])将用户组权限扩展到报 [!UICONTROL General] 表。用户只能在报告中看到他们有权访问视图的那些特征和区段。 [!UICONTROL RBAC] 功能，您可以控制内部团队能够视图的报告数据。例如，管理不同广告商帐户的代理可以配置用户组权限，以便管理广告商A帐户的团队无法看到广告商B的报告数据。

需要时运行[!UICONTROL General]报告：

* 按特征、区段或目标查看性能。
* 以1、7、14、30、60和90天间隔跟踪展示次数（总数和唯一数）。
* 查看总负载和唯一负载计数。
* 比较特征和区段性能。
* 识别强或弱的性能特征和细分，分析需求，或将负载/火灾数据与第三方报告进行比较。
* 导出数据（.csv格式）以进一步分析和共享。

下图提供了[!UICONTROL General]报告中关键元素的高级概述。

![](assets/general_reports.png)

1. 配置以下选项：

   * **报表类型：** 选择所需的报表类型（特征、区段或目标）。

   * **对于截止日期：** 指定报表的日期范围。

2. 按名称或ID搜索特征、区段或目标。
3. 在文件夹列表中，将要报告的特征、区段或目标拖放到右侧的[!UICONTROL Selections]面板。
4. 生成要在可导出表中显示的报表。

## 运行常规报告{#run-general-report}

本节介绍如何运行[!UICONTROL General]报告并设置时间和其他性能选项。

<!-- 

t_run_general_report.xml

 -->

1. 在&#x200B;**[!UICONTROL Analytics]**&#x200B;仪表板中，单击&#x200B;**[!UICONTROL General Reports]**。
1. 从&#x200B;**[!UICONTROL Report Type]**&#x200B;下拉列表中，选择所需的类型：特征、区段或目标。
1. *条* 件单击日期框以显示日历，如果要指定非今天的日期，请选择报表的结束日期。
1. 按名称或ID搜索特征、区段或目标。
1. 在文件夹列表中，将要报告的特征、区段或目标拖放到右侧的[!UICONTROL Selections]面板。
1. 单击 **[!UICONTROL Run Report]**.

   结果显示在可导出的表中。 单击列标题可按升序或降序对结果排序。
1. 选择报表顶部所需的选项按钮，按性能（[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]或[!UICONTROL Total Trait Population]）或时间（1、7、14、30、60或90天范围）筛选数据。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 仅计 [!UICONTROL Rule-based Traits] 算。

1. *可* 选单 **[!UICONTROL Export to CSV]**&#x200B;击。这将导出所有日范围的[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]和[!UICONTROL Total Trait Population]。

## 常规报告结果说明{#general-reports-explained}

[!UICONTROL General Reports]中的数字直接由我们的[!UICONTROL User Profile Store]生成。 结果反映生成这些报告号时后端中包含的[!DNL Audience Manager]用户数。

* 这些数字不包括流量过大的访客ID。 在到达我们的后端系统之前，会过滤来自机器人程序的流量。 此外，在后端运行的每周清理作业期间，会丢弃某些机器人通信。
* 如果通过与[!DNL Audience Manager] UUID进行键控的入站处理来建立数据，并且这些ID包括在系统中不再处于活动状态的用户，则这些不活动的[!DNL Audience Manager] UUID永远不会到达[!UICONTROL User Profile Store]并且不会报告。
* [!UICONTROL Total Trait Realizations] 仅计 [!UICONTROL Rule-based Traits] 算。

## 特征{#general-report-results-traits}的常规报告结果

运行“常规”报告并选择&#x200B;**[!UICONTROL Trait]**&#x200B;作为报告类型时，以下过滤器可用。

按[!UICONTROL Device ID]筛选结果时：

* [!UICONTROL Unique Trait Realizations] 是在选定时间范围内将特征添加到其访客的匿名设备用户档案的数量。
* [!UICONTROL Total Trait Realization] 是所选时间范围内的匿名特征实现总数。
* [!UICONTROL Total Trait Population] 是您的匿名设备访客在其用户档案上具有此特征的数量。

![一般报告特征设备](assets/general-report-traits-deviceid.png)

按[!UICONTROL Cross-Device ID]筛选结果时：

* [!UICONTROL Unique Trait Realizations] 是在所选时间范围内向其用户档案添加特征的已验证访客的数量。
* [!UICONTROL Total Trait Realization] 是所选时间范围内经过身份验证的特征实现的总数。
* [!UICONTROL Total Trait Population] 是已验证的访客在其用户档案上具有此特征的数量。

![通用报告 — traits-cross-device](assets/general-report-traits-cross-device.png)

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


## 区段{#general-report-results-segments}的常规报告结果

运行“常规”报表并选择&#x200B;**[!UICONTROL Segment]**&#x200B;作为报表类型时，可使用以下量度：

### 实时细分填充

此量度表示在指定时间范围内实时查看的唯一访客的实际数量，以及在Audience Manager看到这些数据时，哪些数据符合区段条件。

### 区段总人口

此量度表示在您选择的回顾期间内为区段限定的Audience ManagerUUID总数。 1天的总细分人口是您最准确的定位用户群。

>[!NOTE]
>
>选择&#x200B;**[!UICONTROL Include Destination Mappings]**&#x200B;可查看已激活目标的细分区段填充。

下图显示了为区段报表类型运行常规报表的结果。

![](assets/general_reports_segment_metrics.png)

## 目标{#general-report-results-destinations}的常规报告结果

运行“常规”报表并选择&#x200B;**[!UICONTROL Destination]**&#x200B;作为报表类型时，可使用以下量度：

**实时细分填充**

此量度表示在指定时间范围内实时查看的唯一访客的实际数量，以及在Audience Manager看到这些数据时，哪些数据符合区段条件。

**区段总人口**

此量度表示在回顾期间内，发送到目标的属于区段的Audience ManagerUUID的总数。

下图显示了为目标报告类型运行常规报告的结果。

![](assets/general_reports_destinations.png)
