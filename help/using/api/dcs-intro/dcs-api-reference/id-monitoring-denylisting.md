---
description: DCS会监控收到的ID，并将那些在短时间内以异常高的速率发送的ID添加到阻止列表。
keywords: id；监控；dcs
seo-description: DCS会监控收到的ID，并将那些在短时间内以异常高的速率发送的ID添加到阻止列表。
seo-title: ID监控和列入阻止列表
solution: Audience Manager
title: ID监控和列入阻止列表
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 0%

---

# ID监控和列入阻止列表

[!DNL DCS]会监控收到的ID，并将那些在短时间内以异常高的速率发送的ID添加到阻止列表。

## 概述

为了保护Audience Manager基础架构免受恶意活动的侵害，[!DNL DCS]使用高级算法来监视其收到的ID。 这些参数可以是[!UICONTROL Data Provider Unique User ID]s([!UICONTROL CRM ID]s)、[!UICONTROL Audience Manager Unique User ID]s([!UICONTROL AAM UUID]s)或[!UICONTROL Experience Cloud ID]s([!UICONTROL ECID]s)。 请参阅[Audience Manager](../../../reference/ids-in-aam.md)中的ID索引，以详细说明Audience Manager支持的ID。

[!DNL DCS]可监视其接收这些ID的频率，以检测潜在的恶意活动。 当[!DNL DCS]在短时间内检测到任意给定ID的异常大量[!DNL DCS]请求时，该ID会添加到阻止列表。

## 错误代码

您可以通过从[!DNL DCS]收到的错误代码来识别添加到阻止列表的ID。 您可能收到的错误代码为：

* 303:阻止的客户ID;
* 306:已阻止声明的设备ID;
* 307:阻止了ID的配置文件操作。

有关可能收到的错误代码的详细信息，请参阅[DCS错误代码、消息和示例](dcs-error-codes.md)。

## 从阻止列表中删除ID

已添加到阻止列表的ID不应在将来的任何请求中使用，因为它们会导致数据报告不正确。 [!DNL DCS]不支持从阻止列表中删除ID。

## 对ID同步的影响

[!DNL DCS] 调用可以包含一种或多种类型的ID。如果将包含单个ID的调用添加到阻止列表中，并且在这种情况下不会进行ID同步，则将完全忽略该ID的调用。

当多个ID调用还包列入阻止列表含一个已的ID时，[!DNL DCS]会不考虑已拒绝的ID，而只使用剩余的允许ID进行同步。

## ID的原因和修列入阻止列表复

将ID添加到阻止列表的最常见原因是客户基础架构与Audience Manager之间的集成不正确。 在识别已列入阻止列表的ID时，请确保彻底审查您的Audience Manager集成。 请参阅&#x200B;**实施和集成指南** ，以详细说明如何配置Audience Manager以与其他Experience Cloud解决方案或外部系统一起使用。

添加到阻止列表的ID的另一个常见原因是索引机器人（Web爬网程序），这通常会导致流量增加，从而导致将相同的ID多次发送到[!DNL DCS]。 如果您将索引机器人识别为将ID添加到阻止列表的原因，则应限制机器人对您网站的访问。

如果您很难确定集成问题，请立即联系客户支持。 在打开支持请求之前，请确保浏览器的`.har` `HTTP`存档已准备就绪。 此存档可帮助支持团队确定将ID添加到阻止列表的原因。
