---
description: 回填特征实现以捕获历史受众并避免在特征创建日期之前丢失相关数据。
seo-description: 回填特征实现以捕获历史受众并避免在特征创建日期之前丢失相关数据。
seo-title: 回填特征实现
title: 回填特征实现
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# 回填特征实现 {#backfill-trait-realizations}

回填特征实现以捕获历史受众并避免在特征创建日期之前丢失相关数据。

[!UICONTROL Data Explorer Trait Backfill] 是一种高级功能，可通过解锁其他使用案例来增强Audience Manager体验。 回填需要额外的处理能力，并且所有Audience manager客户都能以递增的成本使用回填。 有关更多详细信息，请与Adobe销售代表联系。

从未使用的信号创建特征时，您可以选择在特定时间段内回填特征实现。 [!DNL Audience Manager] 捕获符合新特征的受众的历史数据并将其存储在相应的配置文件中。 您可以在特 **[!UICONTROL Backfill Options]** 征构建 [!UICONTROL Trait Expression] 器的部分 **[中看到](../../features/traits/about-trait-builder.md)**。

>[!NOTE]
>
>您可以回填基于规则和已载入特征的特征实现。

下面介绍如何回填特征实现：

1. 转至并 [!UICONTROL Audience Data > Signals > Search] 运行“信号搜索”或使用“信号 [控制板](../../features/data-explorer/data-explorer-signals-dashboard.md) ”来识别要用于新特征的信号。
1. 根据所需信号创建新特征。
1. 使用部 **[!UICONTROL Backfill Options]** 分中 **[!UICONTROL Trait Expression]** 的选项选择要回填特征实现的时间间隔。 预定义的回填间隔包括1、7、14和30天。 您还可以选择最多30天的自定义日期范围。

   ![特征回填](assets/signals-trait-backfill.png)

1. （可选）单 **[!UICONTROL Estimate Realizations]** 击该部 **[!UICONTROL Estimated Trait Realizations]** 分可查看最近7天内回填特 [!UICONTROL Unique Trait Realizations] 征 [!UICONTROL Total Trait Population] 的估计值和值。

   ![估计特征实现](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >特征回填和估计对于使用以下运算符的表达式的特征不可用：
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 创建特征。

创建完特征后，您将看到其回填的实现包含在实现统计信息中。

## 特征回填延迟 {#trait-backfilling-latency}

新创建的特征在创建后两到三小时内开始捕获受众。 但是，由于每天执行的数据量 [!DNL Audience Manager] 很大，回填的人口不会立即反映在和图 [!UICONTROL Unique Trait Realizations] 中 [!UICONTROL Total Trait Population] 。

Audience manager在特征创 [!UICONTROL Trait Graph] 建后的48小时内用回填人口进行更新。

## 特征回填限制 {#trait-backfilling-limit}

[!UICONTROL Data Explorer] 允许您每月回填最多50个特征，每月的1天将重置回填计数器。

>[!NOTE]
>
>特征回填配额不会结转前几个月。 例如，如果您在本月回填30个特征，则下个月的特征回填配额将重置为50而不是70。

## 对报告的影响 {#reporting-impact}

回填的特征实现反映在和 [!UICONTROL Unique Trait Realizations] 度量 [!UICONTROL Total Trait Population] 中，将历史信 [!DNL Audience Manager] 号转换为特征实现。

但是， [!UICONTROL Trait Graph]、和 [!UICONTROL General Reports]不会 [!UICONTROL Trend Reports] 使用在特征创建日期之前回填的历史度量进行追溯更新。