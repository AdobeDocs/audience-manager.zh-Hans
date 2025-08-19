---
description: 请阅读下文，了解您在注册People-Based Destinations之前需要满足的客户要求。
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: 先决条件和注意事项
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: 2b823855994f394261a66e896ef7de7bb7a5450f
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 2%

---


# 先决条件和注意事项 {#prerequisites-considerations}

>[!IMPORTANT]
>本文包含产品文档，旨在指导您完成此功能的设置和使用。 此处不包含任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

请阅读下文，了解您在注册[!UICONTROL People-Based Destinations]之前需要满足的客户要求。

>[!IMPORTANT]
> 在进入实施阶段之前，请仔细阅读本文。

## 正在注册[!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations]是一项高级功能，它通过允许您在基于人员的环境中激活第一方受众区段、通过社交网络上的自定义优惠或通过电子邮件营销定向受众，来增强您的Audience Manager体验。

请联系您的Adobe代表以使用此高级功能。

## 特定于合作伙伴的先决条件 {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

在使用[!UICONTROL People-Based Destinations]将第一方受众[!UICONTROL segments]发送到[!DNL Facebook]之前，请确保您满足以下要求：

1. 您的[!DNL Facebook]用户帐户必须为计划使用的广告帐户启用&#x200B;**管理营销活动**&#x200B;权限。
2. 将&#x200B;**Adobe Experience Cloud**&#x200B;商业帐户添加为您[!DNL Facebook Ad Account]中的广告合作伙伴。 使用 `business ID=206617933627973`。有关详细信息，请参阅[将合作伙伴添加到业务管理器](https://www.facebook.com/business/help/1717412048538897)。

   >[!IMPORTANT]
   >配置Adobe Experience Cloud的权限时，必须启用&#x200B;**管理营销活动**&#x200B;权限。 [!UICONTROL People-Based Destinations] 集成要求具备此权限。

3. 阅读并签署[!DNL Facebook Custom Audiences]服务条款。 为此，请转到 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`，其中 `accountID` 是您的 [!DNL Facebook Ad Account ID]。

### [!DNL LinkedIn] {#linkedin}

在使用[!UICONTROL People-Based Destinations]将第一方受众区段发送到[!DNL LinkedIn]之前，请确保您的[!DNL LinkedIn Campaign Manager]帐户具有[!DNL Creative Manager]或更高权限级别。

要了解如何编辑您的[!DNL LinkedIn Campaign Manager]用户权限，请参阅LinkedIn文档中的[添加、编辑和删除Advertising帐户的用户权限](https://www.linkedin.com/help/lms/answer/5753)。

有关视频说明，请参阅[了解和配置LinkedIn基于人员的目标](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html?lang=zh-Hans)。

### [!DNL Google Customer Match] {#gcm}

在使用[!UICONTROL People-Based Destinations]将第一方受众区段发送到[!DNL Google Customer Match]目标之前，请确保您已阅读并遵守Google关于使用[!DNL Customer Match]的政策，如[Google支持文档](https://support.google.com/google-ads/answer/6299717)中所述。

接下来，确保为您的[!DNL Google]帐户配置了[!DNL Standard]或更高权限级别。 有关详细信息，请参阅[Google广告文档](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&rd=1)。

Google会自动允许具有合规帐户的客户列出。

## 数据载入 {#data-onboarding}

>[!IMPORTANT]
>
>所有Audience Manager客户都可以摄取经过哈希处理的电子邮件，而无需注册[!UICONTROL People-Based Destinations]。

[!UICONTROL People-Based Destinations]的数据摄取当前支持每个批处理传输最多10个链接到一个客户ID ([!DNL CRM ID])的哈希电子邮件地址。

如果在多次批量传输中上传链接到一个客户ID的10个以上的经过哈希处理的电子邮件地址，则会导致Audience Manager保留最近添加的10个电子邮件地址。

若要摄取哈希标识符，请[为哈希标识符](../create-data-source-hashed-emails.md)创建跨设备数据源，并启用&#x200B;**[!UICONTROL Share associated cross-device IDs in people-based destinations and/or hashed email workflows]**&#x200B;选项。

![Audience Manager UI图像显示了在基于人员的目标和/或哈希电子邮件工作流中共享关联的跨设备ID的选项](assets/data-source-share-ids.png)

## 数据隐私 {#data-privacy}

虽然[!UICONTROL People-Based Destinations]允许您根据您上传的经过哈希处理的电子邮件地址来定位受众，但仍禁止您将任何直接可识别的访客信息上传到Audience Manager。 在数据载入阶段，您必须确保使用[!DNL SHA256]算法对您计划使用的电子邮件地址进行哈希处理。 否则，您将无法在[!UICONTROL People-Based Destinations]中使用它们。

## 数据散列与加密 {#data-hashing-encryption}

加密是双向功能。 任何加密的信息也可以使用正确的解密密钥进行解密。 在Audience Manager上下文中加密数据会带来严重风险，因为任何加密形式的个人身份信息都可以被解密。 与加密相反，[!UICONTROL People-Based Destinations]设计用于处理哈希数据。

哈希处理是一种单向函数，它可以对输入进行置乱以生成唯一的结果。 如果使用正确的哈希算法（如[!DNL SHA256]），则无法反转哈希函数并显示未加扰的信息。 您将载入Audience Manager的电子邮件地址必须使用[!DNL SHA256]算法进行哈希处理。 这样，您可以确保任何未经哈希处理的电子邮件地址都不会发送到Audience Manager。

## 哈希处理要求 {#hashing-requirements}

在对电子邮件地址进行哈希处理时，请确保符合以下要求：

* 从电子邮件字符串中修剪所有前导空格和尾随空格；示例： `johndoe@example.com`，而不是`<space>johndoe@example.com<space>`；
* 在对电子邮件字符串进行哈希处理时，请确保对小写字符串进行哈希处理；
   * 示例： `example@email.com`，而不是`EXAMPLE@EMAIL.COM`；
* 确保散列字符串全部为小写
   * 示例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`，而不是`55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`；
