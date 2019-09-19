---
description: “常规”报表返回有关特征、区段和目标的性能数据。
seo-description: Audience manager中的常规报表会返回有关特征、区段和目标的性能数据。
seo-title: Audience manager中的常规报告
solution: Audience Manager
title: 一般报告
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
translation-type: tm+mt
source-git-commit: 1c626c770208150d209d93f666b581113ada8de9

---


# 一般报告{#general-reports}

报告 [!UICONTROL General] 会返回有关特征、区段和目标的性能数据。

## 概述 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])将用户组权限扩展到报 [!UICONTROL General] 表。 用户只能在报告中看到他们有权查看的那些特征和区段。 [!UICONTROL RBAC] 功能允许您控制内部团队可以查看的报告数据。 例如，管理不同广告商帐户的代理可以配置用户组权限，以便管理广告商A帐户的团队无法看到广告商B的报告数据。

在需要 [!UICONTROL General] 时运行报告：

* 按特征、区段或目标查看性能。
* 以1天、7天、14天、30天、60天和90天间隔跟踪展示次数（总数和唯一数）。
* 查看总负载和唯一负载计数。
* 比较特征和区段性能。
* 识别强或弱的性能特征和细分，分析需求，或将负载／火灾数据与第三方报告进行比较。
* 导出数据（.csv格式）以进一步分析和共享。

下图提供了报告中关键元素的高级概 [!UICONTROL General] 述。

![](assets/general_reports.png)

1. 配置以下选项：

   * **** 报告类型：选择所需的报告类型（特征、区段或目标）。

   * **** 对于日期至：指定报表的日期范围。

2. 按名称或ID搜索特征、区段或目标。
3. 从文件夹列表中，将要报告的特征、区段或目标拖放到右 [!UICONTROL Selections] 侧的面板中。
4. 生成要在可导出表中显示的报告。

## Run a General Report {#run-general-report}

本节介绍如何运行报告， [!UICONTROL General] 并设置时间和其他性能选项。

<!-- 

t_run_general_report.xml

 -->

1. 在功能 **[!UICONTROL Analytics]** 板中，单击 **[!UICONTROL General Reports]**。
1. 从下 **[!UICONTROL Report Type]** 拉列表中，选择所需的类型：特征、区段或目标。
1. *条件* ：单击日期框以显示日历，如果要指定非今天的日期，请选择报表的结束日期。
1. 按名称或ID搜索特征、区段或目标。
1. 从文件夹列表中，将要报告的特征、区段或目标拖放到右 [!UICONTROL Selections] 侧的面板中。
1. 单击 **[!UICONTROL Run Report]**.

   结果显示在可导出的表中。 单击列标题以按升序或降序对结果进行排序。
1. 选择报告顶部的所需选项按钮，按性能( [!UICONTROL Unique Trait Realizations]、 [!UICONTROL Total Trait Realizations]或 [!UICONTROL Total Trait Population])或时间（1、7、14、30、60或90天范围）筛选数据。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 仅计 [!UICONTROL Rule-based Traits] 算。

1. *可选* ，单击 **[!UICONTROL Export to CSV]**。 这将导出 [!UICONTROL Unique Trait Realizations]所有 [!UICONTROL Total Trait Realizations]日期 [!UICONTROL Total Trait Population] 范围和日期范围。

## 常规报告结果说明 {#general-reports-explained}

中的数字直 [!UICONTROL General Reports] 接由我们生成 [!UICONTROL User Profile Store]。 结果反映生成这些报告 [!DNL Audience Manager] 编号时后端包含的用户数。

* 这些数字不包括流量过大的访客ID。 在到达我们的后端系统之前，会先过滤来自机器人程序的流量。 此外，在后端运行的每周清除作业期间，会丢弃一些机器人流量。
* 如果通过已键出 [!DNL Audience Manager] UUID的入站处理加载数据，并且这些ID包括在我们系统中不再处于活动状态的用户，则这些不活动的 [!DNL Audience Manager] UUID将不会到达并 [!UICONTROL User Profile Store] 不报告。
* [!UICONTROL Total Trait Realizations] 仅计 [!UICONTROL Rule-based Traits] 算。

## 特征的常规报告结果 {#general-report-results-traits}

运行“常规”报表并选择报告类型时，可 **[!UICONTROL Trait]** 以使用以下指标：

**独特的特质实现**

此量度表示限定了选定时间范围中 [特征的唯一Audience Manager唯一用户ID(UUID)](../reference/ids-in-aam.md) 。 例如，如果用户在10月1日三次访问您的主页，您将看到一个唯一特征实现。

**总特征实现**

此度量表示所选时间范围内特征所触发的特征总数。 例如，如果用户访问了您的主页，然后导航到您的技术新闻和体育新闻部分，则它们将作为三个总特征实现和一个唯一特征实现显示在“一般报告”中。

**总特征人口**

此量度表示当前为该特征限定的Audience Manager UUID的总量。 使用此编号可了解可用于细分和定位的用户总数。 通常，用户在120天内都会保留某个特 [征的一部分](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)。 例如，今天三次访问您的主页，之后再也不回来的用户，将每天一直作为该用户，直到现在120天。 在120天大关时，他们将被从人口中移走。 阅读我们 [的特征资格参考](../features/traits/trait-qualification-reference.md) ，了解有关唯一特征实现和总特征群体之间差异的更多示例。

下图显示了为“特征”报告类型运行常规报告的结果。

![](assets/general_reports_metrics.png)

## 常规报告区段的结果 {#general-report-results-segments}

运行“常规”报表并选择报告类型时，可 **[!UICONTROL Segment]** 以使用以下指标：

**实时细分群体**

此指标表示在指定时间范围内实时查看的唯一访客的实际数量，以及在Audience manager看到这些访客时符合区段条件的访客数。

**区段总人数**

此量度表示在您选择的回顾期内限定区段的Audience Manager UUID总数。 您的1天总细分人口代表您最准确的定位用户群。

>[!NOTE]
>
>选择 **[!UICONTROL Include Destination Mappings]** 以查看已激活目标的细分区段人口。

下图显示了为区段报告类型运行常规报告的结果。

![](assets/general_reports_segment_metrics.png)

## 目标的常规报告结果 {#general-report-results-destinations}

运行“常规”报表并选择报告类型时，可 **[!UICONTROL Destination]** 以使用以下指标：

**实时细分群体**

此指标表示在指定时间范围内实时查看的唯一访客的实际数量，以及在Audience manager看到这些访客时符合区段条件的访客数。

**区段总人数**

此量度表示回顾期间内发送到目标的属于区段的Audience Manager UUID总数。

下图显示了为“目标”报告类型运行常规报告的结果。

![](assets/general_reports_destinations.png)
