---
description: '使用基于人员的目标将第一方受众细分发送到基于人员的环境。 这些环境是属于一个实体的封闭生态系统，该实体控制其中显示的内容。 这些平台包括Facebook等社交平台，以及依赖客户帐户个性化显示内容的其他平台。 '
seo-description: '使用基于人员的目标将第一方受众细分发送到基于人员的环境。 这些环境是属于一个实体的封闭生态系统，该实体控制其中显示的内容。 这些平台包括Facebook等社交平台，以及依赖客户帐户个性化显示内容的其他平台。  '
seo-title: 基于人员的目标概述和使用案例
solution: Audience Manager
title: 概述和使用案例
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# 概述和使用案例 {#overview-use-cases}

使用 [!DNL People-Based Destinations] 将第一方受众细分发送到基于人员的环境。 这些环境是属于一个实体的封闭生态系统，该实体控制其中显示的内容。 这些平台包括社交平台(如 [!DNL Facebook]社交平台)和其他依赖客户帐户个性化显示内容的平台。

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

## 概述 {#overview}

[!DNL People-Based Destinations] 使您能够对线上和线下数据应用细分，以根据哈希标识符(如 [电子邮件地址或电话号码](people-based-destinations-prerequisites.md#hashing-requirements))创建受众细分。 然后，您可以将这些细分发送到“围墙花园”, [!DNL Facebook]例如，在社交平台上定位受众。 [!DNL People-Based Destinations] 可以帮助您：

* 根据经过散列处理的电子邮件地址，在平台 [!DNL Facebook]中定位线下和在线受众；
* 补充Audience manager的现有设备和cookie定位功能；
* 消除与第三方数据入门解决方案相关的成本；
* 消除与开发定制化数据载入工作流程相关的成本；
* 在无Cookie的环境中定位受众；
* 通过删除与客户ID匹配的重复电子邮件地址来定位受众。

您可以使用 [!DNL People-Based Destinations] 来细分和定位可能未访问过您网站的高价值客户，或停止定位已脱机转换的客户。 此外，您还可 [!DNL Profile Merge Rules] 以利用线下第一方数据与在线第一方数据（包括来自其他Adobe Experience cloud解决方案的客户数据）相结合，优化您的社交媒体广告工作。

![pbd-overview](assets/pbd-overview.png)

## Availability {#availability}

[!DNL People-Based Destinations] 是高级Audience manager集成。 请联系Adobe代表以利用此高级功能。

## 为何应使用基于人员的目标 {#why-use}

**通过从Audience manager中管理整个受众细分，为客户提供一致的跨渠道体验。**

不通过Audience manager在基于人员的渠道中激活受众细分会导致客户在访问网站时看到的内容与他们在源中看到的内容之间脱节的体 [!DNL Facebook] 验。 跨渠道实现一致的定位可以在优化广告支出的同时增加广告收入。

**无需专用的数据入门解决方案或自定义工作流程即可向受众发送信息，即可触及基于人员的渠道中的受众。**

跨基于人的渠道定位受众的更“传统”的方式包括您必须以平台接受的格式导出客户数据，然后使用平台专用的数据载入方法将客户数据引入广告商帐户。 这是您需要为每个要投放广告的平台完成的所有手动工作。 此外，不同的平台可能有不同的数据格式要求，这使得该过程更加繁琐。

![pbd-overview](assets/pbd-diagram.png)

通过 [!DNL People-Based Destinations]Audience Manager，您可以帮助您将客户数据集中化、构建受众细分，并在多个基于人员的渠道中激活它们。 您可以从Audience Manager UI中完成所有操作，避免手动将数据上传到每个平台的额外工作，从而节省了流程中的宝贵时间。

**从纯线下档案创建和激活受众细分。**

[!DNL People-Based Destinations] 解决以前只能根据设备活动激活受众细分的问题。 利用 [!DNL People-Based Destinations]这些功能，您可以根据自己的纯线下数据创建细分 [!DNL CRM]，并在基于人的平台中激活这些细分。 此外，您还可以将离线数据与Audience manager中已有的设备数据相关联。

**利用Audience manager的数据管理和隐私控制安全地处理客户数据。**

[!DNL People-Based Destinations] 要求您仅使用不可逆转的散列标识符。 这降低了将客户数据手动上传到每个目标平台的风险。

观看以下视频，了解使用时的数据流概述 [!UICONTROL People-Based Destinations]。

>[!VIDEO](https://video.tv.adobe.com/v/28968/?captions=chi_hans)

## 用例 {#use-cases}

为了帮助您更好地了解应如何使用和何时使用 [!DNL People-Based Destinations]，以下是Audience manager客户可以通过此功能解决的两个示例使用案例。

### Use Case #1 {#use-case-1}

一家在线零售商希望通过社交平台接触现有客户，并根据他们先前的订单向他们展示个性化的推广信息。 通过 [!DNL People-Based Destinations]此项服务，在线零售商可以将散列电子邮件地址从他们自己收集到 [!DNL CRM] Audience Manager中，根据他们自己的线下数据构建细分，并将这些细分发送到他们要投放广告的社交平台，从而优化他们的广告支出。

### Use Case #2 {#use-case-2}

航空公司有不同的客户层（铜牌、银牌和金牌），并希望通过社交平台为每层提供个性化的优惠。 公司使用Audience manager分析网站上的客户活动。 但是，并非所有客户都使用该航空公司的移动应用程序，其中一些客户尚未登录该公司的网站。 公司拥有的关于这些客户的唯一标识符是会员ID和电子邮件地址。

要跨社交媒体和类似的基于人员的渠道定位客户，他们可以将客户数据从他们的Audience Manager中载入，并使用哈希电子邮件地址作为标识符。 [!DNL CRM]

接下来，他们可以将线下数据与现有在线活动特征相结合，构建可以定位的新受众细分 [!DNL People-Based Destinations]。
