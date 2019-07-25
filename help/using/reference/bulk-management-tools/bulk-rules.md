---
description: 创建和更新工作表接受了一个Trit规则标题，它允许您在一个操作中应用多个规则。按照这些说明进行批量规则请求。
seo-description: 创建和更新工作表接受了一个Trit规则标题，它允许您在一个操作中应用多个规则。按照这些说明进行批量规则请求。
seo-title: 创建或更新特征规则和区段规则
solution: Audience Manager
title: 创建或更新特征规则和区段规则
uuid: bdd5f8f1-bb83-4844-b681-654e45 ace3 e1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create or Update Trait Rules and Segment Rules{#create-or-update-trait-rules-and-segment-rules}

创建和更新工作表接受了一个Trit规则标题，它允许您在一个操作中应用多个规则。按照这些说明进行批量规则请求。

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具仅为方便起见而提供，并且仅作为好意提供。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI中](../../features/administration/administration-overview.md) 分配的CLUAC组权限在 [!DNL Audience Manager] 此中受支持 [!UICONTROL Bulk Management Tools]。

## Working with trait rules {#trait-rules}

在您的工作表中，特征规则列返回并接受由Boolean表达式、比较运算符和正则表达式组成的规则。You can create rules with trait or segment builder in [!DNL Audience Manager] and copy them to your worksheet. 或者，如果您熟悉规则语法，则可以直接在工作表中编写表达式。

## Rule builder example {#rule-builder-example}

Let's take a look at an example that demonstrates how to use [!UICONTROL Segment Builder] to create a rule you can to the bulk worksheet. 但是，这并不是这些工具的一组分步说明。我们将从一个已经创建的简单规则开始。For instructions about how to use the rule builders see [Segment Builder](../../features/segments/segment-builder.md) and [Trait Builder](../../features/traits/about-trait-builder.md).

With the visual rule builder, we've created a segment rule with 3 traits and a Boolean [!UICONTROL AND] operator.

![](assets/visualrule.png)

Click **[!UICONTROL Code View]** to get the text version of this rule.

>[!TIP]
>
>Click **[!UICONTROL Validate Expression]** to check your rule logic. 这将有助于防止上传无效规则。

![](assets/coderule.png)

Paste the rule into the [!UICONTROL Bulk Management Tools] worksheet and commit your changes to update segment rules in bulk.

![](assets/segmentrule.png)

## Creating your own rules {#create-rules}

You can write your own rules outside of [!UICONTROL Rule Builder]. 在开始之前，请务必阅读包含操作符、表达式和所需变量等内容的文档。我们建议您查看以下内容：

* [与特征生成器中的比较运算符协作](../../features/traits/trait-comparison-operators.md)
* [运营顺序](../../features/traits/trait-operator-precedence.md)
* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)
* [使用布尔和比较运算符的示例表达式](../../features/traits/trait-expression-samples.md)

