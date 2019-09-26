---
description: '使用基于人员的目标将第一方受众细分发送到基于人员的环境。 这些环境是属于一个实体的封闭生态系统，该实体控制其中显示的内容。 这些平台包括Facebook等社交平台，以及依赖客户帐户个性化显示内容的其他平台。 '
seo-description: '使用基于人员的目标将第一方受众细分发送到基于人员的环境。 这些环境是属于一个实体的封闭生态系统，该实体控制其中显示的内容。 这些平台包括Facebook等社交平台，以及依赖客户帐户个性化显示内容的其他平台。  '
seo-title: 基于人员的目标概述和使用案例
solution: Audience Manager
title: 概述和使用案例
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

---


# 概述和使用案例 {#overview-use-cases}

使用 [!DNL People-Based Destinations] 将第一方受众细分发送到基于人员的环境。 这些环境是属于一个实体的封闭生态系统，该实体控制其中显示的内容。 They include social platforms such as [!DNL Facebook], and other platforms that rely on customer accounts to personalize the displayed content.

## 概述 {#overview}

[!DNL People-Based Destinations] 使您能够对线上和线下数据应用细分，以根据哈希标识符(如 [电子邮件地址或电话号码](people-based-destinations-prerequisites.md#hashing-requirements))创建受众细分。 Then, you can send these segments to "walled gardens" such as , where you can target your audience on the social platforms. [!DNL Facebook][!DNL People-Based Destinations] can help you:

* Target offline and online audiences in platforms such as [!DNL Facebook], based on hashed email addresses;
* Complement existing device and cookie targeting capabilities of Audience Manager;
* Eliminate costs associated with third-party data onboarding solutions;
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

**Reach audiences in people-based channels without the need of a dedicated data onboarding solution or custom workflows to send audiences.**

The more "traditional" way of targeting audiences across people-based channels involves you having to export your customer data in a format accepted by the platform that you want to advertise on, and then using the platform's dedicated data onboarding method to bring your customer data to your advertiser account. This is all manual work that you need to do for each platform that you want to advertise on. Additionally, different platforms may have different data format requirements, making the process even more tedious.

![pbd-overview](assets/pbd-diagram.png)

通过 [!DNL People-Based Destinations]Audience Manager，您可以帮助您将客户数据集中化、构建受众细分，并在多个基于人员的渠道中激活它们。 您可以从Audience Manager UI中完成所有操作，避免手动将数据上传到每个平台的额外工作，从而节省了流程中的宝贵时间。

**从纯线下档案创建和激活受众细分。**

[!DNL People-Based Destinations] 解决以前只能根据设备活动激活受众细分的问题。 利用 [!DNL People-Based Destinations]这些功能，您可以根据自己的纯线下数据创建细分 [!DNL CRM]，并在基于人的平台中激活这些细分。 此外，您还可以将离线数据与Audience manager中已有的设备数据相关联。

**利用Audience manager的数据管理和隐私控制安全地处理客户数据。**

[!DNL People-Based Destinations] 要求您仅使用不可逆转的散列标识符。 这降低了将客户数据手动上传到每个目标平台的风险。

## 用例 {#use-cases}

为了帮助您更好地了解应如何使用和何时使用 [!DNL People-Based Destinations]，以下是Audience manager客户可以通过此功能解决的两个示例使用案例。

### Use Case #1 {#use-case-1}

一家在线零售商希望通过社交平台接触现有客户，并根据他们先前的订单向他们展示个性化的推广信息。 通过 [!DNL People-Based Destinations]此项服务，在线零售商可以将散列电子邮件地址从他们自己收集到 [!DNL CRM] Audience Manager中，根据他们自己的线下数据构建细分，并将这些细分发送到他们要投放广告的社交平台，从而优化他们的广告支出。

### Use Case #2 {#use-case-2}

航空公司有不同的客户层（铜牌、银牌和金牌），并希望通过社交平台为每层提供个性化的优惠。 公司使用Audience manager分析网站上的客户活动。 但是，并非所有客户都使用该航空公司的移动应用程序，其中一些客户尚未登录该公司的网站。 公司拥有的关于这些客户的唯一标识符是会员ID和电子邮件地址。

要跨社交媒体和类似的基于人员的渠道定位客户，他们可以将客户数据从他们的Audience Manager中载入，并使用哈希电子邮件地址作为标识符。 [!DNL CRM]

接下来，他们可以将线下数据与现有在线活动特征相结合，构建可以定位的新受众细分 [!DNL People-Based Destinations]。
