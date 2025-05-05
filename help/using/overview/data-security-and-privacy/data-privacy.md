---
description: 介绍 Audience Manager 集成以及与消费者隐私和选择退出程序相关的公认最佳实践合规性。
seo-description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-title: Data Privacy Overview
solution: Audience Manager
title: 数据隐私概述
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: Data Governance & Privacy
exl-id: 051de369-e762-49fb-b65f-6faf94db48a4
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 52%

---

# 数据隐私概述 {#data-privacy}

## 概述

数据隐私文档描述了[!DNL Audience Manager]集成以及与消费者隐私和选择退出程序相关的公认最佳实践合规性。

[!DNL Audience Manager]认识到消费者和他们与之互动的在线品牌之间的关系的重要性。 双方都受益于匿名数据元素的透明交换：

* 消费者可获得个性化内容、折扣产品选件和简化的用户体验。
* 品牌可获得支持多个在线业务模型的重要收入流。

在我们对这一模型的持续支持下，[!DNL Audience Manager]仍将致力于为您提供工具，以帮助支持您为消费者提供透明度和控制的能力，同时根据[在线行为Advertising (OBA)自我监管原则](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/)提供个性化广告。

## [!DNL GDPR] {#gdpr}

[《通用数据保护条例》(GDPR)](https://gdpr.eu/data-privacy/) 为欧盟成员国引入了几项新的数据隐私权，其中包括&#x200B;**访问权**&#x200B;和&#x200B;**被遗忘权**。这意味着您的企业已收集其个人数据的任何[!DNL EU]公民都可以随时请求访问或删除其数据。 如果不能遵守这些要求，贵组织将面临数百万美元的罚款。

为了符合[!DNL GDPR]，[!DNL Audience Manager]支持数据访问和删除[请求](data-privacy-requests.md)。

## [!DNL CCPA] {#ccpa}

[《加州消费者隐私法案》(CCPA)](https://www.caprivacy.org/about) 已于 2020 年 1 月 1 日生效，它为加利福尼亚州居民提供了有关其个人信息的新权利，并对某些在加利福尼亚州开展业务的实体施加了数据保护责任。

[!DNL CCPA]为加利福尼亚州居民提供了新的数据隐私权，包括访问和删除其个人数据的权利，以及知晓其个人数据是否被出售或披露（以及向谁出售或披露）的权利。 为了符合[!DNL CCPA]，[!DNL Audience Manager]支持[!DNL CCPA]访问和删除[请求](data-privacy-requests.md)。

有关更多详细信息，请参阅 [Adobe 隐私中心](https://www.adobe.com/cn/privacy/opt-out.html)。

## 法规合规性 {#compliance}

[!DNL Audience Manager]通过诸如[Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hans)之类的用于数据访问和删除请求的隐私工具，帮助您履行某些隐私法规规定的义务。

此服务提供了一个 [!DNL RESTful API] 和用户界面，可帮助您管理消费者数据请求。使用 [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hans)，您可以根据个人消费者的请求提交访问和删除个人数据的请求，从而帮助自动履行这部分合规义务。

在通过Privacy Service处理数据访问和删除请求时，当前通过[DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)支持[选择退出请求](data-privacy-requests.md#opt-out-requests)。 有关详细信息，请参阅[数据隐私请求](data-privacy-requests.md)。

## 相关概念 {#related-concepts}

* [数据隐私请求](data-privacy-requests.md)
* [同意管理](data-privacy-consent.md)
* [适用于 IAB TCF 的 Audience Manager 插件](aam-iab-plugin.md)
* [Audience Manager标识符](data-privacy-ids.md)
* [CCPA 术语表](aam-ccpa-glossary.md)
* [GDPR 术语表](aam-gdpr-glossary.md)
* [与目标相关的 GDPR 注意事项](aam-gdpr-partners.md)
* [面向 Audience Manager 客户的 GDPR 准备指南](aam-gdpr-readiness.md)
* [数据管理](data-governance.md)
* [隐私和数据保留常见问题解答](../../faq/faq-privacy.md)
