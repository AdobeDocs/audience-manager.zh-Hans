---
description: 使用逻辑运算符对键值对和回填特征进行分组。
seo-description: 使用逻辑运算符对键值对和回填特征进行分组。
seo-title: 支持的逻辑运算符
title: 支持的逻辑运算符
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 10%

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
| **=>** | 大于/等于 |
| **&lt;=** | 小于/等于 |

### 命名运算符

| 运算符 | 计算结果为[!DNL True]时间 |
|---|---|
| **[!UICONTROL Contains]** | 键值对&#x200B;*中的值包含由此运算符指定的*&#x200B;字符。 |
| **[!UICONTROL Startswith]** | 键值对&#x200B;*中的值以*&#x200B;字符开头，这些字符由此运算符指定。 |
| **[!UICONTROL Endswith]** | 键值对&#x200B;*中的值以*&#x200B;此运算符指定的字符结尾。 |

## 支持的特征回填和估计运算符{#supported-operators-backfilling}

您可以回填特征，该特征包含包含[!UICONTROL Signal Search]支持的任意运算符的表达式。 除了这些运算符之外，特征回填和估计还支持[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL AND NOT]逻辑运算符，用于组合回填特征表达式中的键值对。
