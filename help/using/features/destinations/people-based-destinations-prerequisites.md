---
description: '阅读下面的内容，了解在注册基于人员的目标之前需要满足的客户要求。  '
seo-description: '阅读下面的内容，了解在注册基于人员的目标之前需要满足的客户要求。  '
seo-title: 基于人员的目标先决条件和注意事项
solution: Audience Manager
title: 先决条件和注意事项
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# 先决条件和注意事项 {#prerequisites-considerations}

阅读下面的内容，了解在注册之前需要满足的客户要求 [!DNL People-Based Destinations]。

>[!IMPORTANT]
> 仔细阅读本文，然后转到实施阶段。

## 注册基于人员的目标 {#signing-up}

[!DNL People-Based Destinations] 是一项高级功能，可让您通过在社交网络上或通过电子邮件营销定位受众，从而在基于人群的环境中激活第一方受众细分，从而增强Audience Manager体验。

有关如何注册的详细信息，请与Adobe销售代表联系 [!DNL People-Based Destinations]。

## 合作伙伴特定的先决条件 {#partner-prerequisites}

### [!DNL Facebook]

在使用 [!DNL People-Based Destinations] 受众细分发送受众 [!DNL Facebook]之前，请确保满足以下要求：

1. [!DNL Facebook] 您的用户帐户必须为您计划使用的广告帐户启用 **“管理营销活动** ”权限。
1. 将 **Adobe Experience Cloud** 业务帐户添加为您 [!DNL Facebook Ad Account]的广告合作伙伴。使用 `business ID=206617933627973`. 有关详细信息，请参阅 [向您的业务经理](https://www.facebook.com/business/help/708679622611131) 添加合作伙伴。
   >[!IMPORTANT]
   > 在配置Adobe Experience Cloud的权限时，您必须启用 **“管理营销活动** ”权限。这是 [!DNL People-Based Destinations] 集成所必需的。
1. 阅读并签署服务 [!DNL Facebook Custom Audiences] 条款。要执行此操作，请 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`转到 `accountID`[!DNL Facebook Ad Account ID]您的位置。

## 数据适职 {#data-onboarding}

目前，数据摄取 [!DNL People-Based Destinations] 最多可支持10个将链接到一个客户ID([!DNL CRM ID])的电子邮件地址(每个批量传输)。上传链接到一个客户ID的10个以上的哈希电子邮件地址会导致Audience Manager以无特定顺序收录10个用户。

在多次批量传输中上传链接到一个客户ID的超过10个散列电子邮件地址会导致Audience Manager保留最近添加的10个电子邮件地址。

## 数据隐私{#data-privacy}

尽管 [!DNL People-Based Destinations] 允许您根据电子邮件地址定位受众，但不可直接识别访客信息到达Audience Manager。在数据入门阶段，您必须确保使用算法 [!DNL SHA256] 将计划使用的电子邮件地址散列化。否则 [!DNL People-Based Destinations]，您将无法使用它们。

## 数据散列与加密 {#data-hashing-encryption}

加密是双向函数。任何加密信息都可以使用正确的解密密钥进行解密。在Audience Manager环境中加密数据会带来严重的隐私风险，因为任何加密形式的个人识别信息也可以被解密，从而显示敏感的客户数据。与加密相反， [!DNL People-Based Destinations] 设计用于处理散列数据，从而保护您用于定位的客户数据。

哈希是一个单向函数，它打乱输入以产生独特的结果。通过使用适当的哈希算法，如 [!DNL SHA256]无法颠倒散列函数并显示杂乱的信息。必须使用算法 [!DNL SHA256] 将您登录Audience Manager的电子邮件地址散列化。这样，任何个人识别信息都不会触及Audience Manager，从而保证了您的客户数据安全。

## 散列要求 {#hashing-requirements}

散列电子邮件地址时，请确保符合以下要求：

* 从电子邮件字符串中修剪所有前导和尾部空格；示例： `johndoe@example.com``<space>johndoe@example.com<space>`而不是；
* 确保散列字符串全部小写；示例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149``55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`而不是；
* 请勿更改字符串。

Adobe Experience Cloud可让您通过Experience Cloud ID服务选择散列客户ID。有关如何使用EID以散列客户ID的详细信息，请参阅 [SHA256散列支持setCustomerID](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) 。

## 获取用户权限 {#obtaining-user-permission}

由于 [!DNL People-Based Destinations] 帮助您在基于人群的渠道中激活第一方受众数据，您有责任向客户通知如何将其数据用于广告用途。

注册之前，请 [!DNL People-Based Destinations]确保在使用其信息进行广告用途之前获得客户的同意。

如果客户希望选择退出广告活动，请参阅 [选择退出管理](../../overview/data-security-and-privacy/opt-out-management.md) 以了解如何阻止Audience Manager进一步收集数据。

## 强制第一方数据激活 {#enforcing-first-party-activation}

使用 [!DNL People-Based Destinations]时，您只能使用第一方数据在基于人群的渠道中激活受众细分。您不能在基于人群的渠道中使用任何第二方或第三方数据进行受众激活。

## 通过声明ID定位载入经过身份验证的哈希ID {#onboard-authenticated-declared-id}

有两种方法可将离线数据引入Audience Manager [!DNL People-Based Destinations]。

* [将批处理数据](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 发送到Audience Manager以收录散列电子邮件地址。使用此方法，您可以使用 [!DNL CRM] 数据库中的所有散列电子邮件地址 [!DNL People-Based Destinations]。此外，使用此方法时，您还可以为 [载入的特征确定散列电子邮件地址](../traits/trait-qualification-reference.md)。
* 使用 [声明的ID](../declared-ids.md) 在通过身份验证的客户ID时声明散列电子邮件地址。使用此方法时，Audience [!DNL People-Based Destinations] Manager仅向已联机身份验证的用户发送散列电子邮件地址。通过Facebook激活的电子邮件地址只是声明ID事件调用中的一个。与客户ID关联的其他电子邮件地址不会实时发送。
