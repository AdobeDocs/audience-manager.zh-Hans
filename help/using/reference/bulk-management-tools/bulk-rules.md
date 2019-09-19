---
description: 创建和更新工作表接受traitRule标题，通过该标题，您可以在单个操作中应用多个规则。 请按照以下说明进行批量规则请求。
seo-description: 创建和更新工作表接受traitRule标题，通过该标题，您可以在单个操作中应用多个规则。 请按照以下说明进行批量规则请求。
seo-title: 创建或更新特征规则和区段规则
solution: Audience Manager
title: 创建或更新特征规则和区段规则
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 创建或更新特征规则和区段规则{#create-or-update-trait-rules-and-segment-rules}

创建和更新工作表接受traitRule标题，通过该标题，您可以在单个操作中应用多个规则。 请按照以下说明进行批量规则请求。

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>不 [!UICONTROL Bulk Management Tools] 支持 *。*[!DNL Audience Manager]此工具仅出于方便和礼貌而提供。 对于批量更改，我们建议您改用 [Audience Manager API](../../api/rest-api-main/aam-api-getting-started.md) 。 [在UI中分配的](../../features/administration/administration-overview.md) RBAC组权限 [!DNL Audience Manager] 在UI中被接受 [!UICONTROL Bulk Management Tools]。

## 使用特征规则 {#trait-rules}

在您的工作表中，特征规则列返回并接受由布尔表达式、比较运算符和正则表达式组成的规则。 您可以在中创建带特征或区段构建器的规 [!DNL Audience Manager] 则，并将其复制到您的工作表。 或者，如果您熟悉规则语法，则可以直接在工作表中编写表达式。

## 规则构建器示例 {#rule-builder-example}

我们来看一个示例，其中演示了如何使用 [!UICONTROL Segment Builder] 创建可批量工作表的规则。 但是，这不是这些工具的一组分步说明。 相反，我们将从一个已经创建的简单规则开始。 有关如何使用规则构建器的说明，请参 [阅区段构建器](../../features/segments/segment-builder.md) 和 [特征构建器](../../features/traits/about-trait-builder.md)。

利用可视规则构建器，我们创建了一个具有3个特征的区段规则和一个布尔运 [!UICONTROL AND] 算符。

![](assets/visualrule.png)

单 **[!UICONTROL Code View]** 击以获取此规则的文本版本。

>[!TIP]
>
>单击 **[!UICONTROL Validate Expression]** 以检查规则逻辑。 这将有助于防止您上传无效规则。

![](assets/coderule.png)

将规则粘贴到工作 [!UICONTROL Bulk Management Tools] 表中，并提交更改以批量更新区段规则。

![](assets/segmentrule.png)

## 创建您自己的规则 {#create-rules}

您可以在之外编写您自己的规则 [!UICONTROL Rule Builder]。 在开始之前，请务必阅读涵盖运算符、表达式和必需变量等内容的文档。 我们建议您查看以下内容：

* [在Trait Builder中使用比较运算符](../../features/traits/trait-comparison-operators.md)
* [操作顺序](../../features/traits/trait-operator-precedence.md)
* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)
* [具有布尔和比较运算符的示例表达式](../../features/traits/trait-expression-samples.md)

