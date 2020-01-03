---
description: 介绍Audience manager集成以及遵守与消费者隐私和选择退出程序相关的公认最佳实践。
seo-description: 介绍Audience manager集成以及遵守与消费者隐私和选择退出程序相关的公认最佳实践。
seo-title: 数据隐私概述
solution: Audience Manager
title: 数据隐私概述
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: f8184dfccdb7b5cbc3ace67831d988dd8061ea38

---


# 数据隐私概述 {#data-privacy}

## 概述

数据隐私文档描述了Audience manager的集成以及与消费者隐私和选择退出程序相关的公认最佳做法的合规性。

Audience manager认识到消费者与其互动的在线品牌之间关系的重要性。 双方都受益于匿名数据元素的透明交换：

* 消费者可获得个性化内容、折扣产品推广信息和简化的用户体验。
* 品牌可获得支持多种在线业务模型的重要收入流。

在我们对此模型的持续支持中，Audience manager继续致力于为您提供帮助支持您为消费者提供透明度和控制的能力的工具，同时根据在线行为广告( [Online Behavior Advertising, OBA)自律原则提供个性化广告](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/)。

 

一般 [数据保护规定(GDPR)](https://eugdpr.org/) 为欧盟成员国引入了若干新的数据隐私权，包括访问权 **、被** 遗忘权 ****。 这意味着，您的企业已收集个人数据的任何欧盟公民均可请求随时访问或删除其数据。 如果不能遵守这些要求，您的组织可能会遭受数百万美元的罚款。

为符合GDPR,Audience manager支持数据访问和删除 [请求](data-privacy-requests.md)。

2020 [年1月1日生效的《加利福尼亚消费者隐私法》(California Consumer Privacy Act, CCPA)](https://www.caprivacy.org/about)，为加利福尼亚州居民提供了有关其个人信息的新权利，并对在加利福尼亚从事业务的某些实体负有数据保护责任。

CCPA为加利福尼亚州居民提供了新的数据隐私权，包括访问和删除其个人数据以及了解其个人数据是出售还是披露（以及向谁）的权利。 为了符合CCPA,Audience manager支持CCPA访问和删除请 [求](data-privacy-requests.md)。

有关更多 [详细信息，请参阅Adobe隐私中心](https://www.adobe.com/privacy/opt-out.html) 。

## 法规合规性 {#compliance}

Audience manager通过 [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) （用于数据访问和删除请求）等隐私工具帮助您遵守某些隐私法规规定的义务。

此服务提供一个 [!DNL RESTful API] 用户界面，帮助您管理消费者数据请求。 使用隐 [私服务](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)，您可以根据个人消费者的请求提交访问和删除个人数据的请求，从而帮助自动执行这部分合规义务。

虽然数据访问和删除请求是通过隐私 [服务处理的](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), [但](data-privacy-requests.md#opt-out-requests) DCS API当前支持退出请求 [](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)。 有关详 [细信息，请参阅数据](data-privacy-requests.md) 隐私请求。

## 相关概念 {#related-concepts}

* [数据隐私请求](data-privacy-requests.md)
* [同意管理](data-privacy-consent.md)
* [适用于 IAB TCF 的 Audience Manager 插件](aam-iab-plugin.md)
* [Audience manager标识符](data-privacy-ids.md)
* [CCPA词汇表](aam-ccpa-glossary.md)
* [GDPR词汇表](aam-gdpr-glossary.md)
* [目标的GDPR注意事项](aam-gdpr-partners.md)
* [面向Audience Manager客户的GDPR就绪性指南](aam-gdpr-readiness.md)
* [数据管理](data-governance.md)
* [隐私和数据保留常见问题解答](../../faq/faq-privacy.md)