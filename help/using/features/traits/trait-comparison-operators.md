---
description: 本文介绍Trait Builder使用的比较运算符。
seo-description: 本文介绍Trait Builder使用的比较运算符。
seo-title: 在特征生成器中使用比较运算符
solution: Audience Manager
title: 在特征生成器中使用比较运算符
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 11%

---


# 在特征生成器中使用比较运算符 {#working-with-comparison-operators-in-trait-builder}

本文描述[!UICONTROL Trait Builder]使用的比较运算符。

## 比较运算符的用途

<!-- c_tb_comparison_operators.xml -->

比较运算符（或关系运算符）用于比较、测试或评估不同值之间的关系。 在[!UICONTROL Trait Builder]中，构建信号规则时，比较运算符允许您测试不同键值对之间的关系。 例如，您可以创建一个信号规则，为昂贵的相机购物者定义受众。 在这种情况下，如果用户已查找价格等于或大于设定金额的相机，则可以创建相机／价格键值对并确定其资格。

## 比较算子的优势

当您需要根据多个值评估和创建特征时，比较运算符很有用。 从商品和服务的价格看，可以说明这一条件。 例如，您的企业可能希望根据访客所视图产品的价格确定客户。 但是，根据特定值定义各个细分可能在管理上效率低下。 比较运算符通过根据价格阈值或范围建立细分触发器来帮助克服这一障碍。

## 比较运算符

您可以使用以下比较运算符构建规则：

| 运算符 | 定义 |
|---|---|
| **==** | 等于 |
| **!=** | 不等于 |
| **>** | 大于 |
| **&lt;** | 小于 |
| **=>** | 大于／等于 |
| **&lt;=** | 小于或等于 |

## 命名运算符

您可以使用以下命名运算符构建规则：

| 运算符 | 计算结果为[!DNL True] |
|---|---|
| **[!UICONTROL Contains]** | 键值对&#x200B;*中的值包含由此运算符指定的*&#x200B;字符。 |
| **[!UICONTROL Matcheswords]** | 键值对&#x200B;*中的值与此运算符指定的模式*&#x200B;匹配。 |
| **[!UICONTROL Startswith]** | 键——值对&#x200B;*中具有由此运算符指定的*&#x200B;字符的开始的值。 |
| **[!UICONTROL Endswith]** | 键值对&#x200B;*中的值以*&#x200B;此运算符指定的字符结尾。 |
| **[!UICONTROL Matchesregex]** | 键值对&#x200B;*中的值与由常规表达式指定的模式*&#x200B;匹配。 [了解](../../features/traits/trait-builder-regex.md) 有关使用常规表达式的更多 [!UICONTROL Trait Builder]信息。 |

>[!MORELIKETHIS]
>
>* [特征和区段生成器中的布尔表达式](../../reference/boolean-expressions-tsb.md)
>* [了解TraitBuilder中的布尔表达式](../../reference/boolean-expressions-tsb.md)
>* [TraitBuilder表达式中的操作顺序](../../features/traits/trait-operator-precedence.md)
>* [含布尔和比较运算符的示例表达式](../../features/traits/trait-expression-samples.md)

