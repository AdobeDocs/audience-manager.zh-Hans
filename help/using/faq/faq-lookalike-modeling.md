---
description: 相似人群拓展建模通过自动数据分析帮助您发现新的独特受众。 本文提供了最常见问题的解答。
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: 相似人群拓展建模常见问题解答
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
source-git-commit: 37823ae54e106e32aa195a6b69e0f1ebfc322f09
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# 相似人群拓展建模常见问题解答

## 概述 {#overview}

本文提供了有关 [!UICONTROL Look-Alike Modeling].

## 问题 {#questions}

**为什么我要买公寓 [!UICONTROL Accuracy & Reach] 图形？**

公寓 [!UICONTROL Accuracy & Reach] 图表表示几乎每个用户都收到模型的相同分数。 在运行模型的数据源中包含网站访客特征时，可能会出现这种情况。 要避免这种情况，请在模型创建步骤中，通过使用 [!UICONTROL Exclusions] 字段。

 

**为什么我一些最具影响力的特征的受众非常少？**

算法会选择与基线特征高度相关的特征。 例如，如果给定特征与基线特征的重叠度为100%，则该特征的权重将非常高，即使该特征中的用户数量很少也是如此。

 

**为什么我的模型没有运行/重新运行？**

仅当您创建了至少一个活动算法特征并将其映射到活动区段和目标时，才会继续运行已生成结果的模型。

 

**为什么我的模型没有产生任何结果？**

这通常是因为所选数据源中的基线群体与群体之间没有显着特征重叠所致。

 

**基线特征或区段大小是否有任何推荐？**

鉴于所选数据源中的基线群体与群体之间存在显着的特征重叠，因此几千个用户应该足以在上运行模型。 [!UICONTROL Look-Alike Modeling] 生成的结果更准确，基线越大。

 

**我应该为模型选择哪些第三方数据源？**

使用与基线特征/区段至少有一些重叠的数据源，但同时吸引更多用户。 您还应考虑与每个数据馈送关联的成本。 在 [!UICONTROL Audience Marketplace].

 

**使用第三方数据进行建模是否需要花费？**

它取决于所选数据馈送的定价模型。 有些信息源允许免费进行建模，而另一些信息源则需要收取费用。 请参阅 [面向数据信息源购买者的账单](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md) 以了解详细信息。

 

**我可以创建多少个模型/特征？**

目前，您最多可以创建20个算法模型和50个算法特征。

 

**模型培训和算法特征群体的刷新频率是多少？**

模型每8天重新培训一次，并刷新算法特征群体。
