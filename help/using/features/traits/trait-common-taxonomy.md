---
description: 本文概述了如何用通用分类对特征进行分类。
keywords: DIL
seo-description: 本文概述了如何用通用分类对特征进行分类。
seo-title: 使用通用分类法对特征进行分类
solution: Audience Manager
title: 使用通用分类法对特征进行分类
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 4%

---


# 使用通用分类法对特征进行分类 {#classifying-traits-with-a-common-taxonomy}

本文概述了如何用通用分类对特征进行分类。

## Audience Manager分类

<!-- c_common_taxonomy_about.xml -->

分类 [!DNL Audience Manager] 是一个可选功能，它使用统一、逻辑和常见的命名约定对特征进行分类。 它在平台级别运行，有助于确保整个生态系统中的命名一 [!DNL Audience Manager] 致性。 最终，通用分类法旨在使我们的产品与消费者隐私和选择退出流程的行业标准更加一致。

## 特征分类的优势

使我们的客户能够构建自定义细分和数据模型是模型 [!DNL Audience Manager] 和您从我们的平台获取价值的核心。 但是，还需要一种可靠且可扩展的方法来向客户和合作伙伴传达有关细分的信息。 此外，此通信要求以易于理解和普遍理解的语言共享细分信息，同时保护您的专有特征和细分名称。 通用 [!DNL Audience Manager] 分类提供此语言和功能。

## 分类法使用行业标准分类类别

通用分类基于由创建的分类 [!DNL Interactive Advertising Bureau (IAB)]。 有关网络和交 [!DNL IAB]换机质 [量保证指南](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) ，请参阅网站。

## 分类组织

分 [!DNL Audience Manager] 类将数据组织到称为层的嵌套类别中。 每个类别最多可包含3个单独的数据分类层。 在最高层，第1层类别将数据分组到其最一般的形式（如地理位置）。 后续各层对较高级别的一般类别(例如， *地理—>美国—>纽约*)提供更加专一性。 但是，并非每个类别都有3层，有些只使用2层。

## 在数据类别中对特征进行分类

在（位于**）中创建或编辑特征时 [!UICONTROL Add New Trait Wizard] 分配分类 **[!UICONTROL Audience Data > Traits]**&#x200B;分类。 有关详细信 [息，请参阅有关创建特](../../features/traits/create-onboarded-rule-based-traits.md) 征的文档。

## 使用分类： 其他注意事项

如果您决定根据我们的常见分类对特征进行分类，请务必记住：

* 分类是可 *选的*。
* 特 *征默认* 不分配给分类类别（即，特征未分类为“未知”或“未分类”等）。
* 特征只能属于 *一个分类类别* (不允许使用多个和跨类别分类)。