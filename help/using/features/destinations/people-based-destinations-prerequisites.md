---
description: '请阅读以下内容，了解在注册基于人员的目标之前需要满足的客户要求。  '
seo-description: '请阅读以下内容，了解在注册基于人员的目标之前需要满足的客户要求。  '
seo-title: 基于人员的目标先决条件和注意事项
solution: Audience Manager
title: 先决条件和注意事项
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: d3184195d6a51ff013a3d1fc8526ca9afd3386c2
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 3%

---


# 先决条件和注意事项 {#prerequisites-considerations}

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

请阅读以下内容，了解注册[!UICONTROL People-Based Destinations]前需要满足的客户要求的概述。

>[!IMPORTANT]
> 在进入实施阶段之前，请仔细阅读本文。

## 注册[!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] 是一项高级功能，允许您在基于人的环境中激活第一方Audience Manager细分，通过社交网络或电子邮件营销定位受众，从而增强受众体验。

请联系您的Adobe代表以利用此高级功能。

## 特定于合作伙伴的先决条件{#partner-prerequisites}

### [!DNL Facebook] {#facebook}

在使用[!UICONTROL People-Based Destinations]将第一方受众[!UICONTROL segments]发送到[!DNL Facebook]之前，请确保满足以下要求：

1. 您的[!DNL Facebook]用户帐户必须为您计划使用的Ad帐户启用&#x200B;**管理活动**&#x200B;权限。
2. 将&#x200B;**Adobe Experience Cloud**&#x200B;商业帐户添加为[!DNL Facebook Ad Account]中的广告合作伙伴。 使用 `business ID=206617933627973`。有关详细信息，请参阅[将合作伙伴添加到您的业务经理](https://www.facebook.com/business/help/1717412048538897)。
   >[!IMPORTANT]
   > 配置Adobe Experience Cloud的权限时，必须启用&#x200B;**管理活动**&#x200B;权限。 [!UICONTROL People-Based Destinations] 集成要求具备此权限。
3. 阅读并签署[!DNL Facebook Custom Audiences]服务条款。 为此，请转到 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`，其中 `accountID` 是您的 [!DNL Facebook Ad Account ID]。

### [!DNL LinkedIn] {#linkedin}

在使用[!UICONTROL People-Based Destinations]将第一方受众段发送到[!DNL LinkedIn]之前，请确保您的[!DNL LinkedIn Campaign Manager]帐户具有[!DNL Creative Manager]或更高的权限级别。

要了解如何编辑[!DNL LinkedIn Campaign Manager]用户权限，请参阅LinkedIn文档中的[添加、编辑和删除广告帐户的用户权限](https://www.linkedin.com/help/lms/answer/5753)。

有关视频说明，请参见[了解和配置LinkedIn基于人的目标](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html)。

### [!DNL Google Customer Match] {#gcm}

在使用[!UICONTROL People-Based Destinations]将第一方受众段发送到[!DNL Google Customer Match]目标之前，必须先将[!DNL Google]添加到其允许列表。

与您的[!DNL Google]代表联系，按照[使用客户匹配合作伙伴上传数据](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google]文档中所述的允许列表说明进行操作。

完成此过程后，您可以创建[!UICONTROL People-Based Destination]。

## 数据载入 {#data-onboarding}

目前，[!UICONTROL People-Based Destinations]的数据获取支持每个批量传输最多10个与一个客户ID([!DNL CRM ID])链接的哈希电子邮件地址。 上传10个以上已散列化的电子邮件地址，链接到一个客户ID会导致Audience Manager按任意顺序收集其中的10个。

在多个批次传输中，上传10个以上已散列化的电子邮件地址，将导致Audience Manager保留最近添加的10个电子邮件地址。

## 数据隐私{#data-privacy}

尽管[!UICONTROL People-Based Destinations]允许您根据您上传的哈希电子邮件地址目标受众，但仍禁止将任何直接可识别身份的访客信息上传到Audience Manager。 在数据载入阶段，必须确保您计划使用的电子邮件地址已使用[!DNL SHA256]算法散列。 否则，您将无法在[!UICONTROL People-Based Destinations]中使用它们。

## 数据哈希与加密{#data-hashing-encryption}

加密是双向的函数。 任何加密的信息也可以使用正确的解密密钥进行解密。 在Audience Manager环境中加密数据会带来严重的风险，因为任何加密形式的个人识别信息也可以被解密。 与加密相反，[!UICONTROL People-Based Destinations]设计为改用散列数据。

散列是单向函数，它对输入进行加扰以产生独特的结果。 通过使用适当的散列算法（如[!DNL SHA256]），无法反转散列函数并显示未加扰的信息。 您将载入到Audience Manager的电子邮件地址必须使用[!DNL SHA256]算法进行散列处理。 这样，您就可以确保没有未散列的电子邮件地址到达Audience Manager。

## 散列要求{#hashing-requirements}

散列电子邮件地址时，请确保符合以下要求：

* 修剪电子邮件字符串中的所有前导和尾随空格；示例：`johndoe@example.com`，不是`<space>johndoe@example.com<space>`;
* 散列电子邮件字符串时，请确保散列小写字符串；
   * 示例：`example@email.com`，不是`EXAMPLE@EMAIL.COM`;
* 确保哈希字符串全为小写
   * 示例：`55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`，不是`55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* 不要把绳子盐掉。

