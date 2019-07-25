---
description: 数据处理组件包括Hadoop、Snow Folke、SOLR和Tableau。
seo-description: 数据处理组件包括Hadoop、Snow Folke、SOLR和Tableau。
seo-title: 数据处理组件
solution: Audience Manager
title: 数据处理组件
uuid: d458d869-7a23-4016-871d-0b994cf4af06
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Processing Components{#data-processing-components}

数据处理组件包括Hadoop、Snow Folke、SOLR和Tableau。

<!-- 

c_comproc.xml

 -->

Audience Manager使用以下组件处理数据：

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop is the master database that contains everything [!DNL Audience Manager] knows about a user. For example, when the [Profile Cache Servers](../../reference/system-components/components-data-collection.md) create log files that contain data about your users, it sends that data to Hadoop for storage. 其他重要的Hadoop元素包括：

* **Have：** Hadoop的数据仓库。Have管理对Hadoop中存储的数据的专门查询。

* **HBase：** 非常大的Hadoop数据库。它处理和管理入站和出站数据、特征规则、算法建模信息，并执行与将数据存储和移动到不同系统相关的许多其他函数。

客户无权直接访问这些系统。但是，客户可以间接地与这些组件一起使用，因为这些组件存储了关于站点访客的重要数据。

## Snowflake {#snowflake}

[Snorflash](https://www.snowflake.net/) 是一个庞大的云数据库。它提供了许多仪表板图表及其相关文本框的数据，它们会显示图中每个项目的变化百分比。If you use [!DNL Audience Manager] and look at the dashboard reports, you're interacting with data provided by [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

This is by no means a comprehensive list, but some common dashboard reports that [!UICONTROL Snowflake] is responsible for include:

* [每日特征变化报告](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* [交付和性能报告](/help/using/reporting/dynamic-reports/delivery-performance-report.md)
* All the overlap reports (see the [Interactive Reports](/help/using/reporting/dynamic-reports/dynamic-reports.md) section for information about each overlap report).
* [未使用的信号报告](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR是Apache中的开放源代码数据库和服务器系统。它通过我们的大型数据集提供强大而快速的搜索功能。As an [!DNL Audience Manager] customer, you can see SOLR in action when you build segments. It provides data to the [!UICONTROL Estimated Historic Segment Size] report. SOLR是这一角色的理想之选。例如，SOLR能够在您构建规则并为区段添加新特征时更新历史大小数据。



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] 使用 [Tableau](https://www.tableausoftware.com/) 在 [交互式报告](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) 和 [受众优化报告中显示数据](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。交互式报告显示特征和区段的性能和重叠数据。它们使用不同的形状、颜色和大小返回数据，而不是使用列在列和行中的数字。此外，您还可以选择一个或多组数据点，然后深入报告结果以了解更多详细信息。这些可视化技术和报告交互性有助于使大量数字数据更易于理解。



![](assets/advertiser_analytics.png)

