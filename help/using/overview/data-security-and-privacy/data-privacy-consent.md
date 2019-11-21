---
description: 本文档介绍了同意管理在Audience manager中的工作方式。
seo-description: 本文档介绍了同意管理在Audience manager中的工作方式。
seo-title: 同意管理
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: 同意管理
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: fbe4e8c912093c495f27ca887a44ac31d394811a

---


# 同意管理

## 概述 {#overview}

在某些营销活动需要同意的情况下，消费者同意必须处于活动状态（例如，没有预先选中的框或默认设置）、取消捆绑并且服务提供不得以数据主体给予同意为条件。 甚至有时某些同意需要刷新才能继续使用数据。

Audience manager为您提供了必要的工具，以获得用户的同意，以便您能够跨渠道为他们提供个性化体验。

>[!IMPORTANT]
>
> 本文件的内容不是法律咨询，也不代替法律咨询。
>
> 作为您的数据处理者，Adobe无法就获得同意提供法律建议。 我们建议您与同意管理解决方案提供商(如 [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) 或 [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/))合作，以获得最佳建议，并咨询贵公司的法律部门，以获取有关同意和在设置选择实施时的做法的建议。

## Experience Cloud选择加入服务

The [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) service lets you set up protocols for the visitor to determine if you can set a cookie on the user's device or browser when visiting your site.

This is an extension of the [!DNL Experience Cloud ID (ECID) Service], designed to let you control whether and which Experience Cloud solutions can place cookies on web pages for visitors prior to user consent.

通过 [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) ，您还可以设置协议以与同意管理平台(CMP)和现有系统集成，作为更大型设计的一部分。

## 管理选择加入／获得同意

Audience Manager客户可以在Audience manager中存储广告或个性化等不同用例的用户同意书。 然后，构建具有这些特征的区段时，将仅包括为每个使用案例提供相应同意的用户。 请注意，使用此方法不会停止数据收集，但只会在发送区段进行激活时影响数据的使用。 当用户撤回其同意时，您可以使用Audience Manager入站批处理或Audience Manager选择退出流程从用 [户档案中删除这些特征](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) ，具体如下所述。

## 管理选择退出／撤回同意

可通过您的隐私选择页面为Adobe Experience Cloud管 [理退出](https://www.adobe.com/privacy/opt-out.html#customeruse) 。 通过一键式功能，您的最终用户可以控制Adobe Experience cloud广告解决方案（包括Audience Manager）的数据收集并选择退出。 具体而言，请参 [阅“隐私选择](https://www.adobe.com/privacy/opt-out.html#customeruse) ”页面的业务客户部分。 对于不支持第三方Cookie的浏览器，请参阅声 [明ID定位](../../features/declared-ids.md#declared-id-targeting)。 对于移动设备，请检索相关的Audience manager标识符并调用Audience Manager退出API，如 [Declared ID退出示例中所述](../../features/declared-ids.md#opt-out-examples)。 随后，您可以使用Mobile SDK中的退出API停止为这些用户收集所有数据——请参阅 [Android设备](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) 和 [iOS设备](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html)。 您可以在数据隐私请求文档中找到有关选择退出的 [其他详细信息](../../overview/data-security-and-privacy/data-privacy-requests.md)。

## 管理第二方数据提供商的同意

第二方数据提供者通常也是数据管理者，并拥有从数据主体获得任何必要同意以与其第二方数据合作伙伴共享数据的过程。 作为Audience manager客户，您有责任确定第二方数据提供商是否已获得您使用案例的必要同意。 有关获得同意的更多详细信息，请参阅上文。

## 管理第三方数据提供商的同意

第三方数据提供者也是数据管理者，拥有获得同意和管理访问／删除／更正请求的流程。 Adobe主动要求数据提供商在 [Adobe Audience Finder中更新其公司档案信息，并提供有关用户数据收集的其他信息](https://www.adobe-audience-finder.com/) 。 信息将来自数据提供商并定期更新。 但是，由每位Audience manager客户确定第三方数据提供商已获得该客户使用案例的必要同意。 Adobe不对第三方数据提供商针对特定使用案例获得或报告的同意的范围或有效性做出任何声明。
