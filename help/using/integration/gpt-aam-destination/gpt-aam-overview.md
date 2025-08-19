---
description: 有关如何使用Google Publisher Tags (GPT)集成Google Ad Manager的概述。
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: 使用Google Publisher Tag (GPT)集成Google Ad Manager
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# 使用Google发布商代码(GPT)集成[!DNL Google Ad Manager]（以前称为DFP）

下面列出的文章概述了如何使用Google发布商标记(GPT)集成[!DNL Google Ad Manager]。 您可以使用服务器端集成，也可以将GPT设置为将Audience Manager区段数据发送到[!DNL Google Ad Manager]的目标。 您还将了解摄取[!DNL Google Ad Manager]个日志文件以在Audience Manager中进行报告所需的步骤。

* [使用Google发布者标记(GPT)将区段发送到Google Ad Manager的要求和方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

  您可以通过客户端或服务器端集成将符合条件的区段发送到[!DNL Google Ad Manager]。 下面列出了这两种方法的要求和相关信息。

* [创建GPT目标](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

  您可以通过客户端（浏览器端）集成或服务器端集成将符合条件的区段发送到[!DNL Google Ad Manager]。 如果选择客户端集成，则必须在Audience Manager中为Google发布者标记创建基于Cookie的目标。

* [修改GPT setTargeting API调用](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

  在调用Audience Manager Publisher Tag .setTargeting方法之前，添加if语句以检查Google Cookie。

* [适用于Google发布商标记的Audience Manager代码](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

  AamGpt是一个JavaScript函数，可读取Audience Manager Cookie数据并将这些信息发送至Google发布商标记。
