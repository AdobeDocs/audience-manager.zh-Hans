---
description: 使用逻辑运算符将键值对和回填特征分组。
seo-description: 使用逻辑运算符将键值对和回填特征分组。
seo-title: 支持的逻辑运算符
title: 支持的逻辑运算符
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# 支持的逻辑运算符 {#supported-logical-operators}

使用逻辑运算符将键值对和回填特征分组。

## 支持的信号搜索操作符 {#supported-operators-search}

使用以下支持的逻辑运算符搜索键值对：

### 比较运算符

| 运算符 | 定义 |
|---|---|
| **==** | 等于 |
| **&gt;** | 大于 |
| **&lt;** | 小于 |
| **=&gt;** | 大于／等于 |
| **&lt;=** | 小于／等于 |

### 指定运营商

| 运算符 | 计算时 [!DNL True] 间 |
|---|---|
| **[!UICONTROL Contains]** | 键值对中的值包含由此运 *算符指定* 的字符。 |
| **[!UICONTROL Startswith]** | 键值对中的值以此运算符 *指定的字符* 开头。 |
| **[!UICONTROL Endswith]** | 键值对中的值以此运算符 *指定的* 字符结束。 |

## 特征回填和估计的支持算子 {#supported-operators-backfilling}

您可以回填包含包含受支持的任何运算符的表达式的特征 [!UICONTROL Signal Search]。 除了这些运算符外，特征回填和估计还支持 [!UICONTROL AND]、 [!UICONTROL OR]和逻辑运算符 [!UICONTROL AND NOT] ，这些运算符用于在回填的特征表达式中组合键值对。