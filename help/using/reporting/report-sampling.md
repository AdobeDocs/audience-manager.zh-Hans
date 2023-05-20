---
description: 用於某些報表的取樣方法摘要、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。
seo-description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-title: Data Sampling and Error Rates in Selected Audience Manager Reports
solution: Audience Manager
title: 选定 Audience Manager 报表中的数据取样率和错误率
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: Reporting Reference
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 6%

---

# 选定 Audience Manager 报表中的数据取样率和错误率{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

用於某些報表的取樣方法摘要、取樣錯誤率，以及根據取樣資料傳回資訊的報表清單。

## 数据采样比率 {#data-sampling-ratio}

某些 [!DNL Audience Manager] 报表会根据可用数据总量的样本集来显示结果。 采样的数据比率为1:54。 对于使用抽样数据的报表，这意味着您的结果基于每组54记录中的1个记录。

这些报表使用的是统计样本数据，因为它们需要大量的计算能力才能生成结果。 采样有助于在减少计算请求、维护系统性能和提供准确结果之间达到平衡。

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

错误可能发生在生成重叠数据的报表中。 錯誤定義為記錄中符合以下條件的百分比：

* 不應納入報表中，但無論如何仍會新增。
* 應該包含在報表中，但被省略。

請注意，我們的測試和模型會顯示錯誤率，這點很重要 *減少* 與資料集中的記錄數成反比。 含有大量記錄的資料集所產生的錯誤會比含有少量記錄的資料集少。 讓我們以更定量的方式審視此判斷提示。 如下表所示，对于一组记录数而言，95% 的报表结果将低于特定的错误率。

| 记录数 | 错误率 |
|--- |--- |
| 500 - 1,000 | 95% 的错误率低于42%。 |
| 1,000 - 1,500 | 95% 的错误率低于34%。 |
| 10,000 - 50,000 | 95%的錯誤率低於14%。 |
| 50,000 | 95%的錯誤率低於6%。 |
| 100,000 | 95% 的错误率低于4%。 |
| 500000（或更多） | 95% 的错误率低于2%。 |

## 使用 Minhash 采样方法 {#minhash}

[根据 Minhash ](https://en.wikipedia.org/wiki/MinHash) 取样方法，Audience Manager 使用 novel 方法计算特征，并在一个排列哈希数据草图上区段 estimators。此新方法产生的变量低于 Jaccard 相似性的标准估算器。 请参阅下面的部分以了解使用此方法的报表。

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## 使用取樣資料的報表 {#reports-using-sampled-data}

此 [!DNL Audience Manager] 使用統計抽樣資料和Minhash抽樣方法的報表包括：

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| 統計抽樣 | Minhash取樣方法 |
|--- |--- |
| [可寻址受众 ](../features/addressable-audiences.md) 数据（客户和区段级别的数据）。 | [重叠报表 ](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) （特征与特征、区段到特征和区段到区段） |
| [量度 [!UICONTROL Profile Merge Rule] 的设备 ](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) 总数。 | [特征推荐](/help/using/features/segments/trait-recommendations.md) |
| [数据浏览器 ](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) 使用选项卡中的 [!UICONTROL Search] 样本数据和任何 [!UICONTROL Saved Searches] | [Audience Marketplace Recommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
