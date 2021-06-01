---
description: 概述如何使用Google Publisher Tags(GPT)集成Google Ad Manager。
seo-description: 概述如何在Adobe Audience Manager(AAM)中使用Google Publisher Tags(GPT)集成Google Ad Manager。
seo-title: 在Adobe Audience Manager(AAM)中使用Google Publisher Tags(GPT)集成Google Ad Manager
title: 使用Google Publisher Tags(GPT)集成Google Ad Manager
feature: 第三方集成
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# 使用Google Publisher Tags(GPT)集成[!DNL Google Ad Manager]（以前称为DFP）

下面列出的文章概述了如何使用Google Publisher Tags(GPT)集成[!DNL Google Ad Manager]。 您可以使用服务器端集成，也可以将GPT设置为目标，以将Audience Manager区段数据发送到[!DNL Google Ad Manager]。 您还将了解获取[!DNL Google Ad Manager]日志文件以在Audience Manager中报告所需的步骤。

* [使用Google Publisher Tags(GPT)将区段发送到Google Ad Manager的要求和方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   您可以通过客户端或服务器端集成将符合条件的区段发送到[!DNL Google Ad Manager]。 下面列出了有关这两种方法的要求和相关信息。

* [创建 GPT 目标](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   您可以通过客户端（浏览器端）集成或服务器端集成将符合条件的区段发送到[!DNL Google Ad Manager]。 如果选择客户端集成，则必须为Audience Manager中的Google Publisher Tags创建基于Cookie的目标。

* [修改 GPT setTargeting API 调用](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   在调用Google Publisher Tag .setTargeting方法之前，添加if语句以检查Audience ManagerCookie。

* [Google Publisher Tag 的 Audience Manager 代码](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt是一个JavaScript函数，用于读取Audience ManagerCookie数据，并将该信息发送到Google Publisher Tags。
