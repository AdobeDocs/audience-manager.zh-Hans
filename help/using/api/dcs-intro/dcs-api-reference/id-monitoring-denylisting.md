---
description: DCS监视其接收的ID，并将短时间内以异常高速率发送的ID添加到拒绝列表。
keywords: id;monitoring;dcs
seo-description: DCS监视其接收的ID，并将短时间内以异常高速率发送的ID添加到拒绝列表。
seo-title: ID监控和密码列表
solution: Audience Manager
title: ID监控和密码列表
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# ID监控和密码列表

监 [!UICONTROL DCS] 视其接收的ID，并将短时间内以异常高速率发送的ID添加到拒绝列表。

## 概述

为了保护受众管理器基础架构免受恶意活动的侵 [!UICONTROL DCS] 害，该管理器使用高级算法来监视其接收的ID。 这些 [!UICONTROL Data Provider Unique User ID]可以[!UICONTROL CRM ID]是s 、 [!UICONTROL Audience Manager Unique User ID]s[!UICONTROL AAM UUID]s或 [!UICONTROL Experience Cloud ID][!UICONTROL ECID]s s。 请参 [阅受众管理器中的ID索引](../../../reference/ids-in-aam.md) ，以详细了解受众管理器支持的ID。

监 [!UICONTROL DCS] 视接收这些ID的频率，以检测潜在的恶意活动。 当在 [!UICONTROL DCS] 很短的时间内检测到任何 [!UICONTROL DCS] 给定ID的异常大量请求时，该ID将添加到拒绝列表。

## 错误代码

您可以通过从中接收的错误代码来标识添加到拒绝列表的ID [!UICONTROL DCS]。 您可能收到的错误代码为：

* 303: 被阻止的客户ID;
* 306: 已阻止声明的设备ID;
* 307: 阻止ID的用户档案操作。

有关 [您可能收到的错误代码的详细信息](dcs-error-codes.md) ，请参阅DCS错误代码、消息和示例。

## 从拒绝列表删除ID

为拒绝列表而添加的ID不应用于将来的任何请求，因为它们将导致错误的报告。 不支持 [!UICONTROL DCS] 从拒绝列表中删除ID。

## 对ID同步的影响

[!UICONTROL DCS] 调用可以包括一个或多个类型的ID。 如果将包含单个ID的调用添加到拒绝列表，并且在这种情况下不进行ID同步，则将完全忽略该ID的调用。

当多个ID调用还包括拒绝列出的ID时， [!UICONTROL DCS] 将忽略拒绝的ID，并仅使用其余的允许的ID进行同步。

## ID密码列表的原因和修复

添加ID以拒绝列表的最常见原因是客户基础架构与受众管理器之间的集成不正确。 在您识别已拒绝列出的ID时，请确保彻底检查受众管理器集成。 请参 **阅实施和集成指南** ，详细说明如何配置受众管理器以与其他Experience Cloud解决方案或外部系统结合使用。

为拒绝列表而添加ID的另一个常见原因是索引程序（Web爬虫程序），它通常导致流量增加，导致将同一ID多次发 [!UICONTROL DCS] 送到。 如果将索引机器人程序标识为添加ID以拒绝列表的原因，则应限制对网站的bot访问。

如果您很难确定集成问题，请随时联系客户支持。 在打开支持请求之前，请确保您的浏 `.har` 览器 `HTTP` 的存档准备就绪。 此存档可帮助支持团队确定为何将ID添加到拒绝列表。