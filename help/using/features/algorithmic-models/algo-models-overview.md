---
description: 描述Audience Manager中可用的算法模型。
keywords: algo模型如何工作预测受众
seo-description: 描述Audience Manager中可用的算法模型。
seo-title: 算法模型概述
solution: Audience Manager
title: 算法模型概述
feature: 算法模型
exl-id: ee5c3392-2756-45c5-b325-41a51d3c494f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 16%

---

# 算法模型概述

## 什么是算法建模{#what-algo-modeling}

Audience Manager中的算法建模是指使用数据科学来扩展现有受众，或将现有受众分类为角色。

这可通过两种类型的算法来完成：[!UICONTROL Look-Alike Modeling]和[!UICONTROL Predictive Audiences]。

## 相似人群拓展建模{#lam}

[!UICONTROL Look-Alike Modeling] 通过自动数据分析帮助您发现新的独特受众。当您选择特征或区段、时间间隔以及第一方和第三方数据源时，将开始该过程。 您的选择为算法模型提供了输入。 运行分析流程时，它会根据所选群体的共享特征查找符合条件的用户。

完成后，此数据将在[特征生成器](../../features/traits/about-trait-builder.md)中提供，您可以在其中使用这些数据根据[准确性创建特征并访问](../../features/traits/trait-accuracy-reach.md)。 此外，您还可以构建将算法特征与基于规则的特征相结合的区段，并使用布尔表达式和比较运算符添加其他资格要求。

[!UICONTROL Look-Alike Modeling] 可让您动态地从所有可用特征数据中提取值。

要了解有关[!UICONTROL Look-Alike Modeling]的更多信息，请参阅[了解相似人群拓展建模](understanding-models.md)。

## Predictive Audiences{#predictive-audiences}

[!UICONTROL Predictive Audiences] 可以帮助您使用高级数据科学技术将未知受众实时分类为不同的角色。

在营销环境中，角色是指由具有一系列相同特征（例如人口统计特征、浏览习惯、购物历史记录等）的访客、用户或潜在购买者构成的一个受众区段。

[!UICONTROL Predictive Audiences] 模型进一步扩展了这一概念的应用，它使用Audience Manager的机器学习功能，将未知受众自动分类为不同的角色。Audience Manager通过为一组已知受众计算未知受众的倾向来实现这一点。

要了解有关[!UICONTROL Predictive Audiences]的更多信息，请参阅[预测受众概述](predictive-audiences.md)。
