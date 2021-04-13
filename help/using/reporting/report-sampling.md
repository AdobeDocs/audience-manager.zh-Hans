---
description: 一些报告使用的抽样方法的摘要、抽样误差率以及基于抽样数据返回信息的报告列表。
seo-description: 一些报告使用的抽样方法的摘要、抽样误差率以及基于抽样数据返回信息的报告列表。
seo-title: 选定 Audience Manager 报表中的数据取样率和错误率
solution: Audience Manager
title: 选定 Audience Manager 报表中的数据取样率和错误率
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: 报告参考
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 7%

---

# 选定 Audience Manager 报表中的数据取样率和错误率{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

一些报告使用的抽样方法的摘要、抽样误差率以及基于抽样数据返回信息的报告列表。

## 数据采样率{#data-sampling-ratio}

某些[!DNL Audience Manager]报告根据可用数据总量的样本集显示结果。 采样数据比为1:54。 对于使用采样数据的报表，这意味着您的结果基于每54条记录中的1条记录。

这些报告使用统计抽样数据，因为需要大量计算能力才能生成结果。 采样有助于在减少的计算需求、保持系统性能和提供准确结果之间取得平衡。

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## 错误率{#error-rates}

生成重叠数据的报表中可能会出现错误。 错误定义为记录的百分比：

* 不应该包含在报告中，但无论如何都添加了。
* 本应被列入报告，但被排除在外。

请务必注意，我们的测试和模型显示错误率&#x200B;*以与数据集中记录数成反比的比例减少*。 具有大量记录的数据集生成的错误少于具有少量记录的数据集。 让我们以更定量的方式来看待这一论断。 如下表所示，对于一组记录，95%的报告结果将低于特定错误率。

| 记录数 | 错误率 |
|--- |--- |
| 500 - 1,000 | 95%的错误率低于42%。 |
| 1,000 - 1,500 | 95%的错误率低于34%。 |
| 1~5万 | 95%的错误率低于14%。 |
| 50,000 | 95%的错误率低于6%。 |
| 10万 | 95%的错误率低于4%。 |
| 500,000（或更多） | 95%的错误率低于2%。 |

## 使用Minhash采样方法{#minhash}

基于[Minhash](https://en.wikipedia.org/wiki/MinHash)采样方法，Audience Manager使用一种新方法在一个置换散列数据草图上计算特征和段估计。 该方法比标准Jaccard相似度估计器产生的方差要小。 有关使用此方法的报告，请参阅下面的部分。

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## 使用采样数据{#reports-using-sampled-data}的报表

[!DNL Audience Manager]使用统计采样数据和Minhash采样方法的报告包括：

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| 统计抽样 | Minhash采样方法 |
|--- |--- |
| [可寻](../features/addressable-audiences.md) 址受众数据（客户和细分数据）。 | [重叠报表](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) （特征到特征、区段到特征和区段到区段） |
| [[!UICONTROL Profile Merge Rule]的“设备总数](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics)”量度。 | [特征推荐](/help/using/features/segments/trait-recommendations.md) |
| [数据开](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) 发者在选项卡和任 [!UICONTROL Search] 何  [!UICONTROL Saved Searches] | [Audience Marketplace Recommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
