---
description: 使用逻辑操作符对键值对和回填特征进行分组。
seo-description: 使用逻辑操作符对键值对和回填特征进行分组。
seo-title: 支持的逻辑运算符
title: 支持的逻辑运算符
uuid: 645fcb6f-50ac-49bc-8df9-c699 c749 cf8 f
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Supported Logical Operators {#supported-logical-operators}

使用逻辑操作符对键值对和回填特征进行分组。

## Supported Operators for Signal Search {#supported-operators-search}

使用以下支持的逻辑运算符搜索键值对：

### 比较运算符

| 运算符 | 定义 |
|---|---|
| **==** | 等于 |
| **&gt;** | 大于 |
| **&lt;** | 小于 |
| **=&gt;** | 大于/等于 |
| **&lt;=** | 小于/等于 |

### 指定运营商

| 运算符 | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |

## Supported Operators for Trait Backfilling and Estimation {#supported-operators-backfilling}

You can backfill traits that include expressions containing any of the operators supported by [!UICONTROL Signal Search]. In addition to these operators, trait backfilling and estimation also support the [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL AND NOT] logical operators, used to combine key-value pairs within the backfilled trait expressions.