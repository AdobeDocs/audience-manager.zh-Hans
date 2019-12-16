---
description: 本文档介绍如何在Audience manager中管理客户数据。
seo-description: 本文档介绍如何在Audience manager中管理客户数据。
seo-title: 数据管理
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: 数据管理
translation-type: tm+mt
source-git-commit: 9004dc46c0ac431e9f193467a2147a2d9ac36cdc

---


# 数据管理

## 概述 {#overview}

Audience Manager中的数据管理是指Audience manager中客户数据的生命周期，它包含收集和模糊 [化IP地址](data-governance.md#collecting-ip-addresses)、 [数据保留](data-governance.md#data-retention)[和跨境数据传输](data-governance.md#data-transfers)。

## 收集IP地址和IP地址模糊化 {#collecting-ip-addresses}

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**** IP模糊化方法：Adobe Audience manager遵循“按设计保护隐私”的原则，允许客户在UI中实现模糊处理，无论是在全球所有地理区域还是针对特定国家／地区。 [!DNL IP] 启用此设置后，当将地址引入Audience manager中时，地址的最后八位字节( [!DNL IP] 最后一部分) [!DNL IP] 将立即被丢弃。 Audience manager在处理之前(包括 [!DNL IP] 在任何可选的地理查找或地址记录之前)放弃此部分地 [!DNL IP] 址。 例如：

* 在记录: `255.255.255.255`
* 之后: `255.255.255.0`

>[!NOTE]
>
>请参 [阅IP地址模糊化](../../features/administration/ip-obfuscation.md) ，了解如何在Audience Manager UI [!DNL IP] 中启用地址模糊化。

观看以下视频，了解地址模糊 [!DNL IP] 处理在Audience manager中的工作原理。

>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=chi_hans)

**** 地理细分：如果启用地 [!DNL IP] 址模糊处理，则地址的其余八位 [!DNL IP] 元仍可用于Audience manager中的地域划分和报告。 如果不启用地址模 [!DNL IP] 糊处理，则Audience manager将使用完整地 [!DNL IP] 址。 您可以使用“地理分段”功能，在任一情况下，该功能都允许您按地理区域来识别位置，但在使用模糊处理时，会稍有不 [!DNL IP][!DNL IP] 确定位置。 Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. 获取区域和国家一级的信息应仅受到轻微影响。 地理细分数据仅粒度级别为市级或邮政编码级别，而不粒度级别为个人级别。 阅读更多关 [于地理定位](../../features/traits/trait-geotarget-keys.md) ，以及如何使用地理变量设置特征。

## Audience manager中的数据保留 {#data-retention}

对数据应用适当、安全和及时的数据保留策略是遵守数据隐私法规的重要部分。 Audience Manager客户可以通过定义所需的TTL（生存时间），为特征和区段设置自定义保留期。 有关保 [留期的更多详细信息](../../faq/faq-privacy.md) ，请参阅数据保留常见问题解答。

## 跨边界数据传输 {#data-transfers}

当Audience manager跨国境传输客户的个人数据时，Audience manager会遵守适用法律。 请访问 [Adobe隐私中心](https://www.adobe.com/privacy/eudatatransfers.html) ，了解更多信息。