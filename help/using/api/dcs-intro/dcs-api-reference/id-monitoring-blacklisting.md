---
description: DCS会监视接收到的ID并列入黑名单，这些ID在短时间内以异常高的速率发送。
keywords: id；监控；黑名单；s
seo-description: DCS会监视接收到的ID并列入黑名单，这些ID在短时间内以异常高的速率发送。
seo-title: ID监控和黑名单
solution: Audience Manager
title: ID监控和黑名单
uuid: 498e0316-cf1 b-43e9-88ba-338ee0 daf221
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# ID监控和黑名单

The [!UICONTROL DCS] monitors the IDs it receives and blacklists those that are being sent at an unusually high rate over a short period of time.

## 概述

To protect the Audience Manager infrastructure against malicious activity, the [!UICONTROL DCS] uses an advanced algorithm to monitor the IDs it receives. These can be [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), or [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). See [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md) for detailed explanations of the IDs supported by Audience Manager.

The [!UICONTROL DCS] monitors the frequency at which it receives these IDs to detect potential malicious activity. When the [!UICONTROL DCS] detects an unusually large amount of [!UICONTROL DCS] requests for any given ID in a short amount of time, that ID is blacklisted.

## 错误代码

You can identify blacklisted IDs by the error codes received from the [!UICONTROL DCS]. 您可能收到的错误代码有：

* 303：阻止的客户ID；
* 306：被阻止的已声明设备ID；
* 307：已阻止ID的配置文件操作。

See [DCS Error Codes, Messages, and Examples](dcs-error-codes.md) for details on the error codes that you may receive.

## 取消黑名单

黑名单ID不应在将来的请求中使用，因为它们会导致数据报告错误。The [!UICONTROL DCS] does not support un-blacklisting of IDs.

## 对ID同步的影响

[!UICONTROL DCS] 调用可以包括一种或多种类型的ID。如果该ID列入黑名单，包含单个ID的调用会被完全忽略，而在这种情况下不会同步ID。

When a multiple ID call also includes a blacklisted ID, the [!UICONTROL DCS] disregards the blacklisted ID and only uses the remaining, non-blacklisted IDs for synchronization.

## ID黑名单的原因和修复

列入黑名单的最常见的原因是客户基础结构与Audience Manager之间的集成不正确。在识别列入黑名单的ID时，请务必仔细查看Audience Manager集成。See **Implementation and Integration Guides** for detailed explanations of how you should configure Audience Manager to work with other Experience Cloud solutions or external systems.

Another frequent cause of blacklisted IDs are indexing bots (web crawlers), which generally cause increases in traffic, leading to the same IDs being sent to the [!UICONTROL DCS] multiple times. 如果识别索引机器人作为ID黑名单的原因，应限制机器人访问您的网站。

如果您很难确定集成问题，请不要犹豫，与客户支持联系。Prior to opening a support request, make sure to keep the `.har` `HTTP` archive of your browser ready. 此存档可帮助支持团队识别ID黑名单发生原因。