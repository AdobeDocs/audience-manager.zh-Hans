---
description: 数据处理组件包括Hadoop、Snowflake、SOLR和表格。
seo-description: 数据处理组件包括Hadoop、Snowflake、SOLR和表格。
seo-title: 数据处理组件
solution: Audience Manager
title: 数据处理组件
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: 系统组件
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 4%

---

# 数据处理组件{#data-processing-components}

数据处理组件包括Hadoop、Snowflake、SOLR和表格。

<!-- 

c_comproc.xml

 -->

Audience Manager使用以下组件处理数据：

## Hadoop {#hadoop}

在[!DNL Audience Manager]中，Hadoop是主数据库，其中包含[!DNL Audience Manager]对用户所知的一切。 例如，当[配置文件缓存服务器](../../reference/system-components/components-data-collection.md)创建包含用户相关数据的日志文件时，它会将该数据发送到Hadoop以进行存储。 其他重要的Hadoop元素包括：

* **配置单元：** data warehouseHadoop。配置单元管理对存储在Hadoop中的数据的临时查询。

* **HBase:** 一个非常大的Hadoop数据库。它处理和管理入站和出站数据、特征规则、算法建模信息，并执行与将数据存储和移动到不同系统相关的许多其他功能。

客户无法直接访问这些系统。 但是，客户确实会间接与他们合作，因为这些组件存储了有关其网站访客的重要数据。

## Snowflake {#snowflake}

[](https://www.snowflake.net/) Snowflake是一个庞大的云数据库。它向许多功能板图形及其相关文本框提供数据，这些文本框显示图表中每个项目的更改百分比。 如果您使用[!DNL Audience Manager]并查看功能板报表，则表示您正在与[!UICONTROL Snowflake]提供的数据交互。



![](assets/dashboardreport.png)

这绝不是一个完整的列表，但是，一些由[!UICONTROL Snowflake]负责的常见功能板报表包括：

* [每日特征变化报表](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* 所有重叠报表（有关每个重叠报表的信息，请参阅[交互式报表](/help/using/reporting/dynamic-reports/dynamic-reports.md)部分）。
* [未使用的信号报表](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR是Apache提供的开源数据库和服务器系统。 它提供了强大而快速的搜索功能，覆盖我们的大型数据集。 作为[!DNL Audience Manager]客户，您可以在构建区段时看到SOLR的运行情况。 它会向[!UICONTROL Estimated Historic Segment Size]报表提供数据。 SOLR由于其速度而非常适合此角色。 例如，在您构建规则并向区段添加新特征时，SOLR能够更新历史大小数据。



![](assets/audsize.png)

## 塔布洛 {#tableau}

[!DNL Audience Manager] 使用 [](https://www.tableausoftware.com/) 交互式报表和 [Audience Optimization](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) 报表 [中的](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。交互式报表可显示特征和区段的性能和重叠数据。 它们不使用列和行中排列的数字，而是使用不同的形状、颜色和大小返回数据。 此外，您还可以选择单个或一组数据点，并深入查看报表结果，以获取更多详细信息。 这些可视化技术和报表交互性有助于使大量数字数据更易于理解。



![](assets/advertiser_analytics.png)
