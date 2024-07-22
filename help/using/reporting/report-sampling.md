---
description: 用于某些报表的取样方法摘要、取样错误率以及返回基于取样数据的信息的报表列表。
seo-description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-title: Data Sampling and Error Rates in Selected Audience Manager Reports
solution: Audience Manager
title: 选定Audience Manager报表中的数据取样率和错误率
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: Reporting Reference
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# 选定Audience Manager报表中的数据取样率和错误率{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

用于某些报表的取样方法摘要、取样错误率以及返回基于取样数据的信息的报表列表。

## 数据采样比率 {#data-sampling-ratio}

某些[!DNL Audience Manager]报告根据可用数据总量的采样集显示结果。 采样数据比率为1:54。 对于使用采样数据的报表，这意味着您的结果基于每组54条记录中的1条记录。

这些报告使用统计采样数据，因为它们需要大量计算能力才能生成结果。 取样有助于在减少的计算需求、保持系统性能以及提供准确的结果之间取得平衡。

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## 错误率 {#error-rates}

生成重叠数据的报表中可能会发生错误。 错误被定义为满足以下条件的记录的百分比：

* 报表中不应包含该变量，但无论如何仍将其添加。
* 应该列入报告，但被排除在外。

请注意，我们的测试和模型显示错误率&#x200B;*降低*&#x200B;与数据集中的记录数成反比。 与记录数较少的集相比，记录数较多的数据集生成的错误较少。 让我们以更具体的方式来看一下这一断言。 如下表所示，对于一组记录而言，95%的报告结果将低于特定错误率。

| 记录数 | 错误率 |
|--- |--- |
| 500 - 1,000 | 95%的错误率低于42%。 |
| 1,000 - 1,500 | 95%的错误率低于34%。 |
| 10,000 - 50,000 | 95%的错误率低于14%。 |
| 50,000 | 95%的错误率低于6%。 |
| 100,000 | 95%的错误率低于4%。 |
| 500,000（或更多） | 95%的错误率低于2%。 |

## 使用Minhash采样方法 {#minhash}

基于[Minhash](https://en.wikipedia.org/wiki/MinHash)采样方法，Audience Manager在One Permentation Hashing数据草图的基础上使用一种新的方法计算特征和区段估计值。 与标准估计方法相比，该方法对Jaccard相似性的估计方差更小。 请参阅以下部分，了解使用这种方法的报告。

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## 使用采样数据的报表 {#reports-using-sampled-data}

使用统计采样数据和Minhash采样方法的[!DNL Audience Manager]报表包括：

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| 统计取样 | Minhash采样方法 |
|--- |--- |
| [可寻址受众](../features/addressable-audiences.md)数据（客户和区段级别的数据）。 | [重叠报表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)（特征到特征、区段到特征和区段到区段） |
| [!UICONTROL Profile Merge Rule]的[总设备](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics)指标。 | [特征推荐](/help/using/features/segments/trait-recommendations.md) |
| [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md)在[!UICONTROL Search]选项卡和任何[!UICONTROL Saved Searches]中使用采样数据 | [Audience MarketplaceRecommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
