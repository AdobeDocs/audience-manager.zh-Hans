---
description: 对用于某些报告的采样方法、采样错误率和基于采样数据返回信息的报告列表的摘要。
seo-description: 对用于某些报告的采样方法、采样错误率和基于采样数据返回信息的报告列表的摘要。
seo-title: 选定 Audience Manager 报表中的数据取样率和错误率
solution: Audience Manager
title: 选定 Audience Manager 报表中的数据取样率和错误率
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: reporting reference
translation-type: tm+mt
source-git-commit: 397be3f44bf865633140bb45630a78be0a0d2219
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 7%

---


# 选定 Audience Manager 报表中的数据取样率和错误率{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

对用于某些报告的采样方法、采样错误率和基于采样数据返回信息的报告列表的摘要。

## 数据采样率 {#data-sampling-ratio}

某 [!DNL Audience Manager] 些报告根据可用数据总量的抽样集显示结果。 采样数据率为1:54。 对于使用采样数据的报表，这意味着您的结果基于每54条记录中的1条记录。

这些报告使用统计抽样数据，因为它们需要大量计算能力才能生成结果。 采样有助于在减少的计算需求、保持系统性能和提供准确结果之间取得平衡。

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

生成重叠数据的报表中可能出现错误。 错误定义为记录的百分比：

* 本不应包含在报告中，但仍应添加。
* 本应被列入报告，但被遗漏了。

必须注意的是，我们的测试和模型显示错误率 *与* 数据集中记录数成反比减少。 具有大量记录的数据集生成的错误比具有少量记录的数据集少。 让我们用更定量的方式来看看这一论断。 如下表所示，对于一组记录，95%的报告结果将低于特定错误率。

| 记录数 | 错误率 |
|--- |--- |
| 500 - 1,000 | 95%的错误率低于42%。 |
| 1,000 - 1,500 | 95%的错误率低于34%。 |
| 10,000 - 50,000 | 95%的错误率低于14%。 |
| 50,000 | 95%的错误率低于6%。 |
| 100,000 | 95%的错误率低于4%。 |
| 500,000（或更多） | 95%的错误率低于2%。 |

## 使用Minhash采样方法 {#minhash}

基于Minhash [采样方法](https://en.wikipedia.org/wiki/MinHash) ,Audience Manager在单置换散列数据草图上，采用一种新的方法计算特征和分段估计。 该方法比标准Jaccard相似度估计器产生的方差要小。 有关使用此方法的报告，请参阅以下部分。

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## 使用采样数据的报告 {#reports-using-sampled-data}

使用 [!DNL Audience Manager] 统计采样数据和Minhash采样方法的报告包括：

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| 统计抽样 | Minhash采样方法 |
|--- |--- |
| [可寻址受众](../features/addressable-audiences.md) （客户级和细分级数据）。 | [重叠报告](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) （特征到特征、区段到特征和区段到区段） |
| 的 [设备总](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) 数指标 [!UICONTROL Profile Merge Rule]。 | [特征推荐](/help/using/features/segments/trait-recommendations.md) |
| [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) 使用选项卡中的 [!UICONTROL Search] 采样数据以及 [!UICONTROL Saved Searches] | [Audience MarketplaceRecommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
