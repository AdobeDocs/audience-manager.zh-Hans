---
description: 描述Audience Manager集成以及遵守与消费者隐私和选择退出程序相关的公认最佳实践。
seo-description: 描述Audience Manager集成以及遵守与消费者隐私和选择退出程序相关的公认最佳实践。
seo-title: 数据隐私概述
solution: Audience Manager
title: 数据隐私概述
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 2%

---


# 数据隐私概述 {#data-privacy}

## 概述

数据隐私文档描述 [!DNL Audience Manager] 与消费者隐私和选择退出程序相关的公认最佳实践的集成和合规性。

[!DNL Audience Manager] 认识到消费者与其互动的在线品牌之间关系的重要性。 双方都受益于匿名数据元素的透明交换：

* 消费者可获得个性化内容、折扣产品优惠和简化的用户体验。
* 各品牌可获得支持多个在线业务模型的重要收入流。

在我们继续支持这种模式 [!DNL Audience Manager] 的过程中，我们仍致力于为您提供工具，帮助您支持向消费者提供透明度和控制的能力，同时根据在线行为广告(OBA)自 [律原则提供个性化广告](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/)。

## GDPR {#gdpr}

一般 [数据保护规定](https://eugdpr.org/) (GDPR)为欧洲合并成员引入了多项新的数据隐私权，包括 **访问权** 和 **被遗忘权**。 这意味着，您的企业已收集其个人数据的任何欧盟公民都可以请求随时访问或删除其数据。 如果不能遵守这些要求，您的组织将面临数百万美元的罚款。

为符合要求， [!DNL GDPR]支持 [!DNL Audience Manager] 数据访问和删除 [请求](data-privacy-requests.md)。

## CCPA {#ccpa}

2020 [年1月1日生效的《加州消费者隐私法》](https://www.caprivacy.org/about)(California Consumer Privacy Act, CCPA)为加利福尼亚州居民提供了有关其个人信息的新权利，并对在加利福尼亚开展业务的某些实体负有数据保护责任。

[!DNL CCPA] 为加州居民提供新的数据隐私权，包括访问和删除其个人数据以及了解其个人数据是出售还是披露（以及向谁）的权利。 为符合要求， [!DNL CCPA]支持 [!DNL Audience Manager] 访问 [!DNL CCPA] 和删除 [请求](data-privacy-requests.md)。

有关更多 [详细信息](https://www.adobe.com/privacy/opt-out.html) ，请参阅Adobe隐私中心。

## 法规合规性 {#compliance}

[!DNL Audience Manager] 通过Adobe Experience Platform Privacy Service访问和删除请求等隐私工具，帮助您遵守某些隐私 [法规](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 下的义务。

此服务提供一 [!DNL RESTful API] 个用户界面，帮助您管理消费者数据请求。 使用 [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)，您可以根据个人消费者的请求提交访问和删除个人数据的请求，从而帮助自动处理这部分合规义务。

虽然Privacy Service处理数据访问和删除请 [求](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), [但DCS API当前支持退](data-privacy-requests.md#opt-out-requests) 出请求 [](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)。 有关详 [细信息，请参阅](data-privacy-requests.md) “数据隐私请求”。

## 相关概念 {#related-concepts}

* [数据隐私请求](data-privacy-requests.md)
* [同意管理](data-privacy-consent.md)
* [适用于 IAB TCF 的 Audience Manager 插件](aam-iab-plugin.md)
* [Audience Manager标识符](data-privacy-ids.md)
* [CCPA术语表](aam-ccpa-glossary.md)
* [GDPR词汇表](aam-gdpr-glossary.md)
* [目的地的GDPR考虑事项](aam-gdpr-partners.md)
* [面向Audience Manager客户的GDPR就绪性指南](aam-gdpr-readiness.md)
* [数据管理](data-governance.md)
* [隐私和数据保留常见问题解答](../../faq/faq-privacy.md)