---
description: 介绍 Audience Manager 集成以及与消费者隐私和选择退出程序相关的公认最佳实践合规性。
seo-description: 介绍 Audience Manager 集成以及与消费者隐私和选择退出程序相关的公认最佳实践合规性。
seo-title: 数据隐私概述
solution: Audience Manager
title: 数据隐私概述
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 78%

---


# 数据隐私概述 {#data-privacy}

## 概述

The Data Privacy documentation describes [!DNL Audience Manager] integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.

[!DNL Audience Manager] 认识到消费者以及他们与之互动的网络品牌之间的关系的重要性。双方都受益于匿名数据元素的透明交换：

* 消费者可获得个性化内容、折扣产品选件和简化的用户体验。
* 品牌可获得支持多个在线业务模型的重要收入流。

In our continuing support of this model, [!DNL Audience Manager] remains committed to providing you with the tools to help support your ability to provide  transparency and control to your consumers, while delivering personalized ads subject to the [Online Behavioral Advertising (OBA) Self-Regulatory Principles](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## [!DNL GDPR] {#gdpr}

[《通用数据保护条例》(GDPR)](https://eugdpr.org/) 为欧盟成员国引入了几项新的数据隐私权，其中包括&#x200B;**访问权**&#x200B;和&#x200B;**被遗忘权**。This means that any [!DNL EU] citizen whose personal data has been collected by your business can request to access or delete their data at any time. 如果不能遵守这些要求，贵组织将面临数百万美元的罚款。

To comply with [!DNL GDPR], [!DNL Audience Manager] supports data access and delete [requests](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

[《加州消费者隐私法案》(CCPA)](https://www.caprivacy.org/about) 已于 2020 年 1 月 1 日生效，它为加利福尼亚州居民提供了有关其个人信息的新权利，并对某些在加利福尼亚州开展业务的实体施加了数据保护责任。

[!DNL CCPA] 为加利福尼亚州居民提供了新的数据隐私权，包括访问和删除其个人数据，以及了解其个人数据是否被出售或被透露（以及向谁出售或透露）的权利。为符合要求， [!DNL CCPA]支持 [!DNL Audience Manager] 访问 [!DNL CCPA] 和删除 [请求](data-privacy-requests.md)。

有关更多详细信息，请参阅 [Adobe 隐私中心](https://www.adobe.com/cn/privacy/opt-out.html)。

## 法规合规性 {#compliance}

[!DNL Audience Manager] 通过诸如 [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 之类的用于数据访问和删除请求的隐私工具，帮助您履行某些隐私法规规定的义务。

此服务提供了一个 [!DNL RESTful API] 和用户界面，可帮助您管理消费者数据请求。使用 [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)，您可以根据个人消费者的请求提交访问和删除个人数据的请求，从而帮助自动履行这部分合规义务。

数据访问和删除请求通过 [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 进行处理，而[选择退出请求](data-privacy-requests.md#opt-out-requests)当前则通过 [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) 提供支持。有关详细信息，请参阅[数据隐私请求](data-privacy-requests.md)。

## 相关概念 {#related-concepts}

* [数据隐私请求](data-privacy-requests.md)
* [同意管理](data-privacy-consent.md)
* [适用于 IAB TCF 的 Audience Manager 插件](aam-iab-plugin.md)
* [Audience Manager 标识符](data-privacy-ids.md)
* [CCPA 术语表](aam-ccpa-glossary.md)
* [GDPR 术语表](aam-gdpr-glossary.md)
* [与目标相关的 GDPR 注意事项](aam-gdpr-partners.md)
* [面向 Audience Manager 客户的 GDPR 准备指南](aam-gdpr-readiness.md)
* [数据管理](data-governance.md)
* [隐私和数据保留常见问题解答](../../faq/faq-privacy.md)