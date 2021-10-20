---
description: '请阅读下文，了解在注册基于人员的目标之前需要满足的客户要求。  '
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: 先决条件和注意事项
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: cd40e1e3cc2199d1937950934d674cfad301f3e8
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 3%

---

# 先决条件和注意事项 {#prerequisites-considerations}

>[!IMPORTANT]
>本文包含旨在指导您完成此功能的设置和使用的产品文档。 这里没有任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

请阅读下文，了解在注册之前需要满足的客户要求的概述 [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> 在进入实施阶段之前，请仔细阅读本文。

## 注册 [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] 是一项高级功能，通过允许您在基于人员的环境中激活第一方受众区段，并通过社交网络上的自定义选件或电子邮件营销定向受众，来增强您的Audience Manager体验。

请联系您的Adobe代表以利用此高级功能。

## 特定于合作伙伴的先决条件 {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

在使用之前 [!UICONTROL People-Based Destinations] 发送第一方受众 [!UICONTROL segments] to [!DNL Facebook]，请确保满足以下要求：

1. 您的 [!DNL Facebook] 用户帐户必须具有 **管理营销活动** 为您计划使用的广告帐户启用的权限。
2. 添加 **Adobe Experience Cloud** 商业帐户作为您的 [!DNL Facebook Ad Account]. 使用 `business ID=206617933627973`。请参阅 [将合作伙伴添加到您的业务经理](https://www.facebook.com/business/help/1717412048538897) 以了解详细信息。
   >[!IMPORTANT]
   > 配置Adobe Experience Cloud的权限时，必须启用 **管理营销活动** 权限。 [!UICONTROL People-Based Destinations] 集成要求具备此权限。
3. 阅读并签署 [!DNL Facebook Custom Audiences] 服务条款。 为此，请转到 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`，其中 `accountID` 是您的 [!DNL Facebook Ad Account ID]。

### [!DNL LinkedIn] {#linkedin}

在使用之前 [!UICONTROL People-Based Destinations] 将第一方受众区段发送到 [!DNL LinkedIn]，确保 [!DNL LinkedIn Campaign Manager] 帐户具有 [!DNL Creative Manager] 或更高的权限级别。

了解如何编辑 [!DNL LinkedIn Campaign Manager] 用户权限，请参阅 [添加、编辑和删除广告帐户的用户权限](https://www.linkedin.com/help/lms/answer/5753) (在LinkedIn文档中)。

请参阅 [了解和配置LinkedIn基于人员的目标](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) ，以了解视频说明。

### [!DNL Google Customer Match] {#gcm}

在使用之前 [!UICONTROL People-Based Destinations] 将第一方受众区段发送到 [!DNL Google Customer Match] 目标，请确保阅读并遵循Google的策略以使用 [!DNL Customer Match]，在 [Google支持文档](https://support.google.com/google-ads/answer/6299717).

接下来，确保您的 [!DNL Google] 为 [!DNL Standard] 或更高的权限级别。 请参阅 [Google Ads文档](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) 以了解详细信息。

具有合规帐户的客户会自动允许由Google列出。

## 数据载入 {#data-onboarding}

数据获取 [!UICONTROL People-Based Destinations] 当前最多支持与一个客户ID([!DNL CRM ID])，每次批量传输。 上传10个以上经过哈希处理的电子邮件地址，并将其链接到一个客户ID，会导致Audience Manager按特定顺序摄取其中10个。

在多次批量传输中上传10个以上经过哈希处理的电子邮件地址，以便关联到一个客户ID，这会导致Audience Manager保留最近添加的10个电子邮件地址。

## 数据隐私 {#data-privacy}

尽管 [!UICONTROL People-Based Destinations] 如果允许您根据上传的经过哈希处理的电子邮件地址来定位受众，则仍禁止将任何直接可识别的访客信息上传到Audience Manager。 在数据载入阶段，您必须确保您计划使用的电子邮件地址与 [!DNL SHA256] 算法。 否则，您将无法在 [!UICONTROL People-Based Destinations].

## 数据哈希处理与加密 {#data-hashing-encryption}

加密是双向的。 任何加密信息也可以使用正确的解密密钥解密。 在Audience Manager环境中对数据进行加密会带来严重的风险，因为任何加密形式的个人身份信息也都可以解密。 与加密相反， [!UICONTROL People-Based Destinations] 旨在改用经过哈希处理的数据。

哈希处理是一种单向函数，用于对输入进行加扰以产生唯一的结果。 通过使用适当的哈希算法，例如 [!DNL SHA256]，则无法反转哈希函数并显示未加扰的信息。 您要载入到Audience Manager的电子邮件地址必须使用进行哈希处理 [!DNL SHA256] 算法。 这样，您就可以确保没有未经哈希处理的电子邮件地址可以访问Audience Manager。

## 哈希处理要求 {#hashing-requirements}

对电子邮件地址进行哈希处理时，请确保符合以下要求：

* 从电子邮件字符串中裁切所有前导和尾随空格；示例： `johndoe@example.com`，否 `<space>johndoe@example.com<space>`;
* 对电子邮件字符串进行哈希处理时，请确保对小写字符串进行哈希处理；
   * 示例： `example@email.com`，否 `EXAMPLE@EMAIL.COM`;
* 确保经过哈希处理的字符串全部为小写
   * 示例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`，否 `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* 不要加盐。

请观看以下视频，以了解的哈希处理要求 [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud允许您选择通过 [!DNL Adobe Experience Platform Identity Service (ECID)]. 请参阅 [对setCustomerIDs的SHA256哈希处理支持](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) 有关如何使用ECID对客户ID进行哈希处理的详细信息。

## 获取用户权限 {#obtaining-user-permission}

自 [!UICONTROL People-Based Destinations] 可帮助您在基于人员的渠道中激活第一方受众数据，您有责任告知客户如何将其数据用于广告或其他目的，并征得客户的任何必要同意。

在您注册之前 [!UICONTROL People-Based Destinations]，请确保在将客户信息用于广告之前获得客户同意。

如果您的客户希望选择退出广告促销活动，请参阅 [选择退出管理](../../overview/data-security-and-privacy/data-privacy-requests.md) 以详细了解如何停止Audience Manager进一步收集数据。

## 实施第一方数据激活 {#enforcing-first-party-activation}

使用 [!UICONTROL People-Based Destinations]，则您只能使用第一方数据在基于人员的渠道中激活受众区段。 您无法在基于人员的渠道中使用任何第二方或第三方数据进行受众激活。

使用 [!UICONTROL People-Based Destinations]，使用 [数据导出控制](../data-export-controls.md) 为 [!UICONTROL data sources] 和 [!UICONTROL destinations] 根据目标平台和数据提供商的准则和要求。

## 通过声明的ID定位载入经过身份验证的哈希ID {#onboard-authenticated-declared-id}

有两种方法可以将离线数据载入 Audience Manager 以便用于 [!UICONTROL People-Based Destinations]。

* [发送批量数据](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) Audience Manager以摄取经过哈希处理的电子邮件地址。 通过此方法，您可以选择使用 [!DNL CRM] 数据库 [!UICONTROL People-Based Destinations]. 此外，使用此方法时，您还可以将经过哈希处理的电子邮件地址限定为 [已载入的特征](../traits/trait-and-segment-qualification-reference.md).
* 使用 [声明的ID](../declared-ids.md) 用于在传递经过身份验证的客户ID时声明经过哈希处理的电子邮件地址。 使用此方法时，Audience Manager仅会代表您向 [!UICONTROL People-Based Destinations] 已在线进行身份验证的用户的经过哈希处理的电子邮件地址。 通过基于人员的渠道激活的电子邮件地址只是声明的ID事件调用中的电子邮件地址。 与客户ID关联的其他电子邮件地址不会实时发送。
