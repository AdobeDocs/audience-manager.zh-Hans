---
description: 如何使用Google Publisher Tags(GPT)集成Google Ad Manager的概述。
seo-description: 概述如何在Adobe Audience Manager(AAM)中使用Google Publisher标记(GPT)集成Google Ad Manager。
seo-title: 在Adobe Audience Manager(AAM)中使用Google Publisher标记(GPT)集成Google Ad Manager
title: 使用Google Publisher标记(GPT)集成Google Ad Manager
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Integrate [!DNL Google Ad Manager] (formerly DFP) using Google Publisher Tags (GPT)

下面列出的文章概述了如何使用Google Publisher [!DNL Google Ad Manager] 标记(GPT)进行集成。 您可以使用服务器端集成，也可以将GPT设置为目标以向其发送Audience Manager段数据 [!DNL Google Ad Manager]。 您还将学习在Audience Manager中收录日志 [!DNL Google Ad Manager] 文件以进行报告所需的步骤。

* [使用Google Publisher标记(GPT)将区段发送到Google Ad Manager的要求和方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   您可以通过客户端 [!DNL Google Ad Manager] 或服务器端集成将合格的细分发送给。 下面列出了两种方法的要求和相关信息。

* [创建 GPT 目标](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   您可以通过客户端( [!DNL Google Ad Manager] 浏览器端)集成或服务器端集成向客户端发送符合条件的区段。 如果您选择客户端集成，则必须为Audience Manager中的Google Publisher标记创建基于cookie的目标。

* [修改 GPT setTargeting API 调用](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   在调用Google Publisher标记。setTargeting方法之前，添加if语句以检查Audience Managercookie。

* [Google Publisher Tag 的 Audience Manager 代码](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt是一个JavaScript函数，它读取Audience Managercookie数据并将该信息发送到Google Publisher标记。
