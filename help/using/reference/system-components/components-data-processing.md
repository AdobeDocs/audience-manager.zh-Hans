---
description: 数据处理组件包括Hadoop、Snowflake、SOLR和Tableau。
seo-description: 数据处理组件包括Hadoop、Snowflake、SOLR和Tableau。
seo-title: 数据处理组件
solution: Audience Manager
title: 数据处理组件
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: 系统组件
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 4%

---

# 数据处理组件{#data-processing-components}

数据处理组件包括Hadoop、Snowflake、SOLR和Tableau。

<!-- 

c_comproc.xml

 -->

Audience Manager使用以下组件处理数据：

## Hadoop{#hadoop}

在[!DNL Audience Manager]中，Hadoop是主数据库，其中包含[!DNL Audience Manager]对用户所知的一切。 例如，当[用户档案缓存服务器](../../reference/system-components/components-data-collection.md)创建包含有关用户数据的日志文件时，会将该数据发送到Hadoop以进行存储。 其他重要的Hadoop元素包括：

* **配置单** 元：data warehouseHadoop。Hive管理对存储在Hadoop中的查询的临时。

* **HBase：一** 个非常大的Hadoop数据库。它处理和管理入站和出站数据、特征规则、算法建模信息，并执行与存储数据和将数据移动到不同系统相关的许多其它功能。

客户无法直接访问这些系统。 但是，客户确实会与他们间接合作，因为这些组件存储有关其网站访客的重要数据。

## Snowflake{#snowflake}

[Snowflake是](https://www.snowflake.net/) 一个海量的云数据库。它向许多仪表板图形及其相关文本框提供数据，这些文本框显示图形中每个项目的%更改。 如果使用[!DNL Audience Manager]并查看仪表板报告，则您与由[!UICONTROL Snowflake]提供的数据进行交互。



![](assets/dashboardreport.png)

这并不是一个全面的列表，而是[!UICONTROL Snowflake]负责的一些常见仪表板报告包括：

* [每日特征变化报表](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* 所有重叠报告（有关每个重叠报告的信息，请参见[交互式报告](/help/using/reporting/dynamic-reports/dynamic-reports.md)部分）。
* [未使用的信号报表](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR是Apache的开源数据库和服务器系统。 它为我们的大型数据集提供了强大、快速的搜索功能。 作为[!DNL Audience Manager]客户，您可以在构建区段时看到SOLR的实际操作情况。 它向[!UICONTROL Estimated Historic Segment Size]报表提供数据。 SOLR由于其速度，是该角色的理想之选。 例如，在您构建规则和向区段添加新特征时，SOLR能够更新历史大小数据。



![](assets/audsize.png)

## 表{#tableau}

[!DNL Audience Manager] 使 [](https://www.tableausoftware.com/) 用交互式报表和Audience Optimization [报](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) 表中的自 [动显示数据](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。交互式报表显示特征和区段的性能和重叠数据。 它们不使用排列在列和行中的数字，而是使用不同的形状、颜色和大小返回数据。 此外，您还可以选择单个或一组数据点，并深入到报表结果以了解更多详细信息。 这些可视化技术和报表交互性有助于使大量数字数据更易于理解。



![](assets/advertiser_analytics.png)
