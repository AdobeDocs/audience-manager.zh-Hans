---
description: 相似人群拓展建模可帮助您通过自动数据分析发现新的独特受众。 本文为最常见的问题提供了答案。
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: 相似建模常见问题解答
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
source-git-commit: 37823ae54e106e32aa195a6b69e0f1ebfc322f09
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# 相似建模常见问题解答

## 概述 {#overview}

本文提供了有关[!UICONTROL Look-Alike Modeling]的最常见问题解答。

## 问题 {#questions}

**为什么我会得到一个平面的[!UICONTROL Accuracy & Reach]图形？**

平面的[!UICONTROL Accuracy & Reach]图表示模型几乎每位用户都获得了相同的得分。 如果在运行模型的数据源中包含网站访客特征，则可能会发生这种情况。 要避免这种情况，请在模型创建步骤期间使用[!UICONTROL Exclusions]字段从模型输入中删除通用特征。

 

**为什么我的一些最具影响力特征只有很小的受众？**

算法选择与基线特征高度相关的特征。 例如，如果某个给定特征与基线特征重叠100%，那么即使该特征中的用户数较少，该特征也会具有非常高的权重。

 

**为什么我的模型没有运行/重新运行？**

只有在创建至少一个活动算法特征并将其映射到活动区段和目标时，已生成结果的模型才会继续运行。

 

**为什么我的模型没有生成任何结果？**

通常是由于所选数据源中的基线群体和群体之间没有显着特征重叠所致。

 

**在基线特征或区段大小上是否有任何推荐？**

鉴于基线群体与选定数据源中的群体之间存在显着的特征重叠，只有数千名用户才足以运行模型。 [!UICONTROL Look-Alike Modeling]生成更准确的结果，基线越大。

 

**我应该为模型选择哪些第三方数据源？**

请使用与基线特征/区段至少有一些重叠，但同时会引入更多用户的数据源。 您还应考虑与每个数据馈送关联的成本。 在[!UICONTROL Audience Marketplace]中，成本和定价模型因数据提供商而异。

 

**使用第三方数据进行建模是否耗费？**

这取决于所选数据馈送的定价模型。 某些馈送允许免费建模，而其他馈送则向您收费。 有关详细信息，请参阅[数据馈送购买者的账单](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)。

 

**我可以创建多少个模型/特征？**

目前，您最多可以创建20个算法模型和50个算法特征。

 

**模型训练和算法特征填充的刷新频率是多少？**

该模型每8天重新训练一次，并刷新算法特征群体。
