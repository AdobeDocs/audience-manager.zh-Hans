---
description: 回填特征实现以捕获历史受众并避免在特征创建日期之前丢失相关数据。
seo-description: 回填特征实现以捕获历史受众并避免在特征创建日期之前丢失相关数据。
seo-title: 回填特征实现
title: 回填特征实现
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---


# 回填特征实现 {#backfill-trait-realizations}

回填特征实现以捕获历史受众并避免在特征创建日期之前丢失相关数据。

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] 是一种高级功能，可通过解锁其他用例来增强Audience Manager体验。 回填需要额外的处理能力，并且所有Audience Manager客户都能以递增的成本获得回填。 有关更多详细信息，请与Adobe销售代表联系。

从未使用的信号创建特征时，您可以选择在特定时间段内回填特征实现。 [!DNL Audience Manager] 捕获有关符合新特征的受众的历史数据，并将其存储在相应的用户档案中。 您可以在特 **[!UICONTROL Backfill Options]** 征生 [!UICONTROL Trait Expression] 成器的一 **[节中看到](../../features/traits/about-trait-builder.md)**。

>[!NOTE]
>
>您可以回填基于规则和已载入特征的特征实现。

下面是如何回填特质实现：

1. 转至 [!UICONTROL Audience Data > Signals > Search] amd运行“信号搜索”或使 [用“信号](../../features/data-explorer/data-explorer-signals-dashboard.md) ”仪表板来识别要用于新特征的信号。
1. 根据所需信号创建新特征。
1. 使用 **[!UICONTROL Backfill Options]** 部分 **[!UICONTROL Trait Expression]** 中的选择要回填特征实现的时间间隔。 预定义的回填间隔包括1、7、14和30天。 您还可以选择最多30天的自定义日期范围。

   ![特征回填](assets/signals-trait-backfill.png)

1. （可选）单 **[!UICONTROL Estimate Realizations]** 击该 **[!UICONTROL Estimated Trait Realizations]** 部分以查看最近7 [!UICONTROL Unique Trait Realizations] 天内 [!UICONTROL Total Trait Population] 已回填特征的估计值和值。

   ![估计特征实现](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >对于使用以下运算符的表达式的特征，特征回填和估计不可用：
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 创建特征。

创建完特征后，您将看到它的已回填实现包含在实现统计中。

观看以下视频，了解如何回填特征的视频演练。

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## 特征回填延迟 {#trait-backfilling-latency}

新创建的特征开始在创建后2到3小时捕获受众。 但是，由于每天执行的数据量 [!DNL Audience Manager] 很大，回填的人口不会立即反映在和图 [!UICONTROL Unique Trait Realizations] 形中 [!UICONTROL Total Trait Population] 。

Audience Manager在特 [!UICONTROL Trait Graph] 征创建后的48小时内用已回填的人群更新。

## 特征回填限制 {#trait-backfilling-limit}

[!UICONTROL Data Explorer] 允许您每月回填最多50个特征，每月的1天会重置回填计数器。

>[!NOTE]
>
>特征回填配额不会结转前几个月。 例如，如果本月回填30个特征，则下个月的特征回填配额将重置为50而不是70。

## 对报告的影响 {#reporting-impact}

回填的特征实现反映在 [!UICONTROL Unique Trait Realizations] 和度 [!UICONTROL Total Trait Population] 量中，因 [!DNL Audience Manager] 为将历史信号转换为特征实现。

但是，在特 [!UICONTROL Trait Graph]征创 [!UICONTROL General Reports]建日 [!UICONTROL Trend Reports] 期之前，历史指标会回溯地回填，不会更新、和。