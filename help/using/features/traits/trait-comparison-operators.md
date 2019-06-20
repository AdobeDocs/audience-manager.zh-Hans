---
description: 本文描述了Travientity Builder使用的比较运算符。
seo-description: 本文描述了Travientity Builder使用的比较运算符。
seo-title: 与特征生成器中的比较运算符协作
solution: Audience Manager
title: 与特征生成器中的比较运算符协作
uuid: 41bec3b3-e5 df-4a6 f-abb0-80ce4 c75 f5 e7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Working with Comparison Operators in Trait Builder {#working-with-comparison-operators-in-trait-builder}

This article describes the comparison operators used by [!UICONTROL Trait Builder].

## 比较运算符的用途

<!-- c_tb_comparison_operators.xml -->

比较运算符(或关系运算符)用于比较、测试或评估不同值之间的关系。In [!UICONTROL Trait Builder], when building signal rules, comparison operators let you test the relationship between different key-value pairs. 例如，您可以创建一条信号规则，为昂贵的相机购物者定义受众。在这种情况下，您可以创建相机/价目键对，并确定用户是否找到了价格等于或大于固定金额的相机。

## 比较运算符优势

比较运算符在需要根据多个值评估和创建特征时很有用。了解商品和服务的价格可以说明这种情况。例如，您的企业可能希望根据他们查看的产品价格确定访客。但是，它可以在管理上低效地根据特定值定义各个区段。比较运算符可根据价格阈值或范围建立细分触发器，帮助克服这一障碍。

## 比较运算符

您可以使用以下比较运算符构建规则：

| 运算符 | 定义 |
|---|---|
| **==** | 等于 |
| **!=** | 不等于 |
| **&gt;** | 大于 |
| **&lt;** | 小于 |
| **=&gt;** | 大于/等于 |
| **&lt;=** | 小于/等于 |

## 指定运营商

您可以使用以下指定操作符构建规则：

| 运算符 | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Matcheswords]** | The value in a key-value pair *matches* the pattern specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |
| **[!UICONTROL Matchesregex]** | The value in a key-value pair *matches* the pattern specified by a regular expression. [了解有关](../../features/traits/trait-builder-regex.md) 使用正则表达式的更多信息 [!UICONTROL Trait Builder]。 |

>[!MORE_ LIKE_ This]
>
>* [特征和区段生成器中的布尔表达式](../../reference/boolean-expressions-tsb.md)
>* [了解TraitBuilder中的Boolean表达式](../../reference/boolean-expressions-tsb.md)
>* [TritBuilder表达式中的操作顺序](../../features/traits/trait-operator-precedence.md)
>* [使用布尔和比较运算符的示例表达式](../../features/traits/trait-expression-samples.md)

