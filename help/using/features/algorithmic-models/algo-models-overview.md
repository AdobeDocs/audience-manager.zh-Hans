---
description: 說明Audience Manager中可用的演演算法模型。
keywords: 演演算法會模擬預測受眾的運作方式
seo-description: Describes the algorithmic models available in Audience Manager.
seo-title: Algorithmic Models Overview
solution: Audience Manager
title: 算法模型概述
feature: Algorithmic Models
exl-id: ee5c3392-2756-45c5-b325-41a51d3c494f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 15%

---

# 算法模型概述

## 什麼是演演算法建模{#what-algo-modeling}

Audience Manager中的演演算法模型是指使用資料科學來擴展您現有的對象，或將其分類為角色。

這是透過兩種型別的演演算法完成： [!UICONTROL Look-Alike Modeling] 和 [!UICONTROL Predictive Audiences].

## 相似人群拓展建模{#lam}

[!UICONTROL Look-Alike Modeling] 可協助您透過自動化資料分析，探索新的不重複受眾。 當您選取特徵或區段、時間間隔以及第一方和第三方資料來源時，流程就會開始。 您的選擇會提供演演算法模型的輸入。 分析程式執行時，會根據所選母體的共用特性來尋找合格使用者。

完成後，此資料可用於 [特徵產生器](../../features/traits/about-trait-builder.md) 您可以在其中根據下列專案建立特徵： [精確度和觸及](../../features/traits/trait-accuracy-reach.md). 此外，您也可以建立區段，將演演算法特徵與規則型特徵結合，並使用布林運算式和比較運運算元新增其他資格需求。

[!UICONTROL Look-Alike Modeling] 可讓您以動態方式從所有可用特徵資料中擷取值。

若要深入瞭解 [!UICONTROL Look-Alike Modeling]，請參閱 [瞭解相似建模](understanding-models.md).

## Predictive Audiences{#predictive-audiences}

[!UICONTROL Predictive Audiences] 可協助您使用進階資料科學技術，即時將未知的受眾分類為不重複角色。

在营销环境中，角色是指由具有一系列相同特征（例如人口统计特征、浏览习惯、购物历史记录等）的访客、用户或潜在购买者构成的一个受众区段。

[!UICONTROL Predictive Audiences] 模型透過Audience Manager的機器學習功能，將未知的受眾自動分類為不重複角色，進一步運用此概念。 Audience Manager會計算未知對象對一組已知對象的傾向，以達到此目的。

若要深入瞭解 [!UICONTROL Predictive Audiences]，請參閱 [預測受眾概述](predictive-audiences.md).
