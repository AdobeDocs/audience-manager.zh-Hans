---
description: 服务器到服务器(S2S)API提供的代码和方法允许您发送和接收DCS用户数据，并在您自己的系统或应用程序中处理这些信息。
seo-description: 服务器到服务器(S2S)API提供的代码和方法允许您发送和接收DCS用户数据，并在您自己的系统或应用程序中处理这些信息。
seo-title: 用于服务器到服务器数据传输的DCS API
solution: Audience Manager
title: 用于服务器到服务器数据传输的DCS API
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 用于服务器到服务器数据传输的DCS API{#dcs-apis-for-server-to-server-data-transfers}

服务器到服务器([!UICONTROL S2S])提供 [!DNL API]的代码和方法允许您发送和接收用户数据，并在您自己的系统 [!UICONTROL DCS] 或应用程序中处理这些信息。

## 常见用例 {#common-use-cases}

[!UICONTROL Server-to-server] 转移可以帮助您根据访客兴趣自定义登录页面或其他交互。 一些常见用例包括：

* 现场个性化：通过根据访客所属的区段动态添加相关内容和行动号召，定制访客在您网站上的体验。
* 改进客户服务：通过 [!DNL Audience Manager] 服务器到服 [!DNL CRM] 务器的数据传输，将区段导入到或其他系统中。 这些数据可以为呼叫服务或在线聊天运营商提供有关客户的个性化信息。

## 要求：用户ID和区域服务器名称 {#requirements}

需要 [!UICONTROL DCS API] 用户ID和区域ID才能验证和发出数据请求。

* 用户ID是必需的，因为您需要将数据与特定访客关联。
* 区域ID需要将调用绑定回服务器名称，并且因为用户数据存储在地理位置最接近站点访问者的数据中心中。

## 快速入门 {#getting-started}

目前，本指南介绍如何：

* 从您已作为客户收到的文 [!UICONTROL DCS] 件中获取用户和区域ID [!DNL Audience Manager] 。

* 如果您使用，请获取用户和区域ID [!DNL Visitor ID Service]。
* 在您拥有用 [!UICONTROL DCS] 户和区域ID后向发出呼叫。

我们将在新方法可用时添加新方法。 请参阅以下部分，开始使用。

* [从DCS响应获取用户ID和区域](dcs-aam-ids.md)
* [通过Experience Cloud ID获取用户ID和区域……](dcs-mcid-ids.md)
* [发出服务器到服务器DCS API调用](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS API参考](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

