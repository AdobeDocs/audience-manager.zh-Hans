---
description: 概述了用于某些报告的采样方法、采样错误速率以及基于采样数据返回信息的报告列表。
seo-description: 概述了用于某些报告的采样方法、采样错误速率以及基于采样数据返回信息的报告列表。
seo-title: 选定Audience Manager报告中的数据采样和错误速率
solution: Audience Manager
title: 选定Audience Manager报告中的数据采样和错误速率
uuid: 3d8bd764-a9 da-40f1-8794-54304457bb9 a
translation-type: tm+mt
source-git-commit: d96182b0741dd31cc5ec0ffb68182ed5f8445c03

---


# Data Sampling and Error Rates in Selected Audience Manager Reports{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

概述了用于某些报告的采样方法、采样错误速率以及基于采样数据返回信息的报告列表。

## Data Sampling Ratio and Minimum Requirements {#data-sampling-ratio}

Some [!DNL Audience Manager] reports display results based on a sampled set of the total amount of available data. 采样数据率为1：54。对于使用采样数据的报表，这意味着您的结果基于每组54记录中的个记录。

这些报表使用采样数据，因为他们需要大量的计算能力来生成结果。采样有助于在降低计算需求、保持系统性能和提供准确结果之间取得平衡。

如果不满足最低独特访客要求，使用取样的报表会排除特征和区段。这些最低要求如下所示：

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-qualification-reference.md#unique-trait-realizations) over a 14-day period.
* 区段：超过14，000个实时用户。

## Error Rates {#error-rates}

生成重叠数据的报告中可能出现错误。错误定义为以下记录的百分比：

* 不应包含在报表中，但已添加。
* 应已包含在报表中，但被遗漏。

It's important to note that our tests and models show that the error rate *decreases* in an inverse proportion to the number of records in your data set. 具有大量记录的数据集生成的错误数比少量记录少。让我们以更定量的方式看待此断言。如下表所示，对于设置数量的记录，95%的报告结果将低于特定的错误速率。

| 记录数 | 错误率 |
|--- |--- |
| 500 - 1,000 | 95%的用户按42%的错误费率进行操作。 |
| 1,000 - 1,500 | 95%的错误速率低于34%。 |
| 10,000 - 50,000 | 95%的错误速率低于14%。 |
| 50,000 | 95%的错误速率低于6%。 |
| 100,000 | 95%的错误速率低于4%。 |
| 500,000(或更多) | 95%的错误速率低于2%。 |

## Reports That Use Sampled Data {#reports-using-sampled-data}

The [!DNL Audience Manager] reports that use sampled data include:

* [重叠报告](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (特性到特征、细分到特征和区段到区段)。
* [可寻址受众](../features/addressable-audiences.md) 数据(客户和细分级别数据)。
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
