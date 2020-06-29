---
description: 如何使用Google Publisher Tags(GPT)集成DFP的概述。
seo-description: 概述如何在Adobe Audience Manager(AAM)中使用Google Publisher标记(GPT)集成DFP。
seo-title: 在Adobe Audience Manager(AAM)中使用Google Publisher标记(GPT)集成DFP
title: 使用 Google Publisher Tag (GPT) 集成 DFP
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 18%

---


# 使用 Google Publisher Tag (GPT) 集成 DFP

下面列出的文章概述了如何使用Google Publisher标记(GPT)集成DFP。 您可以使用服务器端集成，也可以将GPT设置为目标，以向DFP发送Audience Manager段数据。 您还将学习在Audience Manager中收录DFP日志文件以进行报告所需的步骤。

* [使用 Google Publisher Tags (GPT) 向 DFP 发送区段的要求和方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   您可以通过客户端或服务器端集成将符合条件的区段发送到DFP。 下面列出了两种方法的要求和相关信息。

* [创建 GPT 目标](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   您可以通过客户端（浏览器端）集成或服务器端集成将符合条件的区段发送到DFP。 如果您选择客户端集成，则必须为Audience Manager中的Google Publisher标记创建基于cookie的目标。

* [修改 GPT setTargeting API 调用](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   在调用Google Publisher标记。setTargeting方法之前，添加if语句以检查Audience Managercookie。

* [Google Publisher Tag 的 Audience Manager 代码](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt是一个JavaScript函数，它读取Audience Managercookie数据并将该信息发送到Google Publisher标记。
