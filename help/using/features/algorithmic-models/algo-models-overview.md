---
description: 描述Audience Manager中可用的算法模型。
keywords: 算法可模拟预测受众的工作方式
seo-description: Describes the algorithmic models available in Audience Manager.
seo-title: Algorithmic Models Overview
solution: Audience Manager
title: 算法模型概述
feature: Algorithmic Models
exl-id: ee5c3392-2756-45c5-b325-41a51d3c494f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---

# 算法模型概述

## 什么是算法建模{#what-algo-modeling}

Audience Manager中的算法建模是指使用数据科学来扩展现有受众或将其分类为角色。

这是通过两种类型的算法完成的： [!UICONTROL Look-Alike Modeling]和[!UICONTROL Predictive Audiences]。

## 相似建模{#lam}

[!UICONTROL Look-Alike Modeling]可帮助您通过自动数据分析发现新的独特受众。 当您选择特征或区段、时间间隔以及第一方和第三方数据源时，流程就会开始。 您的选择为算法模型提供输入。 Analytics流程运行时，会根据选定群体的共享特征查找符合条件的用户。

完成后，此数据将在[特征生成器](../../features/traits/about-trait-builder.md)中可用，您可以在其中使用它根据[精度和范围](../../features/traits/trait-accuracy-reach.md)创建特征。 此外，您还可以构建将算法特征与基于规则的特征相结合的区段，并使用布尔表达式和比较运算符添加其他资格要求。

[!UICONTROL Look-Alike Modeling]为您提供了一种从所有可用特征数据中提取值的动态方法。

要了解有关[!UICONTROL Look-Alike Modeling]的更多信息，请参阅[了解相似人群拓展建模](understanding-models.md)。

## Predictive Audiences{#predictive-audiences}

[!UICONTROL Predictive Audiences]可帮助您使用高级数据科学技术将未知受众实时分类为不同的角色。

在营销环境中，人物是由访客、用户或潜在购买者定义的受众区段，他们具有一组特定特征，如人口统计信息、浏览习惯、购物历史记录等。

[!UICONTROL Predictive Audiences]模型通过使用Audience Manager的机器学习功能将未知受众自动分类为不同的角色，进一步扩展了此概念。 Audience Manager通过为一组已知受众计算未知受众的倾向来实现这一点。

要了解有关[!UICONTROL Predictive Audiences]的更多信息，请参阅[预测受众概述](predictive-audiences.md)。
