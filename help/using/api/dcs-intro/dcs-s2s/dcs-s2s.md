---
description: 服务器到服务器(S2S)API提供了代码和方法，允许您发送和接收DCS用户数据，并在自己的系统或应用程序中处理此信息。
seo-description: 服务器到服务器(S2S)API提供了代码和方法，允许您发送和接收DCS用户数据，并在自己的系统或应用程序中处理此信息。
seo-title: 用于服务器到服务器数据传输的 DCS API
solution: Audience Manager
title: 用于服务器到服务器数据传输的 DCS API
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 11%

---

# 用于服务器到服务器数据传输的 DCS API{#dcs-apis-for-server-to-server-data-transfers}

服务器到服务器([!UICONTROL S2S])[!DNL API]提供的代码和方法允许您发送和接收[!DNL DCS]用户数据，并在自己的系统或应用程序中处理此信息。

## 常见用例{#common-use-cases}

[!UICONTROL Server-to-server] 传输可以帮助您根据访客兴趣自定义登陆页面或其他交互。一些常见用例包括：

* 网站内个性化：通过根据访客所属的区段动态添加相关内容和行动要求，定制访客在您网站上的体验。
* 改进客户服务：通过服务器到服务器数据传输将[!DNL Audience Manager]区段导入[!DNL CRM]或其他系统。 此数据可以为呼叫服务或在线聊天操作员提供有关客户的相关个性化信息。

## 要求：用户ID和区域服务器名称 {#requirements}

[!UICONTROL DCS API]需要用户ID和区域ID才能验证和发出数据请求。

* 需要用户ID，因为您需要将数据与特定访客关联。
* 区域ID是将调用绑定到服务器名称所必需的，因为用户数据存储在地理位置最接近网站访客的数据中心。

## 快速入门 {#getting-started}

目前，本指南介绍如何：

* 从您已经作为[!DNL Audience Manager]客户接收的[!DNL DCS]文件中获取用户和区域ID。

* 如果使用[!DNL Visitor ID Service]，请获取用户ID和区域ID。
* 在拥有用户和区域ID后，调用[!DNL DCS]。

我们将在新方法可用时添加新方法。 请参阅以下章节，以开始使用。

* [从 DCS 响应中获取用户 ID 和区域](dcs-aam-ids.md)
* [通过用户ID获取用户ID和Experience Cloud...](dcs-mcid-ids.md)
* [进行服务器到服务器 DCS API 调用](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS API 参考](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

