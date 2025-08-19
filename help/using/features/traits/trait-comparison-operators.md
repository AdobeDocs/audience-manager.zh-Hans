---
description: 本文介绍了特征生成器使用的比较运算符。
seo-description: This article describes the comparison operators used by Trait Builder.
seo-title: Working with Comparison Operators in Trait Builder
solution: Audience Manager
title: 在特征生成器中使用比较运算符
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 6%

---

# 在特征生成器中使用比较运算符 {#working-with-comparison-operators-in-trait-builder}

本文介绍[!UICONTROL Trait Builder]使用的比较运算符。

## 比较运算符的用途

<!-- c_tb_comparison_operators.xml -->

比较运算符（或关系运算符）用于比较、测试或评估不同值之间的关系。 在[!UICONTROL Trait Builder]中，在构建信号规则时，比较运算符允许您测试不同键值对之间的关系。 例如，您可以创建一个信号规则，以便为昂贵的相机购物者定义受众。 在这种情况下，您可以创建一个摄像头/价格键值对，如果用户已查找价格等于或大于设置数量的摄像头，则表明用户符合条件。

## 比较运算符的优势

在需要根据多个值评估和创建特征时，比较运算符非常有用。 观察商品和服务的价格就可以说明这种情况。 例如，您的企业可能希望根据访客所查看产品的价格来识别访客。 但是，根据特定值定义各个区段在管理上可能效率低下。 比较运算符通过基于价格阈值或范围建立分段触发器，帮助克服此障碍。

## 比较运算符

您可以使用以下比较运算符构建规则：

| 操作员 | 定义 |
|---|---|
| **==** | 等于 |
| **!=** | 不等于 |
| **>** | 大于 |
| **&lt;** | 小于 |
| **=>** | 大于/等于 |
| **&lt;=** | 小于/等于 |

## 已命名的运算符

您可以使用以下命名运算符构建规则：

| 操作员 | 评估为[!DNL True]的情况 |
|---|---|
| **[!UICONTROL Contains]** | 键值对&#x200B;*中的值包含此运算符指定的*&#x200B;个字符。 |
| **[!UICONTROL Matcheswords]** | 键值对&#x200B;*中的值与此运算符指定的模式匹配*。 |
| **[!UICONTROL Startswith]** | 键值对&#x200B;*中的值以此运算符指定的*&#x200B;字符开头。 |
| **[!UICONTROL Endswith]** | 键值对&#x200B;*中的值以*&#x200B;此运算符指定的字符结尾。 |
| **[!UICONTROL Matchesregex]** | 键值对&#x200B;*中的值与*&#x200B;正则表达式指定的模式匹配。 [了解有关](../../features/traits/trait-builder-regex.md)中使用正则表达式的详细信息[!UICONTROL Trait Builder]。 |

>[!MORELIKETHIS]
>
>* [特征和区段生成器中的布尔表达式](../../reference/boolean-expressions-tsb.md)
>* [了解TraitBuilder中的布尔表达式](../../reference/boolean-expressions-tsb.md)
>* TraitBuilder表达式中的[运算顺序](../../features/traits/trait-operator-precedence.md)
>* [含布尔和比较运算符的示例表达式](../../features/traits/trait-expression-samples.md)
