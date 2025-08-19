---
description: 使用基于人员的目标将第一方受众区段发送到基于人员的环境。 这些环境是属于一个实体的封闭生态系统，该实体控制其中显示的内容。 它们包括脸书等社交平台，以及其他依赖客户帐户来个性化显示内容的平台。
seo-description: Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content.
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: 概述和用例
feature: People-based Destinations
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: ab3361a0a54a7200d2f0c03a82ae6ef61a755be9
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 0%

---

# 概述和用例 {#overview-use-cases}

使用[!DNL People-Based Destinations]将第一方受众区段发送到基于人员的环境。 这些环境是属于一个实体的封闭生态系统，该实体控制其中显示的内容。 它们包括社交平台（如[!DNL Facebook]）和依赖客户帐户对显示内容进行个性化的其他平台。

>[!IMPORTANT]
>本文包含产品文档，旨在指导您完成此功能的设置和使用。 此处不包含任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

## 概述 {#overview}

[!DNL People-Based Destinations]允许您对在线和离线数据应用分段，以根据[哈希标识符](people-based-destinations-prerequisites.md#hashing-requirements)创建受众区段，如电子邮件地址。 然后，您可以将这些区段发送到“带墙的花园”，例如[!DNL Facebook]，您可以在社交平台上定位受众。 [!DNL People-Based Destinations]可以帮助您：

* 基于经过哈希处理的电子邮件地址在[!DNL Facebook]等平台中定位离线和在线受众；
* 补充Audience Manager的现有设备和Cookie定位功能；
* 消除与第三方数据载入解决方案相关的成本；
* 消除与开发自定义数据载入工作流相关的成本；
* 在无Cookie的环境中定位受众；
* 通过删除与客户ID匹配的经过哈希处理的电子邮件地址中的重复项来定位受众。

您可以使用[!DNL People-Based Destinations]对可能未访问您网站的高价值客户进行细分和定位，或停止对已离线转换的客户进行定位。 此外，您可以利用[!DNL Profile Merge Rules]将离线的第一方数据与在线的第一方数据(包括其他Adobe Experience Cloud解决方案中的客户数据)相结合，以优化您的社交媒体广告工作。

![pbd-overview](assets/pbd-overview.png)

## 可用性 {#availability}

[!DNL People-Based Destinations]是一个高级Audience Manager集成。 请联系您的Adobe代表以使用此高级功能。

## 为何要使用[!UICONTROL People-Based Destinations] {#why-use}

**通过在Audience Manager中管理整个受众分段，为客户提供一致的跨渠道体验。**

不通过Audience Manager在基于人员的渠道中激活您的受众区段，会导致您的客户在访问您的网站时看到的内容与他们在其[!DNL Facebook]源中看到的内容之间体验脱节。 跨渠道一致的定位可以增加广告收入，同时优化广告支出。

**无需专用数据载入解决方案或自定义工作流即可通过基于人员的渠道触及受众。**

在基于人员的渠道中定位受众的更加“传统”的方式是，您必须采用一种您想在广告上刊登的平台所接受的格式导出客户数据，然后使用该平台的专用数据载入方法将您的客户数据载入到广告商帐户。 这是您需要为每个要在广告中发布的平台执行的所有手动操作。 此外，不同的平台可能具有不同的数据格式要求，这使得该过程更加繁琐。

![pbd-overview](assets/pbd-diagram.png)

通过[!DNL People-Based Destinations]，Audience Manager可帮助您集中客户数据，构建受众区段，并在多个基于人员的渠道中激活这些数据。 您可以在Audience Manager用户界面中完成所有这些操作，避免手动将数据上传到每个平台这一额外工作，从而在此过程中节省您的宝贵时间。

**从纯脱机配置文件中创建和激活受众区段。**

[!DNL People-Based Destinations]解决了以前只能根据设备活动激活受众区段的问题。 通过[!DNL People-Based Destinations]，您可以根据自己[!DNL CRM]的纯离线数据创建区段，并在基于人员的平台上激活它们。 此外，您可以将离线数据与Audience Manager中已存在的设备数据相关联。

**利用Audience Manager的数据治理和隐私控制安全地处理客户数据。**

[!DNL People-Based Destinations]要求您仅使用不可逆散列标识符。 这降低了与手动将客户数据上传到每个目标平台相关的风险。

观看以下视频，了解使用[!UICONTROL People-Based Destinations]时的数据流概况。

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## 用例 {#use-cases}

为了帮助您更好地了解您应如何使用[!DNL People-Based Destinations]以及何时使用，以下是Audience Manager客户可以使用此功能解决的两个示例用例。

### 用例#1 {#use-case-1}

在线retailer希望通过社交平台与现有客户联系，并向他们显示基于先前订单的个性化优惠。 通过[!DNL People-Based Destinations]，在线retailer可以将经过哈希处理的电子邮件地址从自己的[!DNL CRM]摄取到Audience Manager，从自己的离线数据构建区段，并将这些区段发送到他们想要广告的社交平台，从而优化他们的广告支出。

### 用例#2 {#use-case-2}

航空公司有不同的客户层（青铜、银牌和金牌），并希望通过社交平台为每个层提供个性化优惠。 该公司使用Audience Manager来分析网站上的客户活动。 不过，并非所有客户都使用马航的移动应用，其中一些客户尚未登录该公司网站。 公司拥有的关于这些客户的唯一标识符是会员ID和电子邮件地址。

要通过社交媒体和类似的基于人员的渠道定位他们，他们可以使用经过哈希处理的电子邮件地址作为标识符，将客户数据从其[!DNL CRM]载入Audience Manager。

接下来，他们可以将其离线数据与现有的在线活动特征相结合，以构建可通过[!DNL People-Based Destinations]定位的新受众区段。
