---
description: 对用于某些报告的采样方法、采样错误率和基于采样数据返回信息的报告列表的摘要。
seo-description: 对用于某些报告的采样方法、采样错误率和基于采样数据返回信息的报告列表的摘要。
seo-title: 选定 Audience Manager 报表中的数据取样率和错误率
solution: Audience Manager
title: 选定 Audience Manager 报表中的数据取样率和错误率
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 8%

---


# 选定 Audience Manager 报表中的数据取样率和错误率{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

对用于某些报告的采样方法、采样错误率和基于采样数据返回信息的报告列表的摘要。

## 数据采样率和最低要求 {#data-sampling-ratio}

某 [!DNL Audience Manager] 些报告根据可用数据总量的抽样集显示结果。 采样数据率为1:54。 对于使用采样数据的报表，这意味着您的结果基于每54条记录中的1条记录。

这些报表使用采样数据，因为它们需要大量计算能力才能生成结果。 采样有助于在减少的计算需求、保持系统性能和提供准确结果之间取得平衡。

使用采样的报表在不满足最低唯一访客要求时排除特征和区段。 这些最低要求如下：

* 特征： 在14天 [内实现](/help/using/features/traits/trait-and-segment-qualification-reference.md#unique-trait-realizations) 28,000个独特特性。
* 细分： 在14天内有70,000个实时用户。

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

## 使用采样数据的报告 {#reports-using-sampled-data}

使用 [!DNL Audience Manager] 采样数据的报告包括：

* [重叠报告](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) （特征到特征、区段到特征和区段到区段）。
* [可寻址受众](../features/addressable-audiences.md) （客户级和细分级数据）。
* 的 [设备总](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) 数指标 [!UICONTROL Profile Merge Rule]。
* [数据浏览器](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) (Data Explorer)使用选项卡中 [!UICONTROL Search] 的采样数据以及任何 [!UICONTROL Saved Searches]。