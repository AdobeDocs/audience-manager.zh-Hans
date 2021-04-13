---
description: 如何使用Google Publisher标记(GPT)集成Google广告管理器的概述。
seo-description: 概述如何使用Adobe Audience Manager(AAM)中的Google Publisher标记(GPT)集成Google Ad Manager。
seo-title: 在Adobe Audience Manager(AAM)中使用Google Publisher标记(GPT)集成Google Ad Manager
title: 使用Google Publisher标记(GPT)集成Google广告管理器
feature: 第三方集成
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# 使用Google Publisher标签(GPT)集成[!DNL Google Ad Manager]（以前称为DFP）

下面列出的文章概述了如何使用Google Publisher标记(GPT)集成[!DNL Google Ad Manager]。 您可以使用服务器端集成，也可以将GPT设置为目标，以将Audience Manager段数据发送到[!DNL Google Ad Manager]。 您还将学习在Audience Manager中收录[!DNL Google Ad Manager]日志文件以进行报告所需的步骤。

* [使用Google Publisher标记(GPT)将区段发送到Google Ad Manager的要求和方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   您可以通过客户端或服务器端集成将限定的区段发送到[!DNL Google Ad Manager]。 以下列出了两种方法的要求和相关信息。

* [创建 GPT 目标](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   您可以通过客户端（浏览器端）集成或服务器端集成将限定的区段发送到[!DNL Google Ad Manager]。 如果您选择客户端集成，则必须在Audience Manager中为Google Publisher标记创建基于Cookie的目标。

* [修改 GPT setTargeting API 调用](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   在调用Google Publisher标记.setTargeting方法之前，添加if语句以检查Audience ManagerCookie。

* [Google Publisher Tag 的 Audience Manager 代码](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt是一个JavaScript函数，它读取Audience Manager Cookie数据并将该信息发送到Google Publisher Tags。
