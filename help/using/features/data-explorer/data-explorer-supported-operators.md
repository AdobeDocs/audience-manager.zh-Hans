---
description: 使用逻辑运算符对键值对和回填特征进行分组。
seo-description: 使用逻辑运算符对键值对和回填特征进行分组。
seo-title: 支持的逻辑运算符
title: 支持的逻辑运算符
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 9%

---


# 支持的逻辑运算符 {#supported-logical-operators}

使用逻辑运算符对键值对和回填特征进行分组。

## 支持的信号搜索{#supported-operators-search}运算符

使用以下支持的逻辑运算符搜索键值对：

### 比较运算符

| 运算符 | 定义 |
|---|---|
| **==** | 等于 |
| **>** | 大于 |
| **&lt;** | 小于 |
| **=>** | 大于／等于 |
| **&lt;=** | 小于或等于 |

### 命名运算符

| 运算符 | 计算结果为[!DNL True] |
|---|---|
| **[!UICONTROL Contains]** | 键值对&#x200B;*中的值包含由此运算符指定的*&#x200B;字符。 |
| **[!UICONTROL Startswith]** | 键——值对&#x200B;*中具有由此运算符指定的*&#x200B;字符的开始的值。 |
| **[!UICONTROL Endswith]** | 键值对&#x200B;*中的值以*&#x200B;此运算符指定的字符结尾。 |

## 特征回填和估计{#supported-operators-backfilling}支持的运算符

您可以回填包含表达式的特征，这些特征包含[!UICONTROL Signal Search]支持的任何运算符。 除了这些运算符外，特征回填和估计还支持[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL AND NOT]逻辑运算符，它们用于组合回填特征表达式中的键值对。