观看以下视频以了解[!UICONTROL People-Based Destinations]的哈希要求。

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud允许您通过[!DNL Adobe Experience Platform Identity Service (ECID)]散列客户ID。 请参见[SHA256 Hashing Support for setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html)，了解有关如何使用ECID对客户ID进行散列的详细信息。

## 获取用户权限{#obtaining-user-permission}

由于[!UICONTROL People-Based Destinations]可帮助您在基于人的受众中激活第一方渠道数据，因此您有责任告知客户如何将其数据用于广告或其他用途，并征得客户的必要同意。

在注册[!UICONTROL People-Based Destinations]之前，请确保在将客户信息用于广告之前获得客户的同意。

如果您的客户希望退出广告活动，请参阅[退出管理](../../overview/data-security-and-privacy/data-privacy-requests.md)，了解有关如何阻止Audience Manager进一步收集数据的详细信息。

## 实施第一方激活{#enforcing-first-party-activation}

使用[!UICONTROL People-Based Destinations]时，您只能使用第一方数据在基于人的受众中激活渠道段。 您不能在基于人员的受众中使用任何第二方或第三方激活。

使用[!UICONTROL People-Based Destinations]时，请使用[数据导出控件](../data-export-controls.md)根据目标平台和数据提供者的准则和要求对[!UICONTROL data sources]和[!UICONTROL destinations]进行标签。

## 通过声明的ID定位{#onboard-authenticated-declared-id}的板载已验证哈希ID

有两种方法可以将离线数据载入 Audience Manager 以便用于 [!UICONTROL People-Based Destinations]。

* [发送批数](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 据Audience Manager以接收散列电子邮件地址。使用此方法，您可以选择使用[!UICONTROL People-Based Destinations]中[!DNL CRM]数据库的哈希电子邮件地址。 此外，使用此方法时，您还可以为已载入的traits[限定哈希电子邮件地址。](../traits/trait-and-segment-qualification-reference.md)
* 使用[声明的ID](../declared-ids.md)在传入经过身份验证的客户ID时声明具有哈希值的电子邮件地址。 使用此方法时，Audience Manager仅代表您向[!UICONTROL People-Based Destinations]发送经过在线身份验证的用户的哈希电子邮件地址。 通过基于人员的渠道激活的电子邮件地址只是声明的ID事件调用中的电子邮件地址。 与客户ID关联的其他电子邮件地址不会实时发送。
