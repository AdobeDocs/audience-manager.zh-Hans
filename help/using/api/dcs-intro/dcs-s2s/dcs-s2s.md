---
description: 服务器到服务器(S2S) API提供了代码和方法，允许您发送和接收DCS用户数据，并在您自己的系统或应用程序中处理这些信息。
seo-description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-title: DCS APIs for Server-to-Server Data Transfers
solution: Audience Manager
title: 用于服务器到服务器数据传输的DCS API
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# 用于服务器到服务器数据传输的DCS API{#dcs-apis-for-server-to-server-data-transfers}

服务器到服务器([!UICONTROL S2S]) [!DNL API]提供了代码和方法，允许您发送和接收[!DNL DCS]用户数据，并在您自己的系统或应用程序中处理这些信息。

## 常见用例 {#common-use-cases}

[!UICONTROL Server-to-server]传输可帮助您根据访客兴趣自定义登陆页面或其他交互。 一些常见用例包括：

* 现场个性化：根据访客所属的区段动态添加相关内容和行动号召，从而定制访客在您网站上的体验。
* 改善客户服务：通过服务器到服务器数据传输将[!DNL Audience Manager]区段导入[!DNL CRM]或其他系统。 该数据可为呼叫服务或在线聊天运营商提供有关客户的个性化相关信息。

## 要求：用户ID和区域服务器名称 {#requirements}

[!UICONTROL DCS API]需要用户ID和区域ID才能验证和发出数据请求。

* 需要用户ID，因为您需要将数据与特定访客关联。
* 要将调用绑定回服务器名称，并且用户数据存储在地理位置最接近网站访客的数据中心，因此需要区域ID。

## 入门指南 {#getting-started}

目前，本指南介绍如何：

* 从可能已作为[!DNL DCS]客户收到的[!DNL Audience Manager]文件中获取用户和区域ID。

* 如果您使用[!DNL Visitor ID Service]，则获取用户和区域ID。
* 在拥有用户和区域ID后调用[!DNL DCS]。

我们将添加新方法，使它们可用。 请参阅以下部分以开始使用。

* [从DCS响应中获取用户ID和区域](dcs-aam-ids.md)
* [通过Experience Cloud ID获取用户ID和区域……](dcs-mcid-ids.md)
* [进行服务器到服务器DCS API调用](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS API引用](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)
