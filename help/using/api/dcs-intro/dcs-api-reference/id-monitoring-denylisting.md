---
description: DCS将监控其接收到的ID，并将那些在短时间内以异常高的速率发送的ID添加到阻止列表中。
keywords: id；监控；dcs
seo-description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
seo-title: ID Monitoring and Denylisting
solution: Audience Manager
title: ID监控和列入阻止列表
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# ID监控和列入阻止列表

[!DNL DCS]监视它接收到的ID，并将那些在短时间内以异常高的速率发送的ID添加到阻止列表中。

## 概述

为了保护Audience Manager基础架构免受恶意活动的侵扰，[!DNL DCS]使用高级算法来监视其接收的ID。 这些项可以是[!UICONTROL Data Provider Unique User ID] ([!UICONTROL CRM ID])、[!UICONTROL Audience Manager Unique User ID] ([!UICONTROL AAM UUID])或[!UICONTROL Experience Cloud ID] ([!UICONTROL ECID])。 有关Audience Manager支持的ID的详细解释，请参阅Audience Manager中的[ID索引](../../../reference/ids-in-aam.md)。

[!DNL DCS]监视其接收这些ID的频率，以检测潜在的恶意活动。 当[!DNL DCS]检测到短时间内对任何给定ID发出异常大量的[!DNL DCS]请求时，该ID将被添加到阻止列表中。

## 错误代码

您可以通过从[!DNL DCS]接收的错误代码来识别添加到阻止列表的ID。 您可能会收到的错误代码包括：

* 303：阻止的客户ID；
* 306：已阻止声明的设备ID；
* 307：已阻止ID的配置文件操作。

有关您可能会收到的错误码的详细信息，请参阅[DCS错误代码、消息和示例](dcs-error-codes.md)。

## 从阻止列表中删除ID

已添加到阻止列表的ID不应在任何将来的请求中使用，因为它们将导致不正确的数据报表。 [!DNL DCS]不支持从阻止列表中删除ID。

## 对ID同步的影响

[!DNL DCS]调用可以包含一种或多种ID类型。 如果将包含单个ID的调用添加到阻止列表中，则会完全忽略该ID，在这种情况下，不会发生ID同步。

列入阻止列表当多个ID调用还包含ID时，[!DNL DCS]将忽略被拒绝的ID，而只使用剩余的允许的ID进行同步。

## ID列入阻止列表的原因和修复

之所以要将ID添加到阻止列表，最常见的原因是客户基础架构与Audience Manager之间的集成不正确。 识别列入阻止列表ID时，请确保仔细检查您的Audience Manager集成。 有关如何配置Audience Manager以与其他Experience Cloud解决方案或外部系统结合使用的详细说明，请参阅&#x200B;**实施和集成指南**。

将ID添加到阻止列表的另一个常见原因是索引机器人（Web爬网程序），这通常会导致流量增加，从而导致将相同的ID多次发送到[!DNL DCS]。 如果您将索引机器人识别为将ID添加到阻止列表的原因，则应当限制机器人对您网站的访问。

如果您难以确定集成问题，请随时联系客户支持。 在打开支持请求之前，请确保使浏览器的`.har` `HTTP`存档准备就绪。 此存档可帮助支持团队确定将ID添加到阻止列表的原因。
