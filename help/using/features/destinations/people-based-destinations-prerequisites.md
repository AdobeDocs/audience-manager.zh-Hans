---
description: '请阅读以下内容，了解在注册基于人员的目标之前需要满足的客户要求。  '
seo-description: '请阅读以下内容，了解在注册基于人员的目标之前需要满足的客户要求。  '
seo-title: 基于人员的目标先决条件和注意事项
solution: Audience Manager
title: 先决条件和注意事项
feature: 基于人的目标
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 3%

---

# 先决条件和注意事项 {#prerequisites-considerations}

>[!IMPORTANT]
>本文包含旨在指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都是法律建议。 请咨询您自己的法律顾问以获得法律指导。

请阅读以下内容，了解注册[!UICONTROL People-Based Destinations]前需要满足的客户要求的概述。

>[!IMPORTANT]
> 在进入实施阶段之前，请仔细阅读本文。

## 注册[!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] 是一项高级功能，允许您在基于人的环境中激活第一方Audience Manager细分，并通过社交网络或电子邮件营销定位受众，从而增强您的受众体验。

请联系您的Adobe代表以利用此高级功能。

## 特定于合作伙伴的先决条件{#partner-prerequisites}

### [!DNL Facebook] {#facebook}

在使用[!UICONTROL People-Based Destinations]将第一方受众[!UICONTROL segments]发送到[!DNL Facebook]之前，请确保满足以下要求：

1. 您的[!DNL Facebook]用户帐户必须为您计划使用的Ad帐户启用&#x200B;**管理活动**&#x200B;权限。
2. 将&#x200B;**Adobe Experience Cloud**&#x200B;业务帐户添加为[!DNL Facebook Ad Account]中的广告合作伙伴。 使用 `business ID=206617933627973`。有关详细信息，请参阅[将合作伙伴添加到您的业务经理](https://www.facebook.com/business/help/1717412048538897)。
   >[!IMPORTANT]
   > 配置Adobe Experience Cloud的权限时，必须启用&#x200B;**管理活动**&#x200B;权限。 [!UICONTROL People-Based Destinations] 集成要求具备此权限。
3. 阅读并签署[!DNL Facebook Custom Audiences]服务条款。 为此，请转到 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`，其中 `accountID` 是您的 [!DNL Facebook Ad Account ID]。

### [!DNL LinkedIn] {#linkedin}

在使用[!UICONTROL People-Based Destinations]将第一方受众段发送到[!DNL LinkedIn]之前，请确保您的[!DNL LinkedIn Campaign Manager]帐户具有[!DNL Creative Manager]或更高权限级别。

要了解如何编辑您的[!DNL LinkedIn Campaign Manager]用户权限，请参阅LinkedIn文档中的[添加、编辑和删除广告帐户的用户权限](https://www.linkedin.com/help/lms/answer/5753)。

有关视频说明，请参阅[了解和配置基于人员的LinkedIn目标](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html)。

### [!DNL Google Customer Match] {#gcm}

在使用[!UICONTROL People-Based Destinations]将第一方受众段发送到[!DNL Google Customer Match]目标之前，必须先将[!DNL Google]添加到其允许列表。

请联系您的[!DNL Google]代表，并按照[使用客户匹配合作伙伴上传您的数据](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google]文档中描述的允许列表说明进行操作。

完成此过程后，即可创建[!UICONTROL People-Based Destination]。

## 数据载入 {#data-onboarding}

[!UICONTROL People-Based Destinations]的数据摄取当前支持每个批量传输最多10个与一个客户ID([!DNL CRM ID])链接的散列电子邮件地址。 上传10个以上哈希电子邮件地址（链接到一个客户ID）会导致Audience Manager以无特定顺序收录其中的10个。

在多个批量传输中上传10个以上已哈希化的电子邮件地址链接到一个Audience ManagerID会导致客户保留最新添加的10个电子邮件地址。

## 数据隐私{#data-privacy}

尽管[!UICONTROL People-Based Destinations]允许您根据您上传的散列电子邮件地址目标受众，但仍禁止将任何直接可识别的访客信息上传到Audience Manager。 在数据入门阶段，您必须确保计划使用的电子邮件地址已使用[!DNL SHA256]算法进行哈希处理。 否则，您将无法在[!UICONTROL People-Based Destinations]中使用它们。

## 数据哈希与加密{#data-hashing-encryption}

加密是双向功能。 任何加密的信息也可以使用正确的解密密钥进行解密。 在Audience Manager环境中加密数据会带来严重风险，因为任何加密形式的个人识别信息也可以被解密。 与加密相反，[!UICONTROL People-Based Destinations]设计为使用散列数据。

散列是单向函数，它对输入进行加扰以产生独特的结果。 通过使用适当的散列算法（如[!DNL SHA256]），无法反转散列函数并显示未加扰的信息。 您将加载到Audience Manager的电子邮件地址必须使用[!DNL SHA256]算法进行哈希处理。 这样，您就可以确保没有未散列的电子邮件地址到达Audience Manager。

## 散列要求{#hashing-requirements}

对电子邮件地址进行散列处理时，请确保符合以下要求：

* 裁切电子邮件字符串中的所有前导和尾随空格；示例：`johndoe@example.com`，不是`<space>johndoe@example.com<space>`;
* 对电子邮件字符串进行散列时，请确保对小写字符串进行散列；
   * 示例：`example@email.com`，不是`EXAMPLE@EMAIL.COM`;
* 确保哈希字符串全为小写
   * 示例：`55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`，不是`55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* 不要用盐分。

