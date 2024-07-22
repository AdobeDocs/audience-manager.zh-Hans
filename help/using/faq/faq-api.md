---
description: 有关 API 的常见问题。
seo-description: Common API questions and issues.
seo-title: API FAQ
solution: Audience Manager
title: API 常见问题解答
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
exl-id: 9a51220e-3f53-4911-876b-16e968d44d0f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 100%

---

# API 常见问题解答{#api-faq}

有关 API 的常见问题。

<!-- 

faq_api.xml

 -->

[REST API](../api/rest-api-main/rest-api-main.md) 文档中包含有关特定方法和代码示例的详细信息。

<br> 

**[!UICONTROL DIL] 为何使用 [!UICONTROL GET] 和 [!UICONTROL POST] 方法发起事件调用？**

根据事件调用查询字符串的长度，[!UICONTROL DIL] 会通过 `GET` 或 `POST` 方法将数据传递到 [!DNL Audience Manager]。默认情况下，这属于 `GET` 和 `POST` 方法的内置行为。此行为并不是特定于 [!DNL Audience Manager] 的。

* 当 URL 包含的字符数少于或等于 2048 时，[!UICONTROL DIL] 会通过 `GET` 方法发起事件调用。`GET` 事件调用将数据作为查询字符串参数包含在 URL 中，并将其作为键值对传递。

* 当 URL 包含的字符数多于 2048 时，[!UICONTROL DIL] 会通过 `POST` 方法发起事件调用。`POST` 事件调用将数据包含在请求正文中。[!UICONTROL DIL] 将数据放入键值对中，并将信息作为表单数据传递，而不是将其放在 URL 查询字符串中传递。

虽然每种方法传递数据的方式有所不同，但这并不影响实际功能。例如，不论使用哪种方法，[!DNL Audience Manager] 都会将数据发送到目标，ID 同步都可以正常运行，并且您可以根据数据信号创建特征。

<br> 

**通过 [!UICONTROL REST API]，我可以执行哪些操作？**

通过 [!UICONTROL REST API]，您可以采用编程方式使用用户界面中提供的大多数 [!DNL Audience Manager] 功能和特性。

<br> 

**如何获取 [!UICONTROL REST API] 客户端 ID 和密码？**

请联系您的合作伙伴解决方案代表以获取 [!DNL API] 访问凭据。我们的 API 将使用 [OAuth 2.0](https://oauth.net/2/) 标准进行令牌身份验证、授权和续订。有关更多信息，请参阅 [OAuth 身份验证](../api/rest-api-main/aam-api-getting-started.md#oauth)。
