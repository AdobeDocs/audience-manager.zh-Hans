---
description: 创建和更新工作表接受traitRule标题，它允许您在单个操作中应用多个规则。 按照以下说明进行批量规则请求。
seo-description: 创建和更新工作表接受traitRule标题，它允许您在单个操作中应用多个规则。 按照以下说明进行批量规则请求。
seo-title: 创建或更新特征规则和区段规则
solution: Audience Manager
title: 创建或更新特征规则和区段规则
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 10%

---

# 创建或更新特征规则和区段规则{#create-or-update-trait-rules-and-segment-rules}

创建和更新工作表接受traitRule标题，它允许您在单个操作中应用多个规则。 按照以下说明进行批量规则请求。

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[在UI中](../../features/administration/administration-overview.md) 分配的RBAC组 [!DNL Audience Manager] 权限在中得以执行 [!UICONTROL Bulk Management Tools]。

## 使用特征规则{#trait-rules}

在您的工作表中，特征规则列返回并接受由布尔表达式、比较运算符和常规表达式组成的规则。 您可以在[!DNL Audience Manager]中创建具有特征或区段生成器的规则，并将其复制到您的工作表。 或者，如果您熟悉规则语法，则可以直接在工作表中编写表达式。

## 规则生成器示例{#rule-builder-example}

让我们看一个示例，它演示了如何使用[!UICONTROL Segment Builder]创建可用于批量工作表的规则。 但是，这不是针对这些工具的一组分步说明。 相反，我们将使用已经创建的简单规则进行开始。 有关如何使用规则生成器的说明，请参阅[区段生成器](../../features/segments/segment-builder.md)和[特征生成器](../../features/traits/about-trait-builder.md)。

利用可视规则构建器，我们创建了一个具有3个特征的区段规则和一个布尔[!UICONTROL AND]运算符。

![](assets/visualrule.png)

单击&#x200B;**[!UICONTROL Code View]**&#x200B;获取此规则的文本版本。

>[!TIP]
>
>单击&#x200B;**[!UICONTROL Validate Expression]**&#x200B;检查规则逻辑。 这将有助于阻止您上传无效规则。

![](assets/coderule.png)

将规则粘贴到[!UICONTROL Bulk Management Tools]工作表中，并提交更改以批量更新区段规则。

![](assets/segmentrule.png)

## 创建您自己的规则{#create-rules}

您可以在[!UICONTROL Rule Builder]之外编写您自己的规则。 在开始之前，请务必阅读涵盖操作符、表达式和必需变量等内容的文档。 我们建议您查看以下内容：

* [在特征生成器中使用比较运算符](../../features/traits/trait-comparison-operators.md)
* [运营顺序](../../features/traits/trait-operator-precedence.md)
* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)
* [含布尔和比较运算符的示例表达式](../../features/traits/trait-expression-samples.md)
