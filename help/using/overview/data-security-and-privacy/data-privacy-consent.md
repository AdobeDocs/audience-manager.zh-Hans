---
description: 本文档介绍同意管理在受众管理器中的工作方式。
seo-description: 本文档介绍同意管理在受众管理器中的工作方式。
seo-title: 同意管理
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: 同意管理
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# 同意管理

## 概述 {#overview}

在需要特定营销活动同意的情况下，受众经理客户必须确定范围和范围，以及是否需要刷新特定同意才能继续使用未来的数据。

受众管理器优惠您的工具，帮助您支持您从用户处获得所需同意的能力，以便您能够跨渠道为他们提供个性化体验。

>[!IMPORTANT]
>
> 本文档的内容不是法律咨询，不能代替法律咨询。
>
> 作为您的数据处理者，Adobe无法就获得同意提供法律建议。 您还可以考虑与同意管理解决方案提供商( [如Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) 或 [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/))合作，并咨询公司的法律部门，以获得在设置选择实施时有关同意和惯例的建议。

## Experience Cloud选择加入服务

The [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) lets you set up protocols for the visitor to assist you in determining if you can set a cookie on the individual&#39;s device or browser when visiting your site.

This is an extension of the [!DNL Experience Cloud ID (ECID) Service], designed to let you control whether and which Experience Cloud solutions can place cookies on web pages for visitors prior to user consent.

Experience [Cloud选择加入服务](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) ，还允许您设置协议，将协议与同意管理平台(CMP)和现有系统集成，作为更大型设计的一部分。

## 管理选择加入／获得同意

受众管理器客户能够将用户同意存储为受众管理器中的各种用例，如广告或个性化特征。 根据这些特征构建的细分将仅包括为每个使用案例提供相应同意的用户。 请注意，使用此方法不会停止数据收集，但只会在您发送区段进行激活时影响数据的使用。 当用户撤回其同意时，您可以使用用户档案管理器入站批处理或受众管理 [器选择退出流程](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) ，从用户受众中删除这些特征，详见下文。

## 管理选择退出／撤回同意

您可以通过您的隐私选择页面为Adobe Experience Cloud管 [理退出](https://www.adobe.com/privacy/opt-out.html#customeruse) 。 一键式功能可让您的最终用户通过Adobe Experience Cloud广告解决方案(包括受众管理器)控制和选择退出数据收集。 具体而言，请参 [阅隐私选择](https://www.adobe.com/privacy/opt-out.html#customeruse) 页面的业务客户部分。 有关不支持第三方Cookie的浏览器，请参阅声 [明ID定位](../../features/declared-ids.md#declared-id-targeting)。 对于移动设备，请检索相关的受众管理器标识符并调用受众管理器选择退出API，如 [声明ID选择退出示例中所述](../../features/declared-ids.md#opt-out-examples)。 之后，您可以使用Mobile SDK中的API停止为这些用户收集所选择退出有数据——请参阅 [Android设备](https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html) 和 [iOS设备](https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html)。 您可以在数据隐私请求文档中找到有关选择退 [出的其他详细信息](../../overview/data-security-and-privacy/data-privacy-requests.md)。

## 管理第二方合作伙伴的同意

第二方合作伙伴通常也是数据管理者，拥有从数据主体获取任何必要同意的过程，以便与其第二方数据合作伙伴共享数据。 作为受众经理客户，您有责任确定第二方合作伙伴是否已获得您使用案例的必要同意。 有关取得同意的更多详情请参阅上文。

## 管理受众市场第三方合作伙伴的同意

受众市场第三方合作伙伴也是数据管理者，拥有获得同意和管理访问／删除／更正请求的流程。 Adobe主动要求受众市场第三方合作伙伴在Adobe受众查找器中更新其用户档案 [信息，并提供有关用户公司收](https://www.adobe-audience-finder.com/) 集的其他信息。 信息将从受众市场第三方合作伙伴处获得，并定期进行更新。 但是，由每位受众经理客户决定受众市场第三方合作伙伴是否已获得该客户使用案例的必要同意。 Adobe不对受众市场第三方合作伙伴针对特定用例获得或报告的同意的范围或有效性做出任何声明。
