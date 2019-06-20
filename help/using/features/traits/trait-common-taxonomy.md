---
description: 本文提供了有关使用常用分类分类特征的一般概述。
keywords: DIL
seo-description: 本文提供了有关使用常用分类分类特征的一般概述。
seo-title: 使用通用分类分类特征
solution: Audience Manager
title: 使用通用分类分类特征
uuid: 2e177344-07d9-40a7-8c99-c6 c6518 b9 d97
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# Classifying Traits with a Common Taxonomy {#classifying-traits-with-a-common-taxonomy}

本文提供了有关使用常用分类分类特征的一般概述。

## Audience Manager分类

<!-- c_common_taxonomy_about.xml -->

[!DNL Audience Manager] 分类是可选功能，使用统一、逻辑和常用的命名约定对特征分类。It operates at the platform level to help ensure naming consistency throughout the [!DNL Audience Manager] ecosystem. 总而言之，常用分类旨在使我们的产品更加符合有关消费者隐私和选择退出流程的行业标准。

## 特征分类的优势

Enabling our customers to build custom segments and data models is core to the [!DNL Audience Manager] model and to your ability to capture value from our platform. 但是，还需要强大的、可伸缩的方法来向客户和合作伙伴传达有关细分信息的信息。此外，此通信要求以易于理解和普遍理解的语言共享区段信息，同时保护专有特征和细分名称。[!DNL Audience Manager] 常用分类提供此语言和功能。

## 分类分类使用行业标准分类类别

The common taxonomy is based on the classifications created by the [!DNL Interactive Advertising Bureau (IAB)]. Refer to the [!DNL IAB]&#39;s [website](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) for more information about quality assurance guidelines for networks and exchanges.

## 分类组织

[!DNL Audience Manager] 分类将数据组织到称为层的嵌套类别中。每个类别最多可包含个单独的数据分类层。在最高级别，层类将数据分组到其最一般的表单中(例如地理位置)。Subsequent tiers provide greater specificity to the higher level, general category (e.g., *geography --&gt; United States --&gt; New York*). 但是，并非每个类别都有三层，部分只使用2。

## 分类数据类别中的特征

You assign taxonomic classifications when creating or editing traits in the [!UICONTROL Add New Trait Wizard] (located in * **[!UICONTROL Audience Data > Traits]***). Refer to the [documentation on creating traits](../../features/traits/create-onboarded-rule-based-traits.md) for more information.

## 使用分类法：其他注意事项

如果您根据我们常用分类决定分类特征，请记住：

* Classification is *optional*.
* Traits *are not* assigned to a taxonomic category by default (i.e., traits are not classified as &quot;unknown&quot; or &quot;uncategorized&quot; etc.).
* Traits can belong to *one* taxonomic category only (multiple and cross-category classifications are not allowed).