---
description: '使用基于人员的目标将第一方受众区段发送到基于人员的环境。 这些环境是属于一个实体的封闭生态系统，该实体控制其中显示的内容。 其中包括社交平台(如Facebook)，以及依赖客户帐户对显示内容进行个性化的其他平台。 '
seo-description: '使用基于人员的目标将第一方受众区段发送到基于人员的环境。 这些环境是属于一个实体的封闭生态系统，该实体控制其中显示的内容。 其中包括社交平台(如Facebook)，以及依赖客户帐户对显示内容进行个性化的其他平台。  '
seo-title: 基于人员的目标概述和用例
solution: Audience Manager
title: 概述和用例
feature: 基于人员的目标
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 1%

---

# 概述和用例 {#overview-use-cases}

使用[!DNL People-Based Destinations]将第一方受众区段发送到基于人员的环境。 这些环境是属于一个实体的封闭生态系统，该实体控制其中显示的内容。 这些平台包括诸如[!DNL Facebook]之类的社交平台，以及依赖客户帐户个性化显示内容的其他平台。

>[!IMPORTANT]
>本文包含旨在指导您完成此功能的设置和使用的产品文档。 这里没有任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

## 概述 {#overview}

[!DNL People-Based Destinations] 允许您对线上和线下数据应用分段，以根据经过哈希处理的标识符(如 [电子邮件地址或电话号码)](people-based-destinations-prerequisites.md#hashing-requirements)创建受众区段。然后，您可以将这些区段发送到“带墙的花园”，例如[!DNL Facebook]，以便在社交平台上定位受众。 [!DNL People-Based Destinations] 可以帮助您：

* 在诸如[!DNL Facebook]的平台中根据经过哈希处理的电子邮件地址定位离线和在线受众；
* 补充现有的设备和Cookie定位Audience Manager功能；
* 消除与第三方数据载入解决方案相关的成本；
* 消除与开发自定义数据载入工作流程相关的成本；
* 在无Cookie环境中定位受众；
* 通过删除与客户ID匹配的经过哈希处理的电子邮件地址，来定位受众。

您可以使用[!DNL People-Based Destinations]对可能未访问您网站的高价值客户进行细分和定位，或停止定位已离线转换的客户。 此外，您还可以利用[!DNL Profile Merge Rules]将离线第一方数据与在线第一方数据(包括来自其他Adobe Experience Cloud解决方案的客户数据)合并，以优化社交媒体广告工作。

![pbd-overview](assets/pbd-overview.png)

## 可用性 {#availability}

[!DNL People-Based Destinations] 是一个高级Audience Manager集成。请联系您的Adobe代表以利用此高级功能。

## 为什么应使用[!UICONTROL People-Based Destinations] {#why-use}

**通过从Audience Manager中管理整个受众区段，为客户提供一致的跨渠道体验。**

不通过Audience Manager在基于人员的渠道中激活受众区段，会导致客户访问网站时看到的内容与他们在[!DNL Facebook]馈送中看到的内容（例如）之间的体验不相连。 跨渠道实现一致的定位可以在优化广告支出的同时增加广告收入。

**在基于人员的渠道中访问受众，而无需专门的数据载入解决方案或自定义工作流来发送受众。**

在基于人员的渠道中定位受众的更“传统”方式是，您必须以平台接受的要投放广告的格式导出客户数据，然后使用平台的专用数据载入方法将客户数据载入到广告商帐户。 这是您需要为每个要投放广告的平台执行的所有手动操作。 此外，不同的平台可能有不同的数据格式要求，使过程更加繁琐。

![pbd-overview](assets/pbd-diagram.png)

通过[!DNL People-Based Destinations],Audience Manager可帮助您将客户数据集中化、构建受众区段，并在多个基于人员的渠道中激活它们。 您可以在Audience Manager用户界面中执行所有操作，从而避免手动将数据上载到每个平台的额外工作，从而节省流程中的宝贵时间。

**从纯离线配置文件创建和激活受众区段。**

[!DNL People-Based Destinations] 解决以前，您只能根据设备活动激活受众区段的问题。借助[!DNL People-Based Destinations]，您可以从自己的[!DNL CRM]中从纯离线数据创建区段，并在基于人员的平台中激活它们。 此外，您还可以将离线数据与您已在Audience Manager中的设备数据关联。

**利用Audience Manager的数据管理和隐私控制来安全地处理客户数据。**

[!DNL People-Based Destinations] 要求您仅使用不可逆转的哈希标识符。这降低了将客户数据手动上传到每个目标平台的相关风险。

观看以下视频，了解使用[!UICONTROL People-Based Destinations]时的数据流概况。

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## 用例 {#use-cases}

为了帮助您更好地了解应如何使用[!DNL People-Based Destinations]以及何时使用，以下是Audience Manager客户可以使用此功能解决的两个示例用例。

### 用例#1 {#use-case-1}

一家在线零售商希望通过社交平台与现有客户联系，并根据其先前的订单向他们显示个性化优惠。 借助[!DNL People-Based Destinations]，在线零售商可以将经过哈希处理的电子邮件地址从自己的[!DNL CRM]摄取到Audience Manager，从自己的离线数据构建区段，并将这些区段发送到他们要投放广告的社交平台，优化其广告支出。

### 用例#2 {#use-case-2}

一家航空公司拥有不同的客户层（Bronze、Silver和Gold），并希望通过社交平台为每个层提供个性化优惠。 公司使用Audience Manager分析网站上的客户活动。 但是，并非所有客户都使用航空公司的移动设备应用程序，其中一些客户尚未登录到公司网站。 公司关于这些客户的唯一标识符是会员ID和电子邮件地址。

要在社交媒体和类似的基于人员的渠道中定位客户，他们可以将[!DNL CRM]中的客户数据载入Audience Manager，并使用经过哈希处理的电子邮件地址作为标识符。

接下来，他们可以将离线数据与现有在线活动特征相结合，构建可通过[!DNL People-Based Destinations]定位的新受众区段。
