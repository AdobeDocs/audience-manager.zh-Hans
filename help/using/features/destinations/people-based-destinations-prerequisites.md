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
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

请阅读以下内容，了解注册前需要满足的客户要求的概述 [!DNL People-Based Destinations]。

>[!IMPORTANT]
> 在进入实施阶段之前，请仔细阅读本文。

## Signing up for People-Based Destinations {#signing-up}

[!DNL People-Based Destinations] is a premium capability that enhances your Audience Manager experience by allowing you to activate your first-party audience segments in people-based environments, by targeting your audience with customized offers on social networks or through email marketing.

请联系Adobe代表以利用此高级功能。

## 特定于合作伙伴的先决条件 {#partner-prerequisites}

### [!DNL Facebook]

在使用将第 [!DNL People-Based Destinations] 一方受众细分发送到之前，请确保 [!DNL Facebook]满足以下要求：

1. 您 [!DNL Facebook] 的用户帐户必须为您计划使用 **的广告帐户启用** “管理营销活动”权限。
1. Add the **Adobe Experience Cloud** business account as an advertising partner in your [!DNL Facebook Ad Account]. 使用 `business ID=206617933627973`. See Add Partners to Your Business Manager for details.[](https://www.facebook.com/business/help/708679622611131)
   >[!IMPORTANT]
   > When configuring the permissions for Adobe Experience Cloud, you must enable the Manage campaigns permission. **** This is required for the  integration.[!DNL People-Based Destinations]
1. Read and sign the  Terms of Service. [!DNL Facebook Custom Audiences]为此，请转到 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`您的 `accountID` 位置 [!DNL Facebook Ad Account ID]。

## 数据入门 {#data-onboarding}

当前的数据 [!DNL People-Based Destinations] 摄取支持每批传输最多10个与一个客户ID()关联的哈希电子邮件地址[!DNL CRM ID]。 上传10个以上链接到一个客户ID的哈希电子邮件地址会导致Audience manager以无特定顺序收录其中10个。

在多次批量传输中上传10个以上链接到一个客户ID的哈希化电子邮件地址会导致Audience manager保留最近添加的10个电子邮件地址。

## 数据隐私{#data-privacy}

尽管 [!DNL People-Based Destinations] 允许您根据您上传的哈希电子邮件地址定位受众，但仍禁止您将任何直接可识别的访客信息上传到Audience Manager。 In the data onboarding phase, you must ensure that the email addresses you plan to use are hashed with the  algorithm. [!DNL SHA256]否则，您将无法在中使用它们 [!DNL People-Based Destinations]。

## 数据哈希与加密 {#data-hashing-encryption}

加密是双向功能。 任何加密的信息也可以使用正确的解密密钥被解密。 在Audience manager环境中加密数据会带来严重风险，因为任何加密形式的个人识别信息也可以解密。 与加密相比，它 [!DNL People-Based Destinations] 们设计为处理散列数据。

Hashing is a one-way function that scrambles the input to produce a unique result. By using proper hashing algorithms, like , there is no way to reverse the hashing function and reveal the unscrambled information. [!DNL SHA256]您将上传到Audience Manager的电子邮件地址必须使用算法进行哈希 [!DNL SHA256] 处理。 这样，您就可以确保Audience manager不会收到经过散列处理的电子邮件地址。

## 散列要求 {#hashing-requirements}

散列电子邮件地址时，请确保符合以下要求：

* Trim all leading and trailing spaces from the email string; example: , not ;`johndoe@example.com``<space>johndoe@example.com<space>`
* 对电子邮件字符串进行哈希处理时，请确保对小写字符串进行哈希处理；
   * 示例： `example@email.com`不是 `EXAMPLE@EMAIL.COM`;
* Make sure the hashed string is all lowercase
   * 示例： , not ;`55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149``55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`
* Do not salt the string.

Adobe Experience Cloud可让您选择通过Experience Cloud ID服务散列客户ID。 See SHA256 Hashing Support for setCustomerIDs for detailed information on how to use ECID to hash customer IDs.[](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html)

## 获取用户权限 {#obtaining-user-permission}

Since  helps you activate first-party audience data in people-based channels, it is your responsibility to inform and obtain any necessary consents from your customers of how you will use their data for advertising or other purposes.[!DNL People-Based Destinations]

在注册前，请确 [!DNL People-Based Destinations]保在将客户的信息用于广告之前获得客户的同意。

如果客户希望退出广告营销活动，请参阅退出管理 [](../../overview/data-security-and-privacy/opt-out-management.md) ，了解有关如何阻止Audience manager进一步收集数据的详细信息。

## 实施第一方数据激活 {#enforcing-first-party-activation}

使用时， [!DNL People-Based Destinations]您只能使用第一方数据在基于人员的渠道中激活受众细分。 您不能使用任何第二方或第三方数据在基于人员的渠道中激活受众。

## Onboard Authenticated Hashed IDs through Declared ID Targeting {#onboard-authenticated-declared-id}

有两种方法可将离线数据导入Audience Manager [!DNL People-Based Destinations]。

* [将批量数据发送](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 到Audience Manager，以摄取散列化的电子邮件地址。 使用此方法，您可以选择使用中数据库中经过哈希处理的电子 [!DNL CRM] 邮件地址 [!DNL People-Based Destinations]。 此外，使用此方法时，您还可以为已载入的特征限定哈希化电子邮件 [地址](../traits/trait-qualification-reference.md)。
* 在传 [入经身份验证的客户ID时](../declared-ids.md) ，使用Declared ID声明散列化的电子邮件地址。 使用此方法时，Audience manager将代表您仅向通过在线身份验证的 [!DNL People-Based Destinations] 用户发送哈希电子邮件地址。 通过基于人员的渠道激活的电子邮件地址只是声明的ID事件调用中的电子邮件地址。 Other email addresses associated with the customer ID are not sent in real-time.
