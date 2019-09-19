---
description: 常见API问题和问题。
seo-description: 常见API问题和问题。
seo-title: API常见问题解答
solution: Audience Manager
title: API常见问题解答
uuid: 822ebf0-b50e-4f48-8021-dbfca2828b7c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API常见问题解答{#api-faq}

常见API问题和问题。

<!-- 

faq_api.xml

 -->

REST API文 [档包含有关特定方法](../api/rest-api-main/rest-api-main.md) 和代码示例的详细信息。

<br> 

**为什么[!UICONTROL DIL]使用和方法进行事[!UICONTROL GET]件调[!UICONTROL POST]用？**

[!UICONTROL DIL] 根据事 [!DNL Audience Manager] 件调用 `GET` 的查询 `POST` 字符串的长度，使用或方法将数据传递给。 默认情况下，此行为内置 `GET` 于 `POST` 和方法中。 这并非特有的 [!DNL Audience Manager]。

* [!UICONTROL DIL] 当URL包含2048个或 `GET` 更少字符时进行事件调用。 事 `GET` 件调用将URL中的数据作为查询字符串参数包含，这些参数作为键值对传入。

* [!UICONTROL DIL] 当URL包含超 `POST` 过2048个字符时进行事件调用。 事 `POST` 件调用包括请求主体中的数据。 [!UICONTROL DIL] 将数据放入键值对中，并将信息作为表单数据传递，而不是在URL查询字符串中传递。

尽管每种方法以不同的方式传递数据，但这不会影响功能。 例如，使用任一方法， [!DNL Audience Manager] 仍会向目标发送数据，ID同步正常工作，您可以根据数据信号创建特征。

<br> 

**我能[!UICONTROL REST API]做什么？**

使 [!UICONTROL REST API]用，您可以有计划地使用用户界面 [!DNL Audience Manager] 中提供的大多数功能和功能。

<br> 

**如何获取客户[!UICONTROL REST API]端ID和机密？**

请联系您的合作伙伴解决方案代表以获取 [!DNL API] 访问凭据。 我们的API使 [用OAuth 2.0](https://oauth.net/2/) 标准进行令牌身份验证、授权和续订。 有关更 [多信息，请参阅](../api/rest-api-main/aam-api-getting-started.md#oauth) OAuth身份验证。
