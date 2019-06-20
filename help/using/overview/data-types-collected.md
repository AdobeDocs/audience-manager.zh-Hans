---
description: Audience Manager可帮助您收集和管理第一方、第二方和第三方数据。
seo-description: Audience Manager可帮助您收集和管理第一方、第二方和第三方数据。
seo-title: 收集的数据类型
solution: Audience Manager
title: 收集的数据类型
uuid: a2df470-32e6-41ec-a1 d7 d7-a6232 ef084 b9
translation-type: tm+mt
source-git-commit: f87a6f6c79a01c23608e4f5be24d017894e1c541

---


# Types of Data Collected{#types-of-data-collected}

Audience Manager可帮助您收集和管理第一方、第二方和第三方数据。

解锁存储在多个孤岛中的客户信息资产是当今公司面临的最大数据挑战之一。从CRM数据库到注册系统、到广告服务器，等等，公司需要帮助将宝贵数据集中化并管理客户/受众信息作为单一战略数据资产的工具。Audience Manager可帮助您解锁孤立的客户信息并管理来自多个来源的数据收集。收集的数据可以基于数据元素的实时(TTL)值进行管理，这有助于publisher控制所有来源的数据到期。Audience Manager旨在帮助您管理下列类型的数据：

| 数据类型 | 数据来源来源 |
|---|---|
| **第一方** | 客户. 数据是在线收集的(通过您的网站上的消费者交互)或离线收集。 |
| **第二方** | 战略合作伙伴和广告商。 |
| **第三方** | 数据提供商和/或交换。数据可以包括意图、人口统计、社交/生活方式、心理统计等信息。 |

## First-Party Data Collection {#first-party-data}

第一方数据收集是Audience Manager的主要功能。这一核心能力满足了我们的客户(出版商或广告商)的需求，他们希望将专有数据用作其营销计划的基石或针对其他数据源进行定位和建模。

<!-- 

c_1st_party_data.xml

 -->

Audience Manager与客户一起了解他们的数据战略，然后将该战略映射到自定义数据收集计划。我们的合作伙伴解决方案团队与您一起评估网站、原始数据信号和其他用户互动。通过此信息，我们将帮助您创建定制的数据收集策略，从库存中的各个页面捕获用户级数据信号。捕获的数据会存储并映射回预定义分类，在您的业务需求发生变化时可以随时更新。

以下示例说明了如何从示例购物页面捕获潜在数据元素。

![](assets/1st_party_800px.png)

收集原始数据后，它会被映射回Audience Manager平台内客户定义的特征。可以随时调整分类和数据映射，而无需更改数据收集代码。

## Second-Party Data Collection {#second-party-data}

第二方数据来自战略业务合作伙伴(不是publisher数据)。像第一方数据一样收集和管理此信息。

<!-- 

c_2nd_party_data.xml

 -->

在第二方数据方案中，广告商将自己的数据资产发送给出版商，以便将这些信息与publisher的数据相结合，然后执行更具针对性的广告计划。此外，出版商可以通过与广告商合作扩大受众池。在大多数情况下，这些安排涉及到合同关系仅限于将Audience Manager容器标签放入合作伙伴站点以促进数据收集和共享。

第二方数据收集和再营销的示例可能涉及一个汽车制造商，该制造商在其汽车配置页面上收集数据，然后与关键合作伙伴共享此信息。在这种情况下，汽车制造商可以为配置不同类型车辆选项(例如颜色、车型等)的消费者在Audience Manager合作伙伴站点上提供不同的广告。

![](assets/2nd_party_700px.png)

## Third-Party Data Collection {#third-party-data}

第三方数据是Audience Manager之外的供应商收集和共享的信息。

<!-- 

c_3rd_party_data.xml

 -->

第三方数据可用于确定现有数据细分(例如年龄、家庭收入等)，提供按需提供但不提供的数据，或用于根据第一方和第二方数据对照已知用户群进行相似度建模。Audience Manager与许多第三方数据提供商一起工作，并帮助您了解这些数据提供商收集的数据类型，以便您能够与每个提供商进行正确的战略交易。

>[!NOTE]
>
>For a full list of third-party data providers supported by [!DNL Audience Manager], see the [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

Audience Manager可根据其可用的API和数据集与其他数据提供商集成。数据收集实时工作，当用户浏览您的站点，或者通过带外方法在不同的服务器之间同步ID时，在用户离开站点后在服务器之间传输ID。无论是哪种情况，Audience Manager客户端都可以在我们的平台上同步第三方数据，这意味着每个客户端或域都不必执行自己的同步。这有助于提高范围并减少页面的服务器调用。

## Match Partners {#match-partners}

许多客户选择与第三方数据匹配合作伙伴合作。这些实体与具有注册要求的站点建立关系，并可以根据注册网络(实时)对客户数据文件进行匹配(实时)。

![](assets/data_provider_match_700px.png)

