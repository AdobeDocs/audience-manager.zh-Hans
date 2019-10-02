---
description: '阅读以下内容，了解注册基于人员的目标之前需要满足的客户要求。  '
seo-description: '阅读以下内容，了解注册基于人员的目标之前需要满足的客户要求。  '
seo-title: 基于人员的目标先决条件和注意事项
solution: Audience Manager
title: 先决条件和注意事项
translation-type: tm+mt
source-git-commit: ad9c077f538759e195a83d47e0ef36ccffa25c7e

---


# 先决条件和注意事项 {#prerequisites-considerations}

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 Nothing contained herein is legal advice. 请咨询您自己的法律顾问以获得法律指导。

请阅读以下内容，了解注册前需要满足的客户要求的概述 [!DNL People-Based Destinations]。

>[!IMPORTANT]
> 在进入实施阶段之前，请仔细阅读本文。

## Signing up for People-Based Destinations {#signing-up}

[!DNL People-Based Destinations] 是一项高级功能，它允许您在基于人的环境中激活第一方受众细分，通过社交网络或电子邮件营销定制受众，从而增强Audience Manager体验。

请联系Adobe代表以利用此高级功能。

## 特定于合作伙伴的先决条件 {#partner-prerequisites}

### [!DNL Facebook]

在使用将第 [!DNL People-Based Destinations] 一方受众细分发送到之前，请确保 [!DNL Facebook]满足以下要求：

1. 您 [!DNL Facebook] 的用户帐户必须为您计划使用 **的广告帐户启用** “管理营销活动”权限。
1. 将 **Adobe Experience cloud商业帐户添加为广告合作伙伴**[!DNL Facebook Ad Account]。 使用 `business ID=206617933627973`. 有关详 [细信息，请参阅将合作伙伴添加到您的业务经理](https://www.facebook.com/business/help/708679622611131) 。
   >[!IMPORTANT]
   > 配置Adobe Experience cloud的权限时，必须启用“管理营销活 **动”权** 限。 这是集成所必需的 [!DNL People-Based Destinations] 选项。
1. 阅读并签署 [!DNL Facebook Custom Audiences] 服务条款。 为此，请转到 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`您的 `accountID` 位置 [!DNL Facebook Ad Account ID]。

## 数据入门 {#data-onboarding}

当前的数据 [!DNL People-Based Destinations] 摄取支持每批传输最多10个与一个客户ID()关联的哈希电子邮件地址[!DNL CRM ID]。 上传10个以上链接到一个客户ID的哈希电子邮件地址会导致Audience manager以无特定顺序收录其中10个。

在多次批量传输中上传10个以上链接到一个客户ID的哈希化电子邮件地址会导致Audience manager保留最近添加的10个电子邮件地址。

## 数据隐私{#data-privacy}

尽管 [!DNL People-Based Destinations] 允许您根据您上传的哈希电子邮件地址定位受众，但仍禁止您将任何直接可识别的访客信息上传到Audience Manager。 在数据入门阶段，您必须确保您计划使用的电子邮件地址已使用算法进行哈希 [!DNL SHA256] 处理。 否则，您将无法在中使用它们 [!DNL People-Based Destinations]。

## 数据哈希与加密 {#data-hashing-encryption}

Encryption is a two-way function. 任何加密的信息也可以使用正确的解密密钥被解密。 在Audience manager环境中加密数据会带来严重风险，因为任何加密形式的个人识别信息也可以解密。 As opposed to encryption, [!DNL People-Based Destinations] are designed to work with hashed data instead.

Hashing is a one-way function that scrambles the input to produce a unique result. By using proper hashing algorithms, like [!DNL SHA256], there is no way to reverse the hashing function and reveal the unscrambled information. The email addresses that you will onboard to Audience Manager must be hashed with the  algorithm. [!DNL SHA256]This way, you can ensure that no unhashed email addresses reach Audience Manager.

## Hashing Requirements {#hashing-requirements}

When hashing the email addresses, make sure to comply with the following requirements:

* Trim all leading and trailing spaces from the email string; example: , not ;`johndoe@example.com``<space>johndoe@example.com<space>`
* When hashing the email strings, make sure to hash the lowercase string;
   * 示例： , not ;`example@email.com``EXAMPLE@EMAIL.COM`
* Make sure the hashed string is all lowercase
   * 示例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`不是 `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Do not salt the string.

Adobe Experience Cloud可让您选择通过Experience Cloud ID服务散列客户ID。 有关如 [何使用ECID对客户ID进行哈希处理的详细信息，请参阅针对setCustomerID的SHA256哈希支持](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) 。

## 获取用户权限 {#obtaining-user-permission}

由于 [!DNL People-Based Destinations] 可帮助您在基于人的渠道中激活第一方受众数据，因此您有责任告知客户如何将其数据用于广告或其他用途，并从客户那里获得必要的同意。

在注册前，请确 [!DNL People-Based Destinations]保在将客户的信息用于广告之前获得客户的同意。

In case your customers wish to opt-out of advertising campaigns, see Opt-out Management for details on how to stop Audience Manager from collecting data any further.[](../../overview/data-security-and-privacy/opt-out-management.md)

## 实施第一方数据激活 {#enforcing-first-party-activation}

使用时， [!DNL People-Based Destinations]您只能使用第一方数据在基于人员的渠道中激活受众细分。 您不能使用任何第二方或第三方数据在基于人员的渠道中激活受众。

## Onboard Authenticated Hashed IDs through Declared ID Targeting {#onboard-authenticated-declared-id}

有两种方法可将离线数据导入Audience Manager [!DNL People-Based Destinations]。

* [将批量数据发送](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 到Audience Manager，以摄取散列化的电子邮件地址。 使用此方法，您可以选择使用中数据库中经过哈希处理的电子 [!DNL CRM] 邮件地址 [!DNL People-Based Destinations]。 此外，使用此方法时，您还可以为已载入的特征限定哈希化电子邮件 [地址](../traits/trait-qualification-reference.md)。
* 在传 [入经身份验证的客户ID时](../declared-ids.md) ，使用Declared ID声明散列化的电子邮件地址。 使用此方法时，Audience manager将代表您仅向通过在线身份验证的 [!DNL People-Based Destinations] 用户发送哈希电子邮件地址。 通过基于人员的渠道激活的电子邮件地址只是声明的ID事件调用中的电子邮件地址。 与客户ID关联的其他电子邮件地址不会实时发送。
