---
description: 使用逻辑运算符对键值对进行分组，并回填特征。
seo-description: Use logical operators to group key-value pairs and backfill traits.
seo-title: Supported Logical Operators
title: 支持的逻辑运算符
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
TQID: https://experienceleague.adobe.com/m9daAh4HRSx5zwBX-ByQU0dLVy-KOt3RMrdjGvFqsMU
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 151
ht-degree: 4%

---

# 支持的逻辑运算符 {#supported-logical-operators}

使用逻辑运算符对键值对进行分组，并回填特征。

## 信号搜索支持的运算符 {#supported-operators-search}

使用以下受支持的逻辑运算符搜索键值对：

### 比较运算符

| 操作员 | 定义 |
|---|---|
| **==** | 等于 |
| **>** | 大于 |
| **&lt;** | 小于 |
| **=>** | 大于/等于 |
| **&lt;=** | 小于/等于 |

### 已命名的运算符

| 操作员 | 评估为[!DNL True]的情况 |
|---|---|
| **[!UICONTROL Contains]** | 键值对&#x200B;*中的值包含此运算符指定的*&#x200B;个字符。 |
| **[!UICONTROL Startswith]** | 键值对&#x200B;*中的值以此运算符指定的*&#x200B;字符开头。 |
| **[!UICONTROL Endswith]** | 键值对&#x200B;*中的值以*&#x200B;此运算符指定的字符结尾。 |

## 特征回填和估计支持的运算符 {#supported-operators-backfilling}

您可以回填包含表达式的特征，该表达式包含[!UICONTROL Signal Search]支持的任何运算符。 除了这些运算符外，特征回填和估计还支持[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL AND NOT]逻辑运算符，这些运算符用于在回填的特征表达式中组合键值对。
