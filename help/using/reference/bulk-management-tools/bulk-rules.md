---
description: 创建和更新工作表接受一个traitRule标头，通过该标头，您可以在单个操作中应用多个规则。 按照这些说明发出批量规则请求。
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: 创建或更新特征规则和区段规则
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# 创建或更新特征规则和区段规则{#create-or-update-trait-rules-and-segment-rules}

创建和更新工作表接受一个traitRule标头，通过该标头，您可以在单个操作中应用多个规则。 按照这些说明发出批量规则请求。

>[!IMPORTANT]
>
>批量管理工具不是官方支持的Adobe产品。 通过客户关怀团队提供的故障排除和支持将按具体情况处理。

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[接受在](../../features/administration/administration-overview.md) UI中分配的[!DNL Audience Manager]RBAC组权限[!UICONTROL Bulk Management Tools]。

## 使用特征规则 {#trait-rules}

在您的工作表中，特征规则列将返回并接受由布尔表达式、比较运算符和正则表达式组成的规则。 您可以在[!DNL Audience Manager]中创建具有特征或区段生成器的规则，并将它们复制到您的工作表中。 或者，如果您熟悉规则语法，可以直接在工作表中编写表达式。

## 规则生成器示例 {#rule-builder-example}

让我们看一个示例，该示例演示如何使用[!UICONTROL Segment Builder]创建可以处理批量工作表的规则。 但是，这并非这些工具的一组分步说明。 相反，我们将从已创建的简单规则开始。 有关如何使用规则生成器的说明，请参阅[区段生成器](../../features/segments/segment-builder.md)和[特征生成器](../../features/traits/about-trait-builder.md)。

通过可视化规则生成器，我们创建了一个区段规则，该规则具有3个特征和一个布尔值[!UICONTROL AND]运算符。

![](assets/visualrule.png)

单击&#x200B;**[!UICONTROL Code View]**&#x200B;以获取此规则的文本版本。

>[!TIP]
>
>单击&#x200B;**[!UICONTROL Validate Expression]**&#x200B;以检查您的规则逻辑。 这样有助于防止您上传无效的规则。

![](assets/coderule.png)

将规则粘贴到[!UICONTROL Bulk Management Tools]工作表并提交更改以批量更新区段规则。

![](assets/segmentrule.png)

## 创建您自己的规则 {#create-rules}

您可以在[!UICONTROL Rule Builder]之外编写您自己的规则。 在开始之前，请务必阅读涵盖运算符、表达式和必需变量等内容的文档。 我们建议您查看以下内容：

* [在特征生成器中使用比较运算符](../../features/traits/trait-comparison-operators.md)
* [操作顺序](../../features/traits/trait-operator-precedence.md)
* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)
* [带布尔和比较运算符的示例表达式](../../features/traits/trait-expression-samples.md)
