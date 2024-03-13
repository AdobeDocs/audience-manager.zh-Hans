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

请阅读下文，了解注册前需要满足的客户要求 [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> 在进入实施阶段之前，请仔细阅读本文。

## 注册 [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] 是一项高级功能，通过允许您在基于人员的环境中激活第一方受众区段、通过社交网络上的自定义选件或通过电子邮件营销定位受众，来增强您的Audience Manager体验。

请联系您的Adobe代表以使用此高级功能。

## 特定于合作伙伴的先决条件 {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

在可以使用之前 [!UICONTROL People-Based Destinations] 以发送您的第一方受众 [!UICONTROL segments] 到 [!DNL Facebook]，确保您满足以下要求：

1. 您的 [!DNL Facebook] 用户帐户必须具有 **管理营销活动** 为您计划使用的Ad帐户启用的权限。
2. 添加 **Adobe Experience Cloud** 作为广告合作伙伴的商业帐户 [!DNL Facebook Ad Account]. 使用 `business ID=206617933627973`。请参阅 [将合作伙伴添加到您的业务经理](https://www.facebook.com/business/help/1717412048538897) 以了解详细信息。

   >[!IMPORTANT]
   >配置Adobe Experience Cloud的权限时，必须启用 **管理营销活动** 许可。 [!UICONTROL People-Based Destinations] 集成要求具备此权限。

3. 阅读并签署 [!DNL Facebook Custom Audiences] 服务条款。 为此，请转到 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`，其中 `accountID` 是您的 [!DNL Facebook Ad Account ID]。

### [!DNL LinkedIn] {#linkedin}

在可以使用之前 [!UICONTROL People-Based Destinations] 将您的第一方受众区段发送到 [!DNL LinkedIn]，确保您的 [!DNL LinkedIn Campaign Manager] 帐户具有 [!DNL Creative Manager] 或更高权限级别。

要了解如何编辑您的 [!DNL LinkedIn Campaign Manager] 用户权限，请参阅 [添加、编辑和删除广告帐户的用户权限](https://www.linkedin.com/help/lms/answer/5753) 请参阅LinkedIn文档。

请参阅 [了解和配置LinkedIn基于人员的目标](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) 获取视频说明。

### [!DNL Google Customer Match] {#gcm}

在可以使用之前 [!UICONTROL People-Based Destinations] 将您的第一方受众区段发送到 [!DNL Google Customer Match] 目标，请确保您已阅读并遵守Google关于使用的政策 [!DNL Customer Match]，在中概述 [Google支持文档](https://support.google.com/google-ads/answer/6299717).

接下来，确保您的 [!DNL Google] 帐户配置用于 [!DNL Standard] 或更高权限级别。 请参阅 [Google Ads文档](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) 以了解详细信息。

Google会自动允许具有合规帐户的客户列出。

## 数据载入 {#data-onboarding}

>[!IMPORTANT]
>
>所有Audience Manager客户无需注册即可摄取经过哈希处理的电子邮件 [!UICONTROL People-Based Destinations].

数据摄取 [!UICONTROL People-Based Destinations] 当前支持最多10个链接到某个客户ID ([!DNL CRM ID])，每次批次传输。

在多次批量传输中上传链接到某个客户ID的10个以上的经过哈希处理的电子邮件地址会导致Audience Manager保留最近添加的10个电子邮件地址。

要摄取经过哈希处理的标识符， [为经过哈希处理的标识符创建跨设备数据源](../create-data-source-hashed-emails.md) 并启用 **[!UICONTROL Share associated cross-device IDs in people-based destinations and/or hashed email workflows]** 选项。

![Audience ManagerUI图像显示了在基于人员的目标和/或哈希电子邮件工作流中共享关联的跨设备ID的选项](assets/data-source-share-ids.png)

## 数据隐私 {#data-privacy}

尽管 [!UICONTROL People-Based Destinations] 允许您根据自己上传的经过哈希处理的电子邮件地址来定位受众，但您仍会被禁止将任何直接可识别的访客信息上传到Audience Manager。 在数据载入阶段，您必须确保将您计划使用的电子邮件地址与 [!DNL SHA256] 算法。 否则，您将无法在 [!UICONTROL People-Based Destinations].

## 数据散列与加密 {#data-hashing-encryption}

加密是双向功能。 任何加密的信息也可以使用正确的解密密钥进行解密。 在Audience Manager的情况下加密数据会带来严重的风险，因为任何加密形式的个人身份信息都可以被解密。 与加密相反， [!UICONTROL People-Based Destinations] 设计为可处理哈希数据。

哈希处理是一种单向函数，它可以对输入进行置乱以生成唯一的结果。 通过使用适当的哈希算法，如 [!DNL SHA256]，则无法反转哈希函数并显示未置乱的信息。 要载入Audience Manager的电子邮件地址必须使用 [!DNL SHA256] 算法。 这样，即可确保任何未经哈希处理的电子邮件地址都不会到达Audience Manager。

## 哈希处理要求 {#hashing-requirements}

在对电子邮件地址进行哈希处理时，请确保符合以下要求：

* 修剪电子邮件字符串中的所有前导空格和尾随空格；示例： `johndoe@example.com`，不是 `<space>johndoe@example.com<space>`；
* 在对电子邮件字符串进行哈希处理时，请确保对小写字符串进行哈希处理；
   * 示例： `example@email.com`，不是 `EXAMPLE@EMAIL.COM`；
* 确保散列字符串全部为小写
   * 示例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`，不是 `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`；
* 不要把字串加盐。

观看以下视频，了解的哈希处理要求 [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud为您提供了用于散列客户ID的选项 [!DNL Adobe Experience Platform Identity Service (ECID)]. 请参阅 [对setCustomerIDs的SHA256哈希处理支持](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) 有关如何使用ECID对客户ID进行哈希处理的详细信息。

## 获取用户权限 {#obtaining-user-permission}

从 [!UICONTROL People-Based Destinations] 帮助您在基于人员的渠道中激活第一方受众数据，您有责任告知客户，并在客户同意您将如何将其数据用于广告或其他目的时，获得必要的同意。

在您注册之前 [!UICONTROL People-Based Destinations]，确保在将其信息用于广告用途之前获得客户的同意。

如果您的客户希望选择退出广告营销活动，请参阅 [选择退出管理](../../overview/data-security-and-privacy/data-privacy-requests.md) 有关如何阻止Audience Manager进一步收集数据的详细信息。

## 强制执行第一方数据激活 {#enforcing-first-party-activation}

使用时 [!UICONTROL People-Based Destinations]，则您只能使用第一方数据来激活基于人员的渠道中的受众区段。 在基于人员的渠道中，您无法使用任何第二方或第三方数据来激活受众。

使用时 [!UICONTROL People-Based Destinations]，使用 [数据导出控制](../data-export-controls.md) 标记您的 [!UICONTROL data sources] 和 [!UICONTROL destinations] 符合目的地平台和数据提供商的准则和要求。

## 通过声明的ID定位载入经过身份验证的哈希ID {#onboard-authenticated-declared-id}

有两种方法可以将离线数据载入 Audience Manager 以便用于 [!UICONTROL People-Based Destinations]。

* [发送批次数据](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) Audience Manager摄取经过哈希处理的电子邮件地址。 通过此方法，您可以选择使用来自 [!DNL CRM] 中的数据库 [!UICONTROL People-Based Destinations]. 此外，在使用此方法时，您还可以限定经过哈希处理的电子邮件地址 [已载入的特征](../traits/trait-and-segment-qualification-reference.md).
* 使用 [声明的ID](../declared-ids.md) 以在传入经过身份验证的客户ID时声明经过哈希处理的电子邮件地址。 使用此方法时，Audience Manager仅代表您发送至 [!UICONTROL People-Based Destinations] 经过哈希处理的电子邮件地址，这些地址来自已在线进行身份验证的用户。 通过基于人员的渠道激活的电子邮件地址只是声明的ID事件调用中的电子邮件地址。 与客户ID关联的其他电子邮件地址不会实时发送。
