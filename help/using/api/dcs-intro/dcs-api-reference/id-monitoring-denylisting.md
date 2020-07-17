---
description: DCS监视它接收的ID，并将短时间内以异常高速率发送的ID添加到阻止列表。
keywords: id;monitoring;dcs
seo-description: DCS监视它接收的ID，并将短时间内以异常高速率发送的ID添加到阻止列表。
seo-title: ID监控和列入阻止列表
solution: Audience Manager
title: ID监控和列入阻止列表
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# ID监控和列入阻止列表

监 [!DNL DCS] 视其接收的ID，并将短时间内以异常高速率发送的ID添加到阻止列表。

## 概述

为了保护Audience Manager基础架构免受恶意活动的 [!DNL DCS] 侵扰，用户使用高级算法来监视其接收的ID。 这些 [!UICONTROL Data Provider Unique User ID]可以[!UICONTROL CRM ID]是s 、 [!UICONTROL Audience Manager Unique User ID]s[!UICONTROL AAM UUID]s或 [!UICONTROL Experience Cloud ID][!UICONTROL ECID]s s。 请参 [阅Audience Manager中的ID索引](../../../reference/ids-in-aam.md) ，以详细了解Audience Manager支持的ID。

监 [!DNL DCS] 视接收这些ID的频率，以检测潜在的恶意活动。 当在 [!DNL DCS] 很短的时间内检测到任 [!DNL DCS] 何给定ID的异常大量请求时，该ID将添加到阻止列表。

## 错误代码

您可以通过从中接收的错误代码来标识添加到阻止列表的ID [!DNL DCS]。 您可能收到的错误代码为：

* 303: 被阻止的客户ID;
* 306: 已阻止声明的设备ID;
* 307: 阻止ID的用户档案操作。

有关 [您可能收到的错误代码的详细信息](dcs-error-codes.md) ，请参阅DCS错误代码、消息和示例。

## 从阻止列表删除ID

已添加到阻止列表的ID不应用于将来的任何请求，因为它们将导致错误的报告。 不支持 [!DNL DCS] 从阻止列表中删除ID。

## 对ID同步的影响

[!DNL DCS] 调用可以包括一个或多个类型的ID。 如果将包含单个ID的调用添加到阻止列表，并且在这种情况下不进行ID同步，则将完全忽略该ID的调用。

当多个ID调用还包含一个列入阻止列表的ID时，该ID会 [!DNL DCS] 忽略被拒绝的ID，并仅使用其余的允许的ID进行同步。

## ID的原因和修列入阻止列表复

将ID添加到阻止列表最常见的原因是客户基础架构和Audience Manager之间的不正确集成。 识别ID列入阻止列表时，请确保彻底检查Audience Manager集成。 请参 **阅实施和集成指南** ，详细说明如何配置Audience Manager以与其他Experience Cloud解决方案或外部系统一起使用。

阻止列表添加ID的另一个常见原因是索引机器人程序（Web爬虫程序），它通常导致流量增加，导致将同一ID多次发 [!DNL DCS] 送到。 如果将索引机器人程序标识为将ID添加到阻止列表的原因，则应限制对网站的bot访问。

如果您很难确定集成问题，请随时联系客户支持。 在打开支持请求之前，请确保您的浏 `.har` 览器 `HTTP` 的存档准备就绪。 此存档可帮助支持团队确定将ID添加到阻止列表的原因。