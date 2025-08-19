---
description: 本文档介绍同意管理在 Audience Manager 中的工作方式。
seo-description: This document explains how consent management works in Audience Manager.
seo-title: Consent Management
solution: Audience Manager
keywords: GDPR UI， GDPR API， CCPA，隐私，同意
title: 同意管理
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: 9e545e8d-dbe4-4df9-8801-af3c2c73e406
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 98%

---

# 同意管理

## 概述 {#overview}

如果某些营销活动需要获得用户同意，Audience Manager 客户必须确定范围，以及是否需要刷新特定同意才能继续使用将来的数据。

Audience Manager 可为您提供工具，帮助您从用户那里获得所需的同意，以便跨渠道向他们提供个性化的体验。

>[!IMPORTANT]
>
> 本文档的内容不是法律建议，也不会代替法律建议。
>
> 作为您的数据处理者，Adobe 无法就获得用户同意提供法律建议。在设置选择加入实施时，您也可以考虑与同意管理解决方案提供商（如 [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) 或 [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/)）合作，以及咨询公司的法律部门，以获得有关同意和实践的建议。

## Experience Cloud 选择加入服务

[Experience Cloud 选择加入服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=zh-Hans)允许您为访客设置协议，以帮助确定在用户访问网站时您是否可以在用户的设备或浏览器上设置 Cookie。

这是 [!DNL Experience Cloud ID (ECID) Service] 的一项扩展，旨在让您控制 Experience Cloud 解决方案是否可以在用户同意前为访客在网页上放置 Cookie，如果是，具体是哪些解决方案。

[Experience Cloud 选择加入服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=zh-Hans)还允许您设置协议，以便与同意管理平台 (CMP) 和更大型设计中的现有系统相集成。

## 管理选择加入/获取同意

Audience Manager 客户能够将各种用例（如广告或个性化）的用户同意作为特征存储在 Audience Manager 中。然后，使用这些特征构建的区段将只包括为每个用例提供相应同意的用户。请注意，使用此方法不会停止数据收集，但只会在您发送区段进行激活时影响数据的使用。当用户撤回同意时，您可以使用 Audience Manager [入站批处理过程](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)或 Audience Manager 选择退出过程从用户配置文件中删除这些特征，如下所述。

## 管理选择退出/撤回同意

可以通过[隐私选择](https://www.adobe.com/cn/privacy/opt-out.html#customeruse)页面为 Adobe Experience Cloud 管理选择退出。一键式功能允许您的最终用户通过 Adobe Experience Cloud 广告解决方案（包括 Audience Manager）控制和选择退出数据收集。有关具体信息，请参阅隐私选择页面中的[企业客户部分](https://www.adobe.com/cn/privacy/opt-out.html#customeruse)。有关不支持第三方 Cookie 的浏览器，请参阅[声明的 ID 定位](../../features/declared-ids.md#declared-id-targeting)。对于移动设备，请按照[声明的 ID 选择退出示例](../../features/declared-ids.md#opt-out-examples)中所述，检索相关的 Audience Manager 标识符并调用 Audience Manager 选择退出 API。之后，您可以使用 Mobile SDK 中的选择退出 API 停止这些用户的所有数据收集 - 请参阅 [Android 设备](https://experienceleague.adobe.com/docs/mobile-services/android/gdpr-privacy-android/privacy.html?lang=zh-Hans)和 [iOS 设备](https://experienceleague.adobe.com/docs/mobile-services/ios/privacy-gdpr-ios/privacy.html?lang=zh-Hans)。您可以在[数据隐私请求文档](../../overview/data-security-and-privacy/data-privacy-requests.md)中找到有关选择退出的其他详细信息。

## 为第二方合作伙伴管理同意

第二方合作伙伴通常也是数据控制者，拥有从数据主体获得任何必要同意的流程，以便与其第二方数据合作伙伴共享数据。作为 Audience Manager 客户，您有责任确定第二方合作伙伴是否已针对您的用例获得必要的同意。有关获取同意的更多详细信息，请参阅上文。

## 为 Audience Marketplace 第三方合作伙伴管理同意

Audience Marketplace 第三方合作伙伴也是数据控制者，拥有获得同意和管理访问/删除/更正请求的流程。Adobe 积极要求 Audience Marketplace 第三方合作伙伴在 [Adobe 受众查找器](https://www.adobe-audience-finder.com/)中更新其公司配置文件信息，以包含有关用户数据收集的其他信息。信息将从 Audience Marketplace 第三方合作伙伴处获得，并定期进行更新。但是，由每个 Audience Manager 客户确定 Audience Marketplace 第三方合作伙伴是否已针对该客户用例获得必要的同意。Adobe 不对 Audience Marketplace 第三方合作伙伴针对特定用例已获得或已报告的同意的范围或有效性做出任何声明。
