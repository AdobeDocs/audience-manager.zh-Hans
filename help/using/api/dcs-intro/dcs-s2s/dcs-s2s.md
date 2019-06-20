---
description: 服务器到服务器(S2S) API提供的代码和方法允许您发送和接收DCS用户数据，并在您自己的系统或应用程序中处理此信息。
seo-description: 服务器到服务器(S2S) API提供的代码和方法允许您发送和接收DCS用户数据，并在您自己的系统或应用程序中处理此信息。
seo-title: 用于服务器到服务器数据传输的DCS API
solution: Audience Manager
title: 用于服务器到服务器数据传输的DCS API
uuid: 8c369166-c8 a7-46b0-9913-4c027 f5 b1 df9
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# DCS APIs for Server-to-Server Data Transfers{#dcs-apis-for-server-to-server-data-transfers}

Server-to-server ([!UICONTROL S2S]) [!DNL API]s provide code and methods that let you send and receive [!UICONTROL DCS] user data and work with this information in your own systems or applications.

## Common Use Cases {#common-use-cases}

[!UICONTROL Server-to-server] 传输可帮助您根据访客兴趣自定义登陆页面或其他互动。一些常见用例包括：

* 现场个性化：根据访客所属的细分动态添加相关内容和行动号召，定制访客的体验。
* Improve customer service: Import [!DNL Audience Manager] segments into a [!DNL CRM] or other system through a server-to-server data transfer. 此数据可为呼叫服务或线上聊天运营商提供有关客户的相关、个性化信息。

## Requirements: User IDs and Regional Server Names {#requirements}

The [!UICONTROL DCS API] requires user IDs and region IDs to validate and make data requests.

* 用户ID是必需的，因为您需要将数据与特定访客相关联。
* 需要区域ID才能将调用绑定回服务器名称，而且用户数据存储在地理上最接近站点访客的数据中心中。

## 快速入门 {#getting-started}

当前，本指南介绍了如何：

* Get the user and region IDs from the [!UICONTROL DCS] files you may already receive as an [!DNL Audience Manager] customer.

* Get the user and region IDs if you use the [!DNL Visitor ID Service].
* Make calls to the [!UICONTROL DCS] after you have the user and region ID.

我们将在新方法可用时添加新方法。请参阅以下部分以开始。

* [通过DCS响应获取用户ID和区域](dcs-aam-ids.md)
* [通过Experience Cloud ID获取用户ID和区域…](dcs-mcid-ids.md)
* [进行服务器到服务器DCS API调用](dcs-s2s-calls.md)

>[!MORE_ LIKE_ This]
>
>* [DCS API参考](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

