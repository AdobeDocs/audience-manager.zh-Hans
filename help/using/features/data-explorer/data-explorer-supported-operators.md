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

## 支持的信号搜索操作符 {#supported-operators-search}

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

| 运算符 | 评估时 [!DNL True] 间 |
|---|---|
| **[!UICONTROL Contains]** | 键值对中的值包含此运 *算符* 指定的字符。 |
| **[!UICONTROL Startswith]** | 键值对开始中的值， *其字符由* 此运算符指定。 |
| **[!UICONTROL Endswith]** | 键值对中的值以此运 *算符* 指定的字符结尾。 |

## 特征回填和估计的支持算子 {#supported-operators-backfilling}

您可以回填包含表达式的特征，这些特征包含受支持的任何运算符 [!UICONTROL Signal Search]。 除了这些运算符外，特征回填和估计还支 [!UICONTROL AND]持 [!UICONTROL OR]、和 [!UICONTROL AND NOT] 逻辑运算符，它们用于在回填的特征表达式内组合键值对。