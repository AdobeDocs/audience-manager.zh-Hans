---
description: DCS监视其接收的ID，并列出在短时间内以异常高的速率发送的ID。
keywords: id；监控；黑名单；dcs
seo-description: DCS监视其接收的ID，并列出在短时间内以异常高的速率发送的ID。
seo-title: ID监控和黑名单
solution: Audience Manager
title: ID监控和黑名单
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# ID监控和黑名单

监 [!UICONTROL DCS] 视其接收的ID，并列出在短时间内以异常高的速率发送的ID。

## 概述

为了保护Audience manager基础结构免受恶意活动的侵害，该 [!UICONTROL DCS] 基础架构使用高级算法来监视其接收的ID。 这些可 [!UICONTROL Data Provider Unique User ID]以是[!UICONTROL CRM ID]s(s)、 [!UICONTROL Audience Manager Unique User ID]s([!UICONTROL AAM UUID]s) [!UICONTROL Experience Cloud ID]或[!UICONTROL ECID]s(s)。 有关 [Audience manager支持的ID的详细说明，请参阅Audience Manager中的ID索引](../../../reference/ids-in-aam.md) 。

监 [!UICONTROL DCS] 视接收这些ID的频率，以检测潜在的恶意活动。 当在 [!UICONTROL DCS] 很短的时间内检测到任何给 [!UICONTROL DCS] 定ID的异常大量请求时，该ID将被列入黑名单。

## 错误代码

您可以通过从中接收的错误代码来标识列入黑名单的ID [!UICONTROL DCS]。 您可能收到的错误代码是：

* 303:被阻止的客户ID;
* 306:已阻止声明的设备ID;
* 307:已阻止ID的配置文件操作。

有关 [您可能收到的错误代码的详细信息](dcs-error-codes.md) ，请参阅DCS错误代码、消息和示例。

## 非黑名单

列入黑名单的ID不应用于将来的任何请求，因为它们会导致数据报告错误。 不 [!UICONTROL DCS] 支持ID的非黑名单。

## 对ID同步的影响

[!UICONTROL DCS] 调用可以包括一个或多个类型的ID。 如果该ID被列入黑名单，并且在这种情况下不进行ID同步，则包含单个ID的调用将被完全忽略。

当多个ID调用还包含列入黑名单的ID时， [!UICONTROL DCS] 将忽略列入黑名单的ID，并仅使用其余未列入黑名单的ID进行同步。

## ID黑名单的原因和修复

ID被列入黑名单的最常见原因是客户基础架构与Audience manager之间的集成不正确。 识别列入黑名单的ID时，请务必彻底检查Audience manager集成。 有关 **** 如何配置Audience Manager以与其他Experience cloud解决方案或外部系统结合使用的详细说明，请参阅实施和集成指南。

列入黑名单的ID的另一个常见原因是索引机器人（Web爬虫程序），它通常导致流量增加，导致将同一ID多次发 [!UICONTROL DCS] 送到。 如果将索引机器人标识为ID黑名单的原因，则应限制对网站的机器人访问。

如果您很难确定集成问题，请随时联系客户支持。 在打开支持请求之前，请确保您的浏览器 `.har` 的存 `HTTP` 档保持就绪。 此存档可帮助支持团队确定ID黑名单的发生原因。