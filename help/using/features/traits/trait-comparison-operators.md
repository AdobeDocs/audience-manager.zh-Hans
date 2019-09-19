---
description: 本文描述Trait Builder使用的比较运算符。
seo-description: 本文描述Trait Builder使用的比较运算符。
seo-title: 在Trait Builder中使用比较运算符
solution: Audience Manager
title: 在Trait Builder中使用比较运算符
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 在Trait Builder中使用比较运算符 {#working-with-comparison-operators-in-trait-builder}

本文描述了比较运算符 [!UICONTROL Trait Builder]。

## 比较运算符的用途

<!-- c_tb_comparison_operators.xml -->

比较运算符（或关系运算符）用于比较、测试或评估不同值之间的关系。 在构 [!UICONTROL Trait Builder]建信号规则时，比较运算符允许您测试不同键值对之间的关系。 例如，您可以创建一个信号规则来为昂贵的相机购物者定义受众。 在这种情况下，如果用户已查找价格等于或大于设定金额的相机，则可以创建相机／价格键值对并确定其资格。

## 比较算子的优势

当您需要基于多个值评估和创建特征时，比较运算符很有用。 从商品和服务的价格看，可以说明这种情况。 例如，您的企业可能希望根据访客查看的产品价格识别访客。 但是，根据特定值定义各个区段可能在管理上效率低下。 比较运营商通过根据价格阈值或范围建立细分触发器来帮助克服这一障碍。

## 比较运算符

您可以使用以下比较运算符构建规则：

| 运算符 | 定义 |
|---|---|
| **==** | 等于 |
| **!=** | 不等于 |
| **&gt;** | 大于 |
| **&lt;** | 小于 |
| **=&gt;** | 大于／等于 |
| **&lt;=** | 小于／等于 |

## 指定运营商

您可以使用以下命名的运算符构建规则：

| 运算符 | 计算时 [!DNL True] 间 |
|---|---|
| **[!UICONTROL Contains]** | 键值对中的值包含由此运 *算符指定* 的字符。 |
| **[!UICONTROL Matcheswords]** | 键值对中的值与此运算符 *指定* 的模式匹配。 |
| **[!UICONTROL Startswith]** | 键值对中的值以此运算符 *指定的字符* 开头。 |
| **[!UICONTROL Endswith]** | 键值对中的值以此运算符 *指定的* 字符结束。 |
| **[!UICONTROL Matchesregex]** | 键值对中的值与正则表达式 *指定的* 模式相匹配。 [了解有关在中使用正则表达式的更多信息](../../features/traits/trait-builder-regex.md) ，请访问Adobe Connection cloud中的 [!UICONTROL Trait Builder]Adobe Regular Expressions。 |

>[!MORE_LIKE_THIS]
>
>* [Trait和Segment Builder中的布尔表达式](../../reference/boolean-expressions-tsb.md)
>* [了解TraitBuilder中的布尔表达式](../../reference/boolean-expressions-tsb.md)
>* [TraitBuilder表达式中的操作顺序](../../features/traits/trait-operator-precedence.md)
>* [具有布尔和比较运算符的示例表达式](../../features/traits/trait-expression-samples.md)

