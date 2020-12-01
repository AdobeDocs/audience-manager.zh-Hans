---
description: '使用基于人的目标将第一方受众细分发送给基于人的环境。 这些环境是属于控制其中显示的内容的实体的封闭生态系统。 这些平台包括Facebook等社交平台，以及依赖客户帐户个性化显示内容的其他平台。 '
seo-description: '使用基于人的目标将第一方受众细分发送给基于人的环境。 这些环境是属于控制其中显示的内容的实体的封闭生态系统。 这些平台包括Facebook等社交平台，以及依赖客户帐户个性化显示内容的其他平台。  '
seo-title: 基于人员的目标概述和使用案例
solution: Audience Manager
title: 概述和用例
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 1%

---


# 概述和用例 {#overview-use-cases}

使用[!DNL People-Based Destinations]将第一方受众细分发送给基于人员的环境。 这些环境是属于控制其中显示的内容的实体的封闭生态系统。 这些平台包括[!DNL Facebook]等社交平台，以及依赖客户帐户个性化显示内容的其他平台。

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

## 概述 {#overview}

[!DNL People-Based Destinations] 使您能够对线上和线下数据应用分段，以根据散列标识符( [如电子邮件地址](people-based-destinations-prerequisites.md#hashing-requirements)或电话号码)创建受众段。然后，您可以将这些细分发送到“带围墙的花园”，如[!DNL Facebook]，在那里您可以在社交平台上目标受众。 [!DNL People-Based Destinations] 可以帮助您：

* 目标离线和在线受众，在[!DNL Facebook]等平台中，基于散列化的电子邮件地址；
* 补充现有的设备和Audience Managercookie定位功能；
* 消除与第三方数据载入解决方案相关的成本；
* 消除开发定制工作流的相关成本；
* 目标受众无cookie环境;
* 目标受众，方法是消除与客户ID匹配的哈希电子邮件地址。

您可以使用[!DNL People-Based Destinations]细分和目标可能未访问过您网站的高价值客户，或停止定位已脱机转换的客户。 此外，您还可以利用[!DNL Profile Merge Rules]将线下第一方数据与在线第一方数据(包括来自Adobe Experience Cloud其他解决方案的客户数据)相结合，以优化您的社交媒体广告工作。

![pbd-overview](assets/pbd-overview.png)

## 可用性 {#availability}

[!DNL People-Based Destinations] 是高级Audience Manager集成。请联系您的Adobe代表以利用此高级功能。

## 为何应使用[!UICONTROL People-Based Destinations] {#why-use}

**通过从渠道内管理整个受众细分，为客户提供一致的跨Audience Manager体验。**

不通过Audience Manager在基于人的受众中激活您的渠道细分会导致客户在访问网站时看到的内容与他们在[!DNL Facebook]源中看到的内容之间脱节。 跨渠道实现一致的定位可在优化广告支出的同时增加广告收入。

**无需专用的数据入门解决方案或自定义受众发送渠道，即可触及基于人员的工作流中的受众。**

跨基于人员的受众定位渠道的更“传统”方式包括，您必须以平台接受的格式导出客户数据，然后使用平台专用的数据载入方法将客户数据载入广告商帐户。 这是您需要为每个要投放广告的平台执行的所有手动工作。 此外，不同的平台可能有不同的数据格式要求，这使得该过程更加繁琐。

![pbd-overview](assets/pbd-diagram.png)

通过[!DNL People-Based Destinations],Audience Manager可帮助您集中受众数据，构建细分，并在多个基于人的渠道中激活数据。 您可以从Audience Manager用户界面中完成所有操作，避免手动将数据上传到每个平台的额外工作，从而节省流程中的宝贵时间。

**从纯脱机受众创建和激活用户档案段。**

[!DNL People-Based Destinations] 解决以前只能根据设备受众激活活动段的问题。使用[!DNL People-Based Destinations]，您可以从您自己的[!DNL CRM]中的纯离线数据创建细分，并在基于人的平台中激活这些细分。 此外，您还可以将离线数据与已Audience Manager的设备数据关联。

**利用Audience Manager的数据治理和隐私控制来安全地处理客户数据。**

[!DNL People-Based Destinations] 要求您仅使用不可逆转的散列标识符。这降低了将客户数据手动上传到每个目标平台的风险。

观看以下视频，了解使用[!UICONTROL People-Based Destinations]时的数据流概述。

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## 用例 {#use-cases}

为了帮助您更好地了解如何使用[!DNL People-Based Destinations]以及何时应使用&lt;a0/>，以下是Audience Manager客户可通过使用此功能解决的两个示例使用案例。

### 用例#1 {#use-case-1}

一家在线零售商希望通过社交平台接触现有客户，并根据先前的订单向他们展示个性化的优惠。 在[!DNL People-Based Destinations]中，在线零售商可以将散列电子邮件地址从自己的[!DNL CRM]收录到Audience Manager，根据自己的线下数据构建细分，并将这些细分发送到他们想要投放的社交平台，从而优化其广告支出。

### 用例#2 {#use-case-2}

航空公司拥有不同的客户层（铜牌、银牌和金牌），希望通过社交平台为每层提供个性化优惠。 公司使用Audience Manager分析网站上的客户活动。 然而，并非所有客户都使用航空公司的移动应用程序，其中一些客户尚未登录公司网站。 公司有关这些客户的唯一标识符是会员ID和电子邮件地址。

要在社交媒体和类似的基于人的目标中进行渠道，他们可以将[!DNL CRM]的客户数据作为Audience Manager，使用散列电子邮件地址作为标识符。

接下来，他们可以将线下活动与现有在线受众特征相结合，构建可通过[!DNL People-Based Destinations]目标的新细分。
