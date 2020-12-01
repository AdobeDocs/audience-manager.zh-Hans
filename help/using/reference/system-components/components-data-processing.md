---
description: 数据处理组件包括Hadoop、Snowflake、SOLR和Tableau。
seo-description: 数据处理组件包括Hadoop、Snowflake、SOLR和Tableau。
seo-title: 数据处理组件
solution: Audience Manager
title: 数据处理组件
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 3%

---


# 数据处理组件{#data-processing-components}

数据处理组件包括Hadoop、Snowflake、SOLR和Tableau。

<!-- 

c_comproc.xml

 -->

Audience Manager使用以下组件处理数据：

## Hadoop{#hadoop}

在[!DNL Audience Manager]中，Hadoop是包含[!DNL Audience Manager]所知用户信息的主数据库。 例如，当[用户档案缓存服务器](../../reference/system-components/components-data-collection.md)创建包含用户相关数据的日志文件时，会将该数据发送到Hadoop以进行存储。 hadoop其他重要因素包括：

* **蜂巢：** Hadoop的data warehouse。Hive管理存储在Hadoop的数据的临时查询。

* **HBase：一** 个非常大的Hadoop数据库。它处理和管理入站和出站数据、特征规则、算法建模信息，并执行与存储数据和将数据移动到不同系统相关的许多其他功能。

客户无法直接访问这些系统。 但是，客户确实会间接与他们合作，因为这些组件存储有关其网站访客的重要数据。

## Snowflake{#snowflake}

[Snowflake](https://www.snowflake.net/) 是一个庞大的云数据库。它向许多仪表板图形及其相关文本框提供数据，这些文本框显示图形中每个项的%更改。 如果使用[!DNL Audience Manager]并查看仪表板报告，则您正在与[!UICONTROL Snowflake]提供的数据交互。



![](assets/dashboardreport.png)

这绝不是全面的列表，但是一些[!UICONTROL Snowflake]负责的常见仪表板报告包括：

* [每日特征变化报表](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* 所有重叠报告（有关每个重叠报告的信息，请参见[交互式报告](/help/using/reporting/dynamic-reports/dynamic-reports.md)部分）。
* [未使用的信号报表](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR是Apache提供的开放源数据库和服务器系统。 它为我们的大型数据集提供强大而快速的搜索功能。 作为[!DNL Audience Manager]客户，您可以在构建区段时看到SOLR的实际操作。 它向[!UICONTROL Estimated Historic Segment Size]报告提供数据。 SOLR因其速度而成为这一角色的理想之选。 例如，在您构建规则并向区段添加新特征时，SOLR能够更新历史大小数据。



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] 使用 [](https://www.tableausoftware.com/) 交互式报表和Audience Optimization报 [表](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) 中的自动 [显示数据](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。交互式报表显示特征和区段的性能和重叠数据。 它们不使用排列在列和行中的数字，而是使用不同的形状、颜色和大小返回数据。 此外，您还可以选择单个或一组数据点，并深入到报表结果以了解更多详细信息。 这些可视化技术和报表交互性有助于使大量数字数据更易于理解。



![](assets/advertiser_analytics.png)

