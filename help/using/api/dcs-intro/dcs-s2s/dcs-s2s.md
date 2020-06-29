---
description: 服务器到服务器(S2S)API提供了代码和方法，使您能够发送和接收DCS用户数据，并在您自己的系统或应用程序中处理这些信息。
seo-description: 服务器到服务器(S2S)API提供了代码和方法，使您能够发送和接收DCS用户数据，并在您自己的系统或应用程序中处理这些信息。
seo-title: 用于服务器到服务器数据传输的 DCS API
solution: Audience Manager
title: 用于服务器到服务器数据传输的 DCS API
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 11%

---


# 用于服务器到服务器数据传输的 DCS API{#dcs-apis-for-server-to-server-data-transfers}

服务器到服务器([!UICONTROL S2S]) [!DNL API]提供的代码和方法允许您发送和接收用户 [!DNL DCS] 数据，并在自己的系统或应用程序中处理此信息。

## 常见用例 {#common-use-cases}

[!UICONTROL Server-to-server] 传输可帮助您根据登陆页兴趣自定义访客或其他交互。 一些常见用例包括：

* 在线个性化： 根据访客所属的细分动态添加相关内容和行动号召，从而定制客户在您网站上的体验。
* 改善客户服务： 通过 [!DNL Audience Manager] 服务器到服 [!DNL CRM] 务器的数据传输，将区段导入到或其他系统中。 这些数据可以为呼叫服务或在线聊天运营商提供有关客户的个性化信息。

## 要求： 用户ID和区域服务器名称 {#requirements}

需要 [!UICONTROL DCS API] 用户ID和区域ID才能验证和发出数据请求。

* 用户ID是必需的，因为您需要将数据与特定访客关联。
* 区域ID需要将调用绑定到服务器名称，并且因为用户数据存储在地理位置最接近站点访客的数据中心中。

## 快速入门 {#getting-started}

目前，本指南介绍如何：

* 从您已作为客户收到的 [!DNL DCS] 文件中获取用户和区域 [!DNL Audience Manager] ID。

* 如果使用，请获取用户和区域ID [!DNL Visitor ID Service]。
* 在您拥有用 [!DNL DCS] 户和区域ID后拨叫。

我们将在新方法可用时添加它们。 请参阅以下部分，开始使用。

* [从 DCS 响应中获取用户 ID 和区域](dcs-aam-ids.md)
* [通过Experience CloudID获取用户ID和区域……](dcs-mcid-ids.md)
* [进行服务器到服务器 DCS API 调用](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS API 参考](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

