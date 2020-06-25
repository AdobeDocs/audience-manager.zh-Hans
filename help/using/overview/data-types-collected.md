---
description: Audience Manager 可帮助您收集和管理第一方、第二方和第三方数据。
seo-description: Audience Manager 可帮助您收集和管理第一方、第二方和第三方数据。
seo-title: 收集的数据类型
solution: Audience Manager
title: 收集的数据类型
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: overview
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 72%

---


# 收集的数据类型 {#types-of-data-collected}

[!DNL Audience Manager] 可帮助您收集和管理第一方、第二方和第三方数据。

解锁存储在多个数据仓库中的客户信息资产是当今许多公司面临的最大数据挑战之一。From [!DNL CRM] databases, to registration systems, to ad servers, and so forth, companies require tools that help centralize valuable data and manage customer/audience information as a single strategic data asset. [!DNL Audience Manager] 可帮助您解锁独立的客户信息并管理来自多个来源的数据收集。Collected data can be managed based on data element time-to-live ([!DNL TTL]) values, which helps the publisher control data expiration across all sources. [!DNL Audience Manager] 旨在帮助您管理以下类型的数据：

| 数据类型 | 数据来源 |
|---|---|
| **第一方** | 客户。数据是在线（从网站上的消费者交互中）或离线收集的。 |
| **第二方** | 战略合作伙伴和广告商。 |
| **第三方** | 数据提供商和/或交易台。数据可以包括意图、人口统计、社交/生活方式、心理统计等信息。 |

## 第一方数据收集 {#first-party-data}

First-party data collection is a main [!DNL Audience Manager] feature. 此核心能力可满足我们客户（出版商或广告商）的需求，这些客户希望将专有数据用作其营销项目的基石，或针对其他数据源进行定位和建模。

[!DNL Audience Manager] 可与客户一起了解他们的数据策略，然后将该策略反映到自定义数据收集计划。我们的合作伙伴解决方案团队可与您合作，共同评估网站、原始数据信号以及您网站上的其他用户交互。利用这些信息，我们将帮助您创建量身定制的数据收集策略，从库存的各个页面捕获用户级数据信号。捕获的数据会存储并映射回预定义的分类，随着业务需求的变化，该分类会随时更新。

以下示例说明如何从示例购物页面捕获潜在数据元素。

![shopping-cart-data](assets/shopping-cart-data.png)

| 项目 | 描述 |
|---|---|
| 1 | **性别**。购物者的名字通常表明其性别。在我们的示例中，购物者的名字是 Mary，因此我们知道购物者是一位女士。Audience Manager 从不会存储姓名。 |
| 2 | **兴趣**。购物车中的物品可能表明客户的各种兴趣。以我们的示例来说，Mary 在健身器材上花了很多钱。 |
| 3 | **住宅类型**。根据送货地址和/或帐单地址，您可以推断 Mary 是为自己还是为公司购买健身器材。 |
| 4 | **位置**。[!DNL ZIP] 代码比地址 [!DNL IP] 更可靠地指明位置。 |
| 5 | **促销相关性**。如果购物者使用促销代码或礼品卡，则表明他们可能是搜罗最便宜商品的折扣族。 |
| 6 | **消费能力**。Price data correlated with [!DNL ZIP+4] codes indicate spending power of a given location. |

After the raw data is collected, it gets mapped back to customer-defined traits within the [!DNL Audience Manager] platform. 可以随时调整分类和数据映射，而无需更改数据收集代码。

## 第二方数据收集 {#second-party-data}

第二方数据来自战略业务合作伙伴（它不是出版商数据）。这些信息的收集和管理与第一方数据相同。

在第二方数据场景中，广告商会向出版商发送自己的数据资产，以便将该信息与出版商的数据相结合，然后执行更具针对性的广告计划。此外，出版商可以与广告商合作，扩大其受众池。In most cases, these arrangements involve contractual relationships limited to putting the [!DNL Audience Manager] container tag on the partner site to facilitate data collection and sharing.

在第二方数据收集和再营销的示例中，服装零售商收集其产品的数据，然后与主要合作伙伴共享此信息。In this case, the retailed could serve different ads across an [!DNL Audience Manager] partner site for consumers who chose various jacket colors and sizes.

![](assets/shopping-cart-traits.png)

## 第三方数据收集 {#third-party-data}

Third-party data is information collected and shared by vendors outside of [!DNL Audience Manager].

Third-party data can be used to qualify existing data [!UICONTROL segments] (for example, age, household income, and so forth), provide data that is in demand but not otherwise available, or be used in lookalike modeling against a known user base from first-party and second-party data. [!DNL Audience Manager] 可与许多第三方数据提供商合作，帮助您了解这些数据提供商收集的数据类型，以便您能够与每个提供商达成正确的战略交易。

>[!NOTE]
>
>有关 [!DNL Audience Manager] 支持的第三方数据提供商的完整列表，请参阅 [Adobe 受众查找器](https://www.adobe-audience-finder.com/)。

[!DNL Audience Manager] 根据其他数据提供商的可用数据集 [!DNL APIs] 与其集成。 数据收集是在用户浏览您的网站时实时进行的，或者是通过带外方法进行的，在这些方法中，系统会在合作伙伴之间同步 ID，并且在用户离开您的网站后在服务器之间传输数据。In either case, [!DNL Audience Manager] clients get the benefit of having third-party data synchronized on our platform, which means each client, or domain, does not have to perform its own synchronization. 这有助于增加访问范围并减少页面中的服务器调用。

## 匹配合作伙伴 {#match-partners}

许多客户选择与第三方数据匹配合作伙伴合作。这些实体会与具有注册要求的网站建立关系，并可以根据其注册网络（实时）匹配客户数据文件来处理这些文件。

![data-provider-match](assets/data-provider-match.png)
