---
description: 概述如何使用Google Publisher标签(GPT)集成DFP。
seo-description: 概述如何使用Adobe Audience Manager(AAM)中的Google Publisher标签(GPT)集成DFP。
seo-title: 在Adobe Audience Manager(AAM)中使用Google Publisher标签(GPT)集成DFP
title: 使用Google Publisher标签(GPT)集成DFP
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# 使用Google Publisher标签(GPT)集成DFP

以下列出的文章概述了如何使用Google Publisher标签(GPT)集成DFP。您可以使用服务器端集成，也可以将GPT设置为目标，以将Audience Manager区段数据发送到DFP。您还将了解在Audience Manager中收录DFP日志文件所需的步骤。

* [使用 Google Publisher Tags (GPT) 向 DFP 发送区段的要求和方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   您可以通过客户端或通过服务器端集成将合格的区段发送到DFP。以下列出了有关两种方法的要求及相关信息。

* [创建GPT目标](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   您可以通过客户端(浏览器端)集成或服务器端集成将合格的区段发送到DFP。如果选择客户端集成，则必须在Audience Manager中为Google Publisher标记创建基于cookie的目标。

* [修改GPT Settargeting API调用](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   添加if语句以检查Audience Manager cookies，然后调用Google Publisher标记. setTargeting方法。

* [Google Publisher标签的Audience Manager代码](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AMAGPT是一个JavaScript函数，它读取Audience Manager cookie数据并将该信息发送到Google Publisher标记。
