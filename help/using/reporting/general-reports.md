---
description: 常规报表可返回有关特征、区段和目标的性能数据。
seo-description: A General report in Audience Manager returns performance data on traits, segments, and destinations.
seo-title: General Reports in Audience Manager
solution: Audience Manager
title: 常规报表
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: General & Trend Reports
exl-id: dc16a821-b776-4a04-af60-4b8c914253dd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 0%

---

# 常规报表{#general-reports}

[!UICONTROL General]报表返回特征、区段和目标的性能数据。

## 概述 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager]使用[!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])将用户组权限扩展到[!UICONTROL General]报告。 用户只能在报告中看到他们有权查看的特征和区段。 通过[!UICONTROL RBAC]功能，您可以控制内部团队可以查看哪些报表数据。 例如，管理不同广告商帐户的机构可以配置用户组权限，这样管理广告商A帐户的团队将无法查看广告商B的报表数据。

在您需要以下任务时运行[!UICONTROL General]报告：

* 按特征、区段或目标查看绩效。
* 以1、7、14、30、60和90天为间隔跟踪展示次数（总计和唯一）。
* 查看总负载数和独特负载数。
* 比较特征和区段表现。
* 识别性能强或性能差的特性和区段，分析需求，或将加载/触发数据与第三方报表进行比较。
* 导出数据（.csv格式）以供进一步分析和共享。

下图提供了[!UICONTROL General]报表中关键元素的高级概述。

![](assets/general_reports.png)

1. 配置以下选项：

   * **报表类型：**&#x200B;选择所需的报表类型（特征、区段或目标）。

   * **对于截止日期：**&#x200B;指定报表的日期范围。

2. 按名称或ID搜索特征、区段或目标。
3. 从文件夹列表中，将要报告的特征、区段或目标拖放到右侧的[!UICONTROL Selections]面板。
4. 生成要显示在可导出表格中的报告。

## 运行常规报表 {#run-general-report}

本节介绍如何运行[!UICONTROL General]报告并设置时间和其他性能选项。

<!-- 

t_run_general_report.xml

 -->

1. 在&#x200B;**[!UICONTROL Analytics]**&#x200B;仪表板中，单击&#x200B;**[!UICONTROL General Reports]**。
1. 从&#x200B;**[!UICONTROL Report Type]**&#x200B;下拉列表中，选择所需的类型：特征、区段或目标。
1. *有条件*&#x200B;单击日期框以显示日历，如果要指定今天以外的日期，请选择报告的结束日期。
1. 按名称或ID搜索特征、区段或目标。
1. 从文件夹列表中，将要报告的特征、区段或目标拖放到右侧的[!UICONTROL Selections]面板。
1. 单击 **[!UICONTROL Run Report]**。

   结果会显示在可导出的表中。 单击列标题可将结果按升序或降序排序。
1. 选择报表顶部的所需选项按钮，以按性能（[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]或[!UICONTROL Total Trait Population]）或时间（1、7、14、30、60或90天范围）过滤数据。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations]仅针对[!UICONTROL Rule-based Traits]进行计算。

1. *可选*&#x200B;单击&#x200B;**[!UICONTROL Export to CSV]**。 这会导出所有日期范围的[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]和[!UICONTROL Total Trait Population]。

## 一般性报告结果解释 {#general-reports-explained}

[!UICONTROL General Reports]中的数字直接从我们的[!UICONTROL User Profile Store]生成。 结果反映了生成这些报表编号时[!DNL Audience Manager]包含在后端中的用户数。

* 这些数字不包括流量过多的访客ID。 来自机器人的流量在到达我们的后端系统之前会被过滤。 此外，在后端运行每周清理作业期间，还会丢弃某些机器人流量。
* 如果您通过以[!DNL Audience Manager] UUID为关键字的入站处理载入数据，并且这些ID包括系统中不再活动的用户，则这些非活动的[!DNL Audience Manager] UUID永远不会到达[!UICONTROL User Profile Store]，且不会报告。
* [!UICONTROL Total Trait Realizations]仅针对[!UICONTROL Rule-based Traits]进行计算。

## 特征的常规报表结果 {#general-report-results-traits}

运行常规报告并选择&#x200B;**[!UICONTROL Trait]**&#x200B;作为报告类型时，以下筛选器可用。

按[!UICONTROL Device ID]筛选结果时：

* [!UICONTROL Unique Trait Realizations]是在所选时间范围内将特征添加到其配置文件的匿名设备访客数。
* [!UICONTROL Total Trait Realization]是所选时间范围内的匿名特征实现总数。
* [!UICONTROL Total Trait Population]是您的匿名设备访客在其个人资料中拥有此特征的人数。

![general-report-traits-device](assets/general-report-traits-deviceid.png)

按[!UICONTROL Cross-Device ID]筛选结果时：

* [!UICONTROL Unique Trait Realizations]是在所选时间范围内将特征添加到其配置文件的经过身份验证的访客数。
* [!UICONTROL Total Trait Realization]是所选时间范围内已验证的特征实现总数。
* [!UICONTROL Total Trait Population]是您的已验证访客在其个人资料中拥有此特征的数量。

![general-report-traits-cross-device](assets/general-report-traits-cross-device.png)

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


## 常规报表区段结果 {#general-report-results-segments}

运行常规报告并选择&#x200B;**[!UICONTROL Segment]**&#x200B;作为报告类型时，以下量度可用：

### 实时区段人口

此量度表示在指定时间范围内实时查看的实际独特访客数量，以及在Audience Manager查看这些访客时符合区段资格条件的访客数量。

### 总区段人口

此指标表示在您选择的回顾期间内符合区段资格条件的Audience Manager UUID总数。 1天的总区段人口数代表了用于定位的最准确的用户群。

>[!NOTE]
>
>选择&#x200B;**[!UICONTROL Include Destination Mappings]**&#x200B;可查看已激活目标的区段人口细分。

下图显示了为“区段”报表类型运行常规报表的结果。

![](assets/general_reports_segment_metrics.png)

## 目标的常规报告结果 {#general-report-results-destinations}

运行常规报告并选择&#x200B;**[!UICONTROL Destination]**&#x200B;作为报告类型时，以下量度可用：

**实时区段填充**

此量度表示在指定时间范围内实时查看的实际独特访客数量，以及在Audience Manager查看这些访客时符合区段资格条件的访客数量。

总区段人口&#x200B;**&#x200B;**

此量度表示在回顾期间属于某个区段的、已发送到目标的Audience Manager UUID总数。

下图显示了针对“目标”报表类型运行常规报表的结果。

![](assets/general_reports_destinations.png)
