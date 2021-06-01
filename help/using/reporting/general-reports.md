---
description: 常规报表会返回有关特征、区段和目标的性能数据。
seo-description: Audience Manager中的常规报表可返回有关特征、区段和目标的性能数据。
seo-title: 常规报表Audience Manager
solution: Audience Manager
title: 常规报表
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: 常规报表和趋势报表
exl-id: dc16a821-b776-4a04-af60-4b8c914253dd
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

[!DNL Audience Manager] 使 [!UICONTROL Role Based Access Control] 用([!UICONTROL RBAC])扩展报表的用户群组权 [!UICONTROL General] 限。用户只能在报表中查看他们有权查看的那些特征和区段。 [!UICONTROL RBAC] 功能允许您控制内部团队可以查看哪些报表数据。例如，管理不同广告商帐户的代理可以配置用户群组权限，以便管理广告商A帐户的团队无法查看广告商B的报表数据。

在需要执行以下操作时运行[!UICONTROL General]报表：

* 按特征、区段或目标查看性能。
* 以1、7、14、30、60和90天为间隔跟踪展示次数（总和独特）。
* 查看总负载和唯一负载计数。
* 比较特征和区段性能。
* 识别性能强弱的特征和区段、分析需求或将负载/火灾数据与第三方报表进行比较。
* 导出数据（.csv格式），以便进一步分析和共享。

下图提供了[!UICONTROL General]报表中关键元素的高级概述。

![](assets/general_reports.png)

1. 配置以下选项：

   * **报表类型：** 选择所需的报表类型（特征、区段或目标）。

   * **对于日期至：** 指定报表的日期范围。

2. 按名称或ID搜索特征、区段或目标。
3. 从文件夹列表中，将要报告的特征、区段或目标拖放到右侧的[!UICONTROL Selections]面板。
4. 生成要在可导出的表中显示的报告。

## 运行常规报表{#run-general-report}

本节介绍如何运行[!UICONTROL General]报表，以及设置时间和其他性能选项。

<!-- 

t_run_general_report.xml

 -->

1. 在&#x200B;**[!UICONTROL Analytics]**&#x200B;功能板中，单击&#x200B;**[!UICONTROL General Reports]**。
1. 从&#x200B;**[!UICONTROL Report Type]**&#x200B;下拉列表中，选择所需的类型：特征、区段或目标。
1. ** 视情况单击日期框以显示日历，然后选择报表的结束日期（如果要指定除今天以外的日期）。
1. 按名称或ID搜索特征、区段或目标。
1. 从文件夹列表中，将要报告的特征、区段或目标拖放到右侧的[!UICONTROL Selections]面板。
1. 单击 **[!UICONTROL Run Report]**.

   结果显示在可导出的表中。 单击列标题可对结果进行升序或降序排序。
1. 选择报表顶部的所需选项按钮，按性能（[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]或[!UICONTROL Total Trait Population]）或时间（1、7、14、30、60或90天范围）过滤数据。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 仅计 [!UICONTROL Rule-based Traits] 算。

1. ** 可选单击 **[!UICONTROL Export to CSV]**。这会导出所有日期范围的[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]和[!UICONTROL Total Trait Population]。

## 常规报表结果说明{#general-reports-explained}

[!UICONTROL General Reports]中的数字直接从我们的[!UICONTROL User Profile Store]中生成。 结果反映生成这些报表数量时后端包含[!DNL Audience Manager]的用户数。

* 这些数字不包括流量过多的访客ID。 在到达后端系统之前，会过滤来自机器人的流量。 此外，在后端运行的每周清理作业期间，会丢弃某些机器人流量。
* 如果您通过以[!DNL Audience Manager] UUID作为关键字的入站处理载入数据，并且这些ID包含的用户在我们的系统中不再处于活动状态，则这些不活动的[!DNL Audience Manager] UUID将永远不会到达[!UICONTROL User Profile Store]，并且也不会被报告。
* [!UICONTROL Total Trait Realizations] 仅计 [!UICONTROL Rule-based Traits] 算。

## 特征{#general-report-results-traits}的常规报表结果

运行常规报表并选择&#x200B;**[!UICONTROL Trait]**&#x200B;作为报表类型时，可以使用以下过滤器。

按[!UICONTROL Device ID]过滤结果时：

* [!UICONTROL Unique Trait Realizations] 是在选定时间范围内将特征添加到其配置文件的匿名设备访客数量。
* [!UICONTROL Total Trait Realization] 是选定时间范围内的匿名特征实现总数。
* [!UICONTROL Total Trait Population] 是您的匿名设备访客在其配置文件中具有此特征的数量。

![一般报告特征设备](assets/general-report-traits-deviceid.png)

按[!UICONTROL Cross-Device ID]过滤结果时：

* [!UICONTROL Unique Trait Realizations] 是指在选定的时间范围内，已通过身份验证的将特征添加到其配置文件的访客数。
* [!UICONTROL Total Trait Realization] 是选定时间范围内经过身份验证的特征实现的总数。
* [!UICONTROL Total Trait Population] 是已通过身份验证的访客在其配置文件中具有此特征的数量。

![通用报告特征 — 跨设备](assets/general-report-traits-cross-device.png)

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


## 区段{#general-report-results-segments}的常规报表结果

运行常规报表并选择&#x200B;**[!UICONTROL Segment]**&#x200B;作为报表类型时，可以使用以下量度：

### 实时区段人口

此量度表示在指定时间范围内实时查看的独特访客的实际数量，以及在Audience Manager看到符合区段资格条件的独特访客。

### 总区段人口

此量度表示在您选择的回顾期间内符合区段资格条件的Audience ManagerUUID总数。 1天的总区段人口代表了用于定位的最准确用户群。

>[!NOTE]
>
>选择&#x200B;**[!UICONTROL Include Destination Mappings]**&#x200B;可查看已激活目标的区段群体细分。

下图显示了为区段报表类型运行常规报表的结果。

![](assets/general_reports_segment_metrics.png)

## 目标{#general-report-results-destinations}的常规报表结果

运行常规报表并选择&#x200B;**[!UICONTROL Destination]**&#x200B;作为报表类型时，可以使用以下量度：

**实时区段人口**

此量度表示在指定时间范围内实时查看的独特访客的实际数量，以及在Audience Manager看到符合区段资格条件的独特访客。

**总区段人口**

此量度表示在回顾期间内，发送到目标的属于某个区段的Audience ManagerUUID总数。

下图显示了为目标报表类型运行常规报表的结果。

![](assets/general_reports_destinations.png)
