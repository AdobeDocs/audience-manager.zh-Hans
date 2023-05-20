---
description: 概述如何使用 Google Publisher 标记（GPT）集成 Google 广告管理器。
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: 使用 Google Publisher 标记（GPT）集成 Google 广告管理器
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 8%

---

# 使用 Google Publisher 标记（GPT）集成 [!DNL Google Ad Manager] （以前称为 DFP）

下面列出的文章概述了如何使用 Google 发布器标记（GPT）集成 [!DNL Google Ad Manager] 。 您可以使用服务器端集成，也可以将 GPT 设置为将 Audience Manager 区段数据发送到 [!DNL Google Ad Manager] 的目标。 您还将了解为 Audience Manager 中的报告插入 [!DNL Google Ad Manager] 日志文件所需的步骤。

* [使用 Google Publisher 标记（GPT）将区段发送到 Google 广告管理器的要求和方法](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   您可以通过客户端或通过服务器端集成发送合格的区段 [!DNL Google Ad Manager] 。 以下列出了有关这两种方法的要求和相关信息。

* [创建 GPT 目标](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   您可以通过客户端（浏览器端）集成或服务器端集成发送合格的区段 [!DNL Google Ad Manager] 。 如果您选择客户端集成，则必须在 Audience Manager 中为 Google Publisher 标记创建基于 Cookie 的目标。

* [修改 GPT setTargeting API 调用](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   在调用 Google Publisher Tag setTargeting 方法之前，添加一个 if 语句以检查 Audience Manager cookie。

* [Google Publisher Tag 的 Audience Manager 代码](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt 是读取 Audience Manager Cookie 数据并将该信息发送到 Google Publisher 标记的 JavaScript 函数。
