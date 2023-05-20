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
source-wordcount: '460'
ht-degree: 68%

---

# 数据隐私概述 {#data-privacy}

## 概述

資料隱私權檔案說明 [!DNL Audience Manager] 與消費者隱私權和選擇退出程式相關的公認最佳實務作法的整合與合規性。

[!DNL Audience Manager] 认识到消费者以及他们与之互动的网络品牌之间的关系的重要性。双方都受益于匿名数据元素的透明交换：

* 消费者可获得个性化内容、折扣产品选件和简化的用户体验。
* 品牌可获得支持多个在线业务模型的重要收入流。

我們持續支援此模型， [!DNL Audience Manager] 致力為您提供工具，協助您為消費者提供透明度和控制力，同時投放符合以下條件的個人化廣告： [線上行為廣告(OBA)自我監管原則](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## [!DNL GDPR] {#gdpr}

[《通用数据保护条例》(GDPR)](https://gdpr.eu/data-privacy/) 为欧盟成员国引入了几项新的数据隐私权，其中包括&#x200B;**访问权**&#x200B;和&#x200B;**被遗忘权**。這表示任何 [!DNL EU] 公司已收集其個人資料的公民可隨時要求存取或刪除其資料。 如果不能遵守这些要求，贵组织将面临数百万美元的罚款。

要符合 [!DNL GDPR]， [!DNL Audience Manager] 支援資料存取和刪除 [請求](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

[《加州消费者隐私法案》(CCPA)](https://www.caprivacy.org/about) 已于 2020 年 1 月 1 日生效，它为加利福尼亚州居民提供了有关其个人信息的新权利，并对某些在加利福尼亚州开展业务的实体施加了数据保护责任。

[!DNL CCPA] 为加利福尼亚州居民提供了新的数据隐私权，包括访问和删除其个人数据，以及了解其个人数据是否被出售或被透露（以及向谁出售或透露）的权利。要符合 [!DNL CCPA]， [!DNL Audience Manager] 支援 [!DNL CCPA] 存取與刪除 [請求](data-privacy-requests.md).

有关更多详细信息，请参阅 [Adobe 隐私中心](https://www.adobe.com/cn/privacy/opt-out.html)。

## 法规合规性 {#compliance}

[!DNL Audience Manager] 通过诸如 [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) 之类的用于数据访问和删除请求的隐私工具，帮助您履行某些隐私法规规定的义务。

此服务提供了一个 [!DNL RESTful API] 和用户界面，可帮助您管理消费者数据请求。使用 [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en)，您可以根据个人消费者的请求提交访问和删除个人数据的请求，从而帮助自动履行这部分合规义务。

雖然資料存取和刪除請求是透過Privacy Service處理， [選擇退出請求](data-privacy-requests.md#opt-out-requests) 目前透過 [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md). 有关详细信息，请参阅[数据隐私请求](data-privacy-requests.md)。

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
