---
description: 本文介绍了特征生成器使用的比较运算符。
seo-description: 本文介绍了特征生成器使用的比较运算符。
seo-title: 在特征生成器中使用比较运算符
solution: Audience Manager
title: 在特征生成器中使用比较运算符
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: 特征
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 12%

---

# 在特征生成器中使用比较运算符 {#working-with-comparison-operators-in-trait-builder}

本文介绍了[!UICONTROL Trait Builder]使用的比较运算符。

## 比较运算符的用途

<!-- c_tb_comparison_operators.xml -->

比较运算符（或关系运算符）用于比较、测试或评估不同值之间的关系。 在[!UICONTROL Trait Builder]中，构建信号规则时，比较运算符允许您测试不同键值对之间的关系。 例如，您可以创建一个信号规则来为昂贵的相机购买者定义受众。 在这种情况下，您可以创建相机/价格键值对，如果用户查找了价格等于或大于设定金额的相机，则可以确定其资格。

## 比较运算符的优势

当您需要根据多个值评估和创建特征时，比较运算符非常有用。 看看商品和服务的价格可以说明这种情况。 例如，您的企业可能希望根据他们查看的产品价格来识别访客。 但是，根据特定值定义单个区段在管理上可能效率低下。 比较运算符通过根据价格阈值或范围建立分段触发器来帮助克服这一障碍。

## 比较运算符

您可以使用以下比较运算符构建规则：

| 运算符 | 定义 |
|---|---|
| **==** | 等于 |
| **!=** | 不等于 |
| **>** | 大于 |
| **&lt;** | 小于 |
| **=>** | 大于/等于 |
| **&lt;=** | 小于/等于 |

## 命名运算符

您可以使用以下命名的运算符生成规则：

| 运算符 | 计算结果为[!DNL True]时间 |
|---|---|
| **[!UICONTROL Contains]** | 键值对&#x200B;*中的值包含由此运算符指定的*&#x200B;字符。 |
| **[!UICONTROL Matcheswords]** | 键值对&#x200B;*中的值与此运算符指定的模式*&#x200B;匹配。 |
| **[!UICONTROL Startswith]** | 键值对&#x200B;*中的值以*&#x200B;字符开头，这些字符由此运算符指定。 |
| **[!UICONTROL Endswith]** | 键值对&#x200B;*中的值以*&#x200B;此运算符指定的字符结尾。 |
| **[!UICONTROL Matchesregex]** | 键值对&#x200B;*中的值与正则表达式指定的模式*&#x200B;匹配。 [进一](../../features/traits/trait-builder-regex.md) 步了解如何在中使用正则表 [!UICONTROL Trait Builder]达式。 |

>[!MORELIKETHIS]
>
>* [特征和区段生成器中的布尔表达式](../../reference/boolean-expressions-tsb.md)
* [了解TraitBuilder中的布尔表达式](../../reference/boolean-expressions-tsb.md)
* [特征生成器表达式中的运算顺序](../../features/traits/trait-operator-precedence.md)
* [含布尔和比较运算符的示例表达式](../../features/traits/trait-expression-samples.md)

