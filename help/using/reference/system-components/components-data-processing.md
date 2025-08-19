---
description: 数据处理组件包括Hadoop、Snowflake、SOLR和Tableau。
seo-description: Data processing components include Hadoop, Snowflake, SOLR, and Tableau.
seo-title: Data Processing Components
solution: Audience Manager
title: 数据处理组件
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: System Components
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 1%

---

# 数据处理组件{#data-processing-components}

数据处理组件包括Hadoop、Snowflake、SOLR和Tableau。

<!-- 

c_comproc.xml

 -->

Audience Manager使用以下组件来处理数据：

## Hadoop {#hadoop}

在[!DNL Audience Manager]中，Hadoop是包含[!DNL Audience Manager]所知道的关于用户的所有内容的主数据库。 例如，当[配置文件缓存服务器](../../reference/system-components/components-data-collection.md)创建包含用户数据的日志文件时，它会将该数据发送到Hadoop进行存储。 其他重要的Hadoop元素包括：

* **配置单元：** Hadoop的数据仓库。 Hive管理对Hadoop中存储的数据的临时查询。

* **HBase：**&#x200B;非常大的Hadoop数据库。 它处理和管理入站和出站数据、特征规则、算法建模信息，并执行许多与将数据存储和移动到不同系统相关的其他功能。

客户无法直接访问这些系统。 但是，客户确实会间接使用这些组件，因为这些组件存储有关其网站访客的重要数据。

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/)是一个大型云数据库。 它向许多面板图形及其相关文本框提供数据，这些文本框显示图形中每个项目的%变化。 如果您使用[!DNL Audience Manager]并查看仪表板报告，则表示您正在与[!UICONTROL Snowflake]提供的数据进行交互。



![](assets/dashboardreport.png)

这绝不是全面的列表，但[!UICONTROL Snowflake]负责的一些常见信息板报告包括：

* [每日特征变化报表](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* 所有重叠报表（有关每个重叠报表的信息，请参阅[交互式报表](/help/using/reporting/dynamic-reports/dynamic-reports.md)部分）。
* [未使用的信号报表](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR是来自Apache的开源数据库和服务器系统。 它提供了针对我们大型数据集的强大而快速的搜索功能。 作为[!DNL Audience Manager]客户，您可以在生成区段时看到SOLR正在起作用。 它向[!UICONTROL Estimated Historic Segment Size]报表提供数据。 由于其速度，SOLR非常适合于此角色。 例如，在您构建规则并向区段添加新特征时，SOLR能够更新历史大小数据。



![](assets/audsize.png)

## 表格 {#tableau}

[!DNL Audience Manager]使用[Tableau](https://www.tableausoftware.com/)显示[交互式报表](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)和[Audience Optimization报表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)中的数据。 交互式报表显示特征和区段的性能和重叠数据。 它们不使用按列和行排列的数字，而是使用不同的形状、颜色和大小返回数据。 此外，您可以选择单个数据点或数据点组，并深入查看报告结果以了解更多详细信息。 这些可视化技术和报表交互性有助于使大量数字数据更易于理解。



![](assets/advertiser_analytics.png)
