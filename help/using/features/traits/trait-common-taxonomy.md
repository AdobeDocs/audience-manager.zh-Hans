---
description: 本文提供了有关使用通用分类法对特征进行分类的一般概述。
keywords: DIL
seo-description: This article provides general overview about classifying traits with a common taxonomy.
seo-title: Classifying Traits with a Common Taxonomy
solution: Audience Manager
title: 使用通用分类法对特征进行分类
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# 使用通用分类法对特征进行分类 {#classifying-traits-with-a-common-taxonomy}

本文提供了有关使用通用分类法对特征进行分类的一般概述。

## Audience Manager分类

<!-- c_common_taxonomy_about.xml -->

[!DNL Audience Manager]分类法是一项可选功能，它使用统一、逻辑和常见命名约定对特征进行分类。 它在平台级别运行，以帮助确保整个[!DNL Audience Manager]生态系统的命名一致性。 最终，通用分类法旨在使我们的产品在消费者隐私和选择退出流程方面更好地与行业标准保持一致。

## 特征分类的优势

支持我们的客户构建自定义区段和数据模型是[!DNL Audience Manager]模型和您从我们的平台获取价值能力的核心。 但是，还需要一种强大且可扩展的手段来将有关区段的信息传达给客户和合作伙伴。 此外，该通信要求以易于理解和普遍理解的语言共享区段信息，同时保护您的专有特征和区段名称。 [!DNL Audience Manager]通用分类提供了此语言和功能。

## 分类法使用行业标准分类类别

通用分类基于[!DNL Interactive Advertising Bureau (IAB)]创建的分类。 有关网络和交换质量保证准则的更多信息，请参阅[!DNL IAB]的[网站](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines)。

## 分类组织

[!DNL Audience Manager]分类将数据组织到称为层的嵌套类别中。 每个类别最多可包含3个单独的数据分类层。 在最高级别，第1层类别将数据分组为其最通用的形式（例如，地理位置）。 后续层为更高级别的普通类别提供了更大的特殊性（例如，*地理位置 — >美国 — >纽约*）。 但是，并非每个类别都有3个层，有些仅使用2个。

## 对数据类别中的特征进行分类

在[!UICONTROL Add New Trait Wizard]（位于* **[!UICONTROL Audience Data > Traits]***）中创建或编辑特征时，分配分类分类。 有关详细信息，请参阅有关创建特征[&#128279;](../../features/traits/create-onboarded-rule-based-traits.md)的文档。

## 使用分类：其他注意事项

如果您决定根据我们通用的分类法对特征进行分类，请务必记住：

* 分类为&#x200B;*可选*。
* 默认情况下，特征&#x200B;*未分配给分类类别*（即，特征未分类为“未知”或“未分类”等）。
* 特征只能属于&#x200B;*one*&#x200B;分类类别（不允许使用多个和跨类别分类）。
