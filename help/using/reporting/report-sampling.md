---
description: 用于某些报告的采样方法的摘要、采样错误率以及基于采样数据返回信息的报告列表。
seo-description: 用于某些报告的采样方法的摘要、采样错误率以及基于采样数据返回信息的报告列表。
seo-title: 选定Audience manager报告中的数据采样和错误率
solution: Audience Manager
title: 选定Audience manager报告中的数据采样和错误率
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
translation-type: tm+mt
source-git-commit: d96182b0741dd31cc5ec0ffb68182ed5f8445c03

---


# 选定Audience manager报告中的数据采样和错误率{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

用于某些报告的采样方法的摘要、采样错误率以及基于采样数据返回信息的报告列表。

## 数据采样率和最低要求 {#data-sampling-ratio}

某些 [!DNL Audience Manager] 报告根据可用数据总量的样本集显示结果。 采样数据比为1:54。 对于使用采样数据的报表，这意味着您的结果基于每54条记录中的1条记录。

这些报告使用采样数据，因为它们需要大量计算能力来生成结果。 采样有助于在减少的计算需求、保持系统性能和提供准确结果之间取得平衡。

使用采样的报表在不符合最低唯一访客要求时不包括特征和区段。 这些最低要求如下：

* 特征：在14天 [内实现](/help/using/features/traits/trait-qualification-reference.md#unique-trait-realizations) 28,000个独特特征。
* 区段：在14天内有70,000个实时用户。

## 错误率 {#error-rates}

在生成重叠数据的报告中可能会出现错误。 错误定义为以下记录的百分比：

* 不应包含在报告中，但无论如何都应添加。
* 本该写在报告里，但没有写。

必须注意的是，我们的测试和模型显示错误率 *与数据集中* 记录数成反比的下降。 具有大量记录的数据集生成的错误比具有少量记录的数据集少。 让我们从更定量的角度来看一下这一论断。 如下表所示，对于一组记录，95%的报告结果将低于特定错误率。

| 记录数 | 错误率 |
|--- |--- |
| 500 - 1,000 | 95%的错误率低于42%。 |
| 1,000 - 1,500 | 95%的错误率低于34%。 |
| 10,000 - 50,000 | 95%的错误率低于14%。 |
| 50,000 | 95%的错误率低于6%。 |
| 100,000 | 95%的错误率低于4%。 |
| 500,000（或更多） | 95%的错误率低于2%。 |

## 使用采样数据的报告 {#reports-using-sampled-data}

使用 [!DNL Audience Manager] 采样数据的报告包括：

* [重叠报告](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) （特征到特征、区段到特征和区段到区段）。
* [可寻址的受众数据](../features/addressable-audiences.md) （客户级和细分级数据）。
* 的 [设备总数](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics)[!UICONTROL Profile Merge Rule]。