* 不要把字串加盐。

观看以下视频，了解[!UICONTROL People-Based Destinations]的哈希处理要求。

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud为您提供通过[!DNL Adobe Experience Platform Identity Service (ECID)]对客户ID进行哈希处理的选项。 有关如何使用ECID对客户ID进行哈希处理的详细信息，请参阅对setCustomerIDs[的](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html?lang=zh-Hans)SHA256哈希处理支持。

## 获取用户权限 {#obtaining-user-permission}

由于[!UICONTROL People-Based Destinations]可帮助您在基于人员的渠道中激活第一方受众数据，因此您有责任通知客户，并征得客户关于您如何将其数据用于广告或其他目的的任何必要同意。

在注册[!UICONTROL People-Based Destinations]之前，请确保先获得客户的同意，然后再将其信息用于广告目的。

如果您的客户希望选择退出广告营销活动，请参阅[选择退出管理](../../overview/data-security-and-privacy/data-privacy-requests.md)，了解有关如何阻止Audience Manager进一步收集数据的详细信息。

## 强制执行第一方数据激活 {#enforcing-first-party-activation}

使用[!UICONTROL People-Based Destinations]时，您只能使用第一方数据激活基于人员的渠道中的受众区段。 在基于人员的渠道中，您无法使用任何第二方或第三方数据来激活受众。

使用[!UICONTROL People-Based Destinations]时，根据目标平台和数据提供商的准则和要求，使用[数据导出控件](../data-export-controls.md)来标记您的[!UICONTROL data sources]和[!UICONTROL destinations]。

## 通过声明的ID定位载入经过身份验证的哈希ID {#onboard-authenticated-declared-id}

有两种方法可以将离线数据载入 Audience Manager 以便用于 [!UICONTROL People-Based Destinations]。

* [将批次数据](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)发送到Audience Manager以摄取经过哈希处理的电子邮件地址。 使用此方法，您可以选择使用[!DNL CRM]中[!UICONTROL People-Based Destinations]数据库的经过哈希处理的电子邮件地址。 此外，使用此方法时，您还可以限定经过哈希处理的电子邮件地址是否具有[载入的特征](../traits/trait-and-segment-qualification-reference.md)。
* 在传入经过身份验证的客户ID时，使用[声明的ID](../declared-ids.md)来声明经过哈希处理的电子邮件地址。 使用此方法时，Audience Manager仅代表您向在线进行身份验证的用户的[!UICONTROL People-Based Destinations]发送经过哈希处理的电子邮件地址。 通过基于人员的渠道激活的电子邮件地址只是声明的ID事件调用中的电子邮件地址。 与客户ID关联的其他电子邮件地址不会实时发送。
