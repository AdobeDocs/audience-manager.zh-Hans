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

[!DNL DCS]监视其接收的ID，并将短时间内以异常高速率发送的ID添加到阻止列表。

## 概述

为了保护Audience Manager基础架构免受恶意活动的侵害，[!DNL DCS]使用高级算法来监视其接收的ID。 这些参数可以是[!UICONTROL Data Provider Unique User ID]s([!UICONTROL CRM ID]s)、[!UICONTROL Audience Manager Unique User ID]s([!UICONTROL AAM UUID]s)或[!UICONTROL Experience Cloud ID]s([!UICONTROL ECID]s)。 有关Audience Manager支持的ID的详细说明，请参阅Audience Manager](../../../reference/ids-in-aam.md)中的[ ID索引。

[!DNL DCS]监视接收这些ID的频率，以检测潜在的恶意活动。 当[!DNL DCS]在短时间内检测到任何给定ID的异常大量[!DNL DCS]请求时，该ID将添加到阻止列表。

## 错误代码

您可以通过从[!DNL DCS]收到的错误代码来标识添加到阻止列表的ID。 您可能收到的错误代码为：

* 303:被阻止的客户ID;
* 306:已阻止声明的设备ID;
* 307:阻止ID的用户档案操作。

有关您可能收到的错误代码的详细信息，请参阅[DCS错误代码、消息和示例](dcs-error-codes.md)。

## 从阻止列表删除ID

已添加到阻止列表的ID不应用于将来的任何请求，因为它们将导致错误的报告。 [!DNL DCS]不支持从阻止列表删除ID。

## 对ID同步的影响

[!DNL DCS] 调用可以包括一个或多个类型的ID。如果将包含单个ID的调用添加到阻止列表，并且在这种情况下不进行ID同步，则将完全忽略该ID的调用。

当多个ID调用还包列入阻止列表含一个的ID时，[!DNL DCS]会忽略已拒绝的ID，只使用其余的允许的ID进行同步。

## ID的原因和修列入阻止列表复

将ID添加到阻止列表最常见的原因是客户基础架构和Audience Manager之间的不正确集成。 识别ID列入阻止列表时，请确保彻底检查Audience Manager集成。 请参见&#x200B;**实施和集成指南**，详细说明如何配置Audience Manager以与其他Experience Cloud解决方案或外部系统一起使用。

添加ID到阻止列表的另一个常见原因是索引机器人程序（Web爬虫程序），它通常导致流量增加，导致将同一ID多次发送到[!DNL DCS]。 如果将索引机器人程序标识为将ID添加到阻止列表的原因，则应限制对网站的bot访问。

如果您很难确定集成问题，请随时联系客户支持。 在打开支持请求之前，请确保您的浏览器的`.har` `HTTP`存档准备就绪。 此存档可帮助支持团队确定将ID添加到阻止列表的原因。