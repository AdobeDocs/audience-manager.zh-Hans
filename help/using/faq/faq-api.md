---
description: 常见API问题和问题。
seo-description: 常见API问题和问题。
seo-title: API常见问题解答
solution: Audience Manager
title: API常见问题解答
uuid: 8222epf0-b50 e-4f48-8021-dbfca2828 b7 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API FAQ{#api-faq}

常见API问题和问题。

<!-- 

faq_api.xml

 -->

[REST API](../api/rest-api-main/rest-api-main.md) 文档包含有关特定方法和代码示例的详细信息。

<br> 

**为什么[!UICONTROL DIL]要使用[!UICONTROL GET]和[!UICONTROL POST]方法进行事件调用？**

[!UICONTROL DIL] 根据事件调用的查询字符串的长度将数据传递 [!DNL Audience Manager] 给某个 `GET` 或 `POST` 方法。This behavior is built in to `GET` and `POST` methods by default. It is not specific to [!DNL Audience Manager].

* [!UICONTROL DIL] 当URL包含2048个或 `GET` 更少字符时进行事件调用。`GET` 事件调用包含URL中的数据，查询字符串参数作为键值对传入。

* [!UICONTROL DIL] 当URL包含2048 `POST` 个以上的字符时进行事件调用。`POST` 事件调用包含请求正文中的数据。[!UICONTROL DIL] 将数据放入关键值对，并将信息作为表单数据而不是URL查询字符串传递。

尽管每种方法都以不同的方式传递数据，但这并不影响功能。For example, with either method, [!DNL Audience Manager] still sends data to destinations, ID syncs works normally, and you can create traits from data signals.

<br> 

**我可以[!UICONTROL REST API]做什么？**

[!UICONTROL REST API]使用s，您可以使用用户界面中提供的大多数 [!DNL Audience Manager] 功能和功能进行编程工作。

<br> 

**如何获取[!UICONTROL REST API]客户端ID和机密？**

Contact your Partner Solutions representative to obtain [!DNL API] access credentials. Our APIs use [OAuth 2.0](https://oauth.net/2/) standards for token authentication, authorization, and renewal. See [OAuth Authentication](../api/rest-api-main/aam-api-getting-started.md#oauth) for more information.
