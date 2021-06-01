---
description: 回填特征实现，以捕获历史受众并避免在特征创建日期之前丢失相关数据。
seo-description: 回填特征实现，以捕获历史受众并避免在特征创建日期之前丢失相关数据。
seo-title: 回填特征实现
title: 回填特征实现
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 2%

---

# 回填特征实现 {#backfill-trait-realizations}

回填特征实现，以捕获历史受众并避免在特征创建日期之前丢失相关数据。

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] 是一项高级功能，可通过解锁其他用例来增强Audience Manager体验。回填需要额外的处理能力，并且以递增成本提供给所有Audience Manager客户。 有关更多详细信息，请联系您的Adobe销售代表。

从未使用的信号创建特征时，您可以选择在特定时间段内回填特征实现。 [!DNL Audience Manager] 捕获符合新特征的受众的历史数据，并将其存储在相应的用户档案中。您可以在&#x200B;**[特征生成器](../../features/traits/about-trait-builder.md)**&#x200B;的[!UICONTROL Trait Expression]部分中看到&#x200B;**[!UICONTROL Backfill Options]**。

>[!NOTE]
>
>您可以回填基于规则的特征和已载入的特征的特征实现。

以下是如何回填特征实现：

1. 转到[!UICONTROL Audience Data > Signals > Search]并运行信号搜索，或使用[信号仪表板](../../features/data-explorer/data-explorer-signals-dashboard.md)标识要在新特征中使用的信号。
1. 根据所需的信号创建新特征。
1. 使用&#x200B;**[!UICONTROL Trait Expression]**&#x200B;部分的&#x200B;**[!UICONTROL Backfill Options]**&#x200B;选择要回填特征实现的时间间隔。 预定义的回填间隔包括1、7、14和30天。 您还可以选择最多30天的自定义日期范围。

   ![特征回填](assets/signals-trait-backfill.png)

1. （可选）单击&#x200B;**[!UICONTROL Estimated Trait Realizations]**&#x200B;部分中的&#x200B;**[!UICONTROL Estimate Realizations]**&#x200B;以查看过去7天内回填特征的预计[!UICONTROL Unique Trait Realizations]和[!UICONTROL Total Trait Population]值。

   ![估计 — 特征实现](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >特征回填和估计不适用于使用以下运算符的表达式的特征：
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 创建特征。

创建完特征后，您将看到其回填的实现情况包含在实现统计信息中。

请观看以下视频，以了解如何回填特征的视频演练。

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## 特征回填延迟{#trait-backfilling-latency}

新创建的特征在创建后的两到三小时内即开始捕获受众。 但是，由于[!DNL Audience Manager]每天执行的数据量很大，因此回填的群体不会立即反映在[!UICONTROL Unique Trait Realizations]和[!UICONTROL Total Trait Population]图表中。

Audience Manager会在特征创建后48小时内使用回填的群体更新[!UICONTROL Trait Graph]。

## 特征回填限制{#trait-backfilling-limit}

[!UICONTROL Data Explorer] 允许您每月回填最多50个特征，并在每月的1天重置回填计数器。

>[!NOTE]
>
>特征回填配额不会结转前几个月。 例如，如果您本月回填30个特征，则下个月的特征回填配额将重置为50，而不是70。

## 对报表的影响{#reporting-impact}

回填的特征实现会反映在[!UICONTROL Unique Trait Realizations]和[!UICONTROL Total Trait Population]量度中，因为[!DNL Audience Manager]会将历史信号转换为特征实现。

但是，不会以在特征创建日期之前回填的历史量度来追溯更新[!UICONTROL Trait Graph]、[!UICONTROL General Reports]和[!UICONTROL Trend Reports]。