观看以下视频，了解[!UICONTROL People-Based Destinations]的散列法要求。

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud为您提供通过[!DNL Adobe Experience Platform Identity Service (ECID)]对客户ID进行哈希处理的选项。 有关如何使用ECID对客户ID进行哈希处理的详细信息，请参阅[针对setCustomerID的散列支持](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html)。

## 获取用户权限{#obtaining-user-permission}

由于[!UICONTROL People-Based Destinations]可帮助您在基于人的渠道中激活第一方受众数据，因此您有责任向客户通知并征求其同意您将如何使用其数据用于广告或其他目的。

在注册[!UICONTROL People-Based Destinations]之前，请确保在将客户信息用于广告之前获得客户的同意。

如果您的客户希望退出广告活动，请参阅[退出管理](../../overview/data-security-and-privacy/data-privacy-requests.md)以了解有关如何阻止Audience Manager进一步收集数据的详细信息。

## 实施第一方数据激活{#enforcing-first-party-activation}

使用[!UICONTROL People-Based Destinations]时，您只能使用第一方数据在基于人的渠道中激活受众区段。 您不能在基于人的渠道中将任何第二方或第三方数据用于受众激活。

使用[!UICONTROL People-Based Destinations]时，请使用[数据导出控件](../data-export-controls.md)根据目标平台和数据提供商的准则和要求对[!UICONTROL data sources]和[!UICONTROL destinations]进行标签。

## 通过声明ID定位{#onboard-authenticated-declared-id}的板载已验证哈希ID

有两种方法可以将离线数据载入 Audience Manager 以便用于 [!UICONTROL People-Based Destinations]。

* [将批数据](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) Audience Manager发送到收录散列电子邮件地址。使用此方法，您可以选择使用[!UICONTROL People-Based Destinations]中[!DNL CRM]数据库中的哈希电子邮件地址。 此外，使用此方法时，您还可以确定[已载入特征](../traits/trait-and-segment-qualification-reference.md)的哈希电子邮件地址。
* 使用[声明的ID](../declared-ids.md)可在传入经过身份验证的客户ID时声明哈希化的电子邮件地址。 使用此方法时，Audience Manager仅代表您向[!UICONTROL People-Based Destinations]发送经过散列处理的电子邮件地址，这些地址来自已在线验证的用户。 通过基于人员的渠道激活的电子邮件地址只是声明的ID事件调用中的电子邮件地址。 与客户ID关联的其他电子邮件地址不会实时发送。
