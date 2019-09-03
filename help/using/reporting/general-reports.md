---
description: “常规”报告返回特征、区段和目标的性能数据。
seo-description: Audience Manager中的常规报告返回特征、细分和目标的绩效数据。
seo-title: Audience Manager中的一般报告
solution: Audience Manager
title: 一般报告
uuid: cea75a0-969e-4ee3-971a-60b91111e52
translation-type: tm+mt
source-git-commit: 1c626c770208150d209d93f666b581113ada8de9

---


# 一般报告{#general-reports}

[!UICONTROL General] 报告返回特征、区段和目标的绩效数据。

## 概述 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] uses [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])将用户组权限扩展到 [!UICONTROL General] 报告。用户只能查看报告中具有查看权限的特征和区段。[!UICONTROL RBAC] 功能允许您控制内部团队能够查看哪些报告数据。例如，管理不同广告商帐户的代理可以配置用户组权限，以使管理Advertiser A帐户的团队无法看到Advertiser B的报告数据。

在需要时运行 [!UICONTROL General] 报告：

* 按特征、细分或目标审查性能。
* 以1、7、14、30、60和90天的间隔跟踪印象(总数和唯一值)。
* 查看总计和唯一加载计数。
* 比较特征和细分性能。
* 确定强大或不良的性能特征和细分，分析需求，或将加载/触发数据与第三方报表进行比较。
* 导出数据(. csv格式)以进一步分析和共享。

下图提供 [!UICONTROL General] 了报表中关键元素的高级概述。

![](assets/general_reports.png)

1. 配置以下选项：

   * **报告类型：** 选择所需的报告类型(特征、区段或目标)。

   * **对于日期通过：** 指定报告的日期范围。

2. 按名称或ID搜索特征、区段或目标。
3. 从文件夹列表中，将您要报告的特征、区段或目标拖放到右侧的 [!UICONTROL Selections] 面板。
4. 生成要在可导出表格中显示的报表。

## Run a General Report {#run-general-report}

本节介绍如何运行 [!UICONTROL General] 报告以及设置时间和其他性能选项。

<!-- 

t_run_general_report.xml

 -->

1. 在 **[!UICONTROL Analytics]** 仪表板中，单击 **[!UICONTROL General Reports]**。
1. 从 **[!UICONTROL Report Type]** 下拉列表中，选择所需类型：特征、区段或目标。
1. *条件* 单击日期框以显示日历，然后如果要指定其他日期，则选择报告的结束日期。
1. 按名称或ID搜索特征、区段或目标。
1. 从文件夹列表中，将您要报告的特征、区段或目标拖放到右侧的 [!UICONTROL Selections] 面板。
1. 单击 **[!UICONTROL Run Report]**.

   结果显示在可导出的表中。单击列标题可按升序或降序对结果进行排序。
1. 选择报表顶部的所需选项按钮，按性能( [!UICONTROL Unique Trait Realizations]、 [!UICONTROL Total Trait Realizations]或 [!UICONTROL Total Trait Population])或按时间(1、7、14、30、60或90天范围)过滤数据。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 仅供计算。[!UICONTROL Rule-based Traits]

1. *可选* 单击 **[!UICONTROL Export to CSV]**。这将导出 [!UICONTROL Unique Trait Realizations]和 [!UICONTROL Total Trait Realizations]导出 [!UICONTROL Total Trait Population] 整天的范围。

## 常规报告结果说明 {#general-reports-explained}

这些数字 [!UICONTROL General Reports] 由我们 [!UICONTROL User Profile Store]直接生成。结果反映生成这些报告号码时后端 [!DNL Audience Manager] 包含的用户数。

* 这些数字不包括流量过多的访客ID。在到达后端系统之前，筛选机器人中的流量。此外，在后台运行每周清理作业时，将丢弃一些机器人程序流量。
* 如果您通过在 [!DNL Audience Manager] UUID中通过入站处理启动数据，并且这些ID包括在我们的系统中不再处于活动状态的用户，则这些非活动 [!DNL Audience Manager] UI将永远不会到达 [!UICONTROL User Profile Store] 并且未报告。
* [!UICONTROL Total Trait Realizations] 仅供计算。[!UICONTROL Rule-based Traits]

## 一般报告特征的结果 {#general-report-results-traits}

运行常规报告并选择 **[!UICONTROL Trait]** 作为报告类型时，以下量度可用：

**独特特征真实性**

此量度代表在选定时间范围内符合特征的 [Audience Manager唯一用户ID(UUID)](../reference/ids-in-aam.md) 的唯一数量。例如，如果用户在10/1日访问了您的主页三次，您将看到一个唯一特征实现。

**特征真实性**

此量度表示在选定时间范围内特征激发的特征总数。例如，如果某个用户访问了您的主页，然后导航到您的技术新闻和您的体育新闻部分，它们将在“常规报告”中显示为三个特征实时真实性，以及一个独特的特征实现。

**特征总数**

此量度表示当前符合特征的Audience Manager UUID的总量。使用此数字可了解可用于细分和定位的用户总数。通常情况下，用户在特征的一部分保留 [120天](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)。例如，今天访问您的主页三次且永远不会返回的用户将一直作为该人口的一名用户，直到自现在起120天。在120天内，将从人群中删除这些标记。阅读我们 [的“特征资格参考”](../features/traits/trait-qualification-reference.md) ，了解有关独特特征真实性和特征总数之间差异的更多示例。

下图显示了为特征报告类型运行常规报告的结果。

![](assets/general_reports_metrics.png)

## 一般报告区段的结果 {#general-report-results-segments}

运行常规报告并选择 **[!UICONTROL Segment]** 作为报告类型时，以下量度可用：

**实时细分群体**

此量度表示特定访客在指定时间范围内实时查看的实际数量，以及Audience Manager查看时获得区段的实际数量。

**总细分人口**

此量度表示在选定的回顾期内符合区段资格的Audience Manager UUID的总数。您的天总细分人口是定位定位最准确的用户群。

>[!NOTE]
>
>选择 **[!UICONTROL Include Destination Mappings]** 以查看已激活目标的区段人群细分。

下图显示了运行区段报告类型的常规报告的结果。

![](assets/general_reports_segment_metrics.png)

## 一般报告目标结果 {#general-report-results-destinations}

运行常规报告并选择 **[!UICONTROL Destination]** 作为报告类型时，以下量度可用：

**实时细分群体**

此量度表示特定访客在指定时间范围内实时查看的实际数量，以及Audience Manager查看时获得区段的实际数量。

**总细分人口**

此量度表示属于返回期间内的区段的Audience Manager UI总数，该区段被发送到目标。

下图显示了运行目标报告类型的常规报告的结果。

![](assets/general_reports_destinations.png)
