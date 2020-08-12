---
description: '请阅读以下内容，了解在注册基于人员的目标之前需要满足的客户要求。  '
seo-description: '请阅读以下内容，了解在注册基于人员的目标之前需要满足的客户要求。  '
seo-title: 基于人员的目标先决条件和注意事项
solution: Audience Manager
title: 先决条件和注意事项
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: 2e32f9ebff487ae8dfb2088ec1bbfcea1daa00a1
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 3%

---


# 先决条件和注意事项 {#prerequisites-considerations}

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

请阅读以下内容，了解在注册前需要满足的客户要求的概述 [!UICONTROL People-Based Destinations]。

>[!IMPORTANT]
> 在进入实施阶段之前，请仔细阅读本文。

## 注册 [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] 是一项高级功能，允许您在基于人的环境中激活第一方Audience Manager细分，通过社交网络或电子邮件营销定位受众，从而增强受众体验。

请联系您的Adobe代表以利用此高级功能。

## 特定于合作伙伴的先决条件 {#partner-prerequisites}

### [!DNL Facebook]

在使用将 [!UICONTROL People-Based Destinations] 第一方受众发送到 [!UICONTROL segments] 之 [!DNL Facebook]前，请确保满足以下要求：

1. 您 [!DNL Facebook] 的用户帐户必须为 **您计划使用的Ad** 帐户启用“管理活动”权限。
2. Add the **Adobe Experience Cloud** business account as an advertising partner in your [!DNL Facebook Ad Account]. 使用 `business ID=206617933627973`。See [Add Partners to Your Business Manager](https://www.facebook.com/business/help/1717412048538897) for details.
   >[!IMPORTANT]
   > When configuring the permissions for Adobe Experience Cloud, you must enable the **Manage campaigns** permission. [!UICONTROL People-Based Destinations] 集成要求具备此权限。
3. 阅读并签署 [!DNL Facebook Custom Audiences] 服务条款。 为此，请转到 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`，其中 `accountID` 是您的 [!DNL Facebook Ad Account ID]。

### [!DNL LinkedIn]

在使用将第 [!UICONTROL People-Based Destinations] 一方受众段发送到之前， [!DNL LinkedIn]请确保您的 [!DNL LinkedIn Campaign Manager] 帐户具有或更 [!DNL Creative Manager] 高的权限级别。

要了解如何编辑您的 [!DNL LinkedIn Campaign Manager] 用户权限，请 [参阅LinkedIn文档中的添加、编辑和删除](https://www.linkedin.com/help/lms/answer/5753) 广告帐户的用户权限。

有关 [视频说明，请参阅了解和配置LinkedIn基于人员的目标](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) 。

### [!DNL Google Customer Match]

在使用将第 [!UICONTROL People-Based Destinations] 一方受众段发送到目标之前，必 [!DNL Google Customer Match] 须先将您添加到 [!DNL Google] 其允许列表中。

联系您 [!DNL Google] 的代表并按照使用客户匹配合作 [伙伴中所述的允许列表说明](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) 上传您的文档 [!DNL Google] 。

完成此过程后，即可创建您的 [!UICONTROL People-Based Destination]。

## 数据载入 {#data-onboarding}

当前的数 [!UICONTROL People-Based Destinations] 据获取支持每个批量传输最多10个与一个客户ID()链接[!DNL CRM ID]的哈希电子邮件地址。 上传10个以上已散列化的电子邮件地址，链接到一个Audience ManagerID会导致客户按任意顺序收集其中的10个。

在多个批传输中，上传10个以上已散列化的电子邮件地址，将导致Audience Manager保留最近添加的10个电子邮件地址。

## 数据隐私{#data-privacy}

尽管 [!UICONTROL People-Based Destinations] 允许您根据您上传的哈希电子邮件地址目标受众，但仍禁止将任何直接可识别的访客信息上传到Audience Manager。 在数据载入阶段，您必须确保您计划使用的电子邮件地址已使用算法进行散列 [!DNL SHA256] 处理。 否则，您将无法在中使用它们 [!UICONTROL People-Based Destinations]。

## 数据哈希与加密 {#data-hashing-encryption}

加密是双向的函数。 任何加密的信息也可以使用正确的解密密钥进行解密。 在Audience Manager环境中加密数据会带来严重的风险，因为任何加密形式的个人识别信息也可以被解密。 与加密相比，它 [!UICONTROL People-Based Destinations] 设计为使用散列数据。

散列是单向函数，它对输入进行加扰以产生独特的结果。 通过使用适当的散列算法， [!DNL SHA256]例如，无法反转散列函数并显示未加扰的信息。 您将载入到Audience Manager的电子邮件地址必须使用算法进行散列 [!DNL SHA256] 处理。 这样，您就可以确保没有未散列的电子邮件地址到达Audience Manager。

## 散列要求 {#hashing-requirements}

散列电子邮件地址时，请确保符合以下要求：

* 修剪电子邮件字符串中的所有前导和尾随空格；示例： `johndoe@example.com`，不是 `<space>johndoe@example.com<space>`;
* 散列电子邮件字符串时，请确保散列小写字符串；
   * 示例： `example@email.com`，不是 `EXAMPLE@EMAIL.COM`;
* 确保哈希字符串全为小写
   * 示例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`，不是 `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* 不要把绳子盐掉。

请观看以下视频，了解的哈希要求 [!UICONTROL People-Based Destinations]。

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud允许您通过散列客户ID [!DNL Adobe Experience Platform Identity Service (ECID)]有关 [如何使用ECID对客户ID进行散列处理](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) ，请参阅SHA256 Hashing Support for setCustomerIDs，以了解详细信息。

## 获取用户权限 {#obtaining-user-permission}

由于 [!UICONTROL People-Based Destinations] 帮助您在基于人的受众中激活第一方渠道数据，因此您有责任告知客户如何将其数据用于广告或其他用途，并征得客户的必要同意。

注册前，请确 [!UICONTROL People-Based Destinations]保在将客户信息用于广告之前获得客户的同意。

如果您的客户希望退出广告活动，请参 [阅退出管理](../../overview/data-security-and-privacy/data-privacy-requests.md) ，了解有关如何阻止Audience Manager进一步收集数据的详细信息。

## 实施第一方数据激活 {#enforcing-first-party-activation}

使用时， [!UICONTROL People-Based Destinations]您只能使用第一方数据在基于人的受众中激活渠道细分。 您不能在基于人员的受众中使用任何第二方或第三方激活。

在使用 [!UICONTROL People-Based Destinations]时，请使 [用数据导出控件来标](../data-export-controls.md) 记您的，并 [!UICONTROL data sources][!UICONTROL destinations] 根据目标平台和数据提供商的准则和要求。

## 通过声明ID定位的板载验证哈希ID {#onboard-authenticated-declared-id}

有两种方法可以将离线数据载入 Audience Manager 以便用于 [!UICONTROL People-Based Destinations]。

* [向Audience Manager发送批](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 数据，以收录散列电子邮件地址。 使用此方法，您可以选择使用中数据库的散列电子邮件 [!DNL CRM] 地址 [!UICONTROL People-Based Destinations]。 此外，使用此方法时，您还可以为已载入的特征限定散列电子邮件 [地址](../traits/trait-and-segment-qualification-reference.md)。
* Use [Declared IDs](../declared-ids.md) to declare hashed email addresses when passing in authenticated customer IDs. When using this method, Audience Manager, on your behalf, only sends to [!UICONTROL People-Based Destinations] the hashed email addresses from users who have authenticated online. 通过基于人员的渠道激活的电子邮件地址只是声明的ID事件调用中的电子邮件地址。 与客户ID关联的其他电子邮件地址不会实时发送。
