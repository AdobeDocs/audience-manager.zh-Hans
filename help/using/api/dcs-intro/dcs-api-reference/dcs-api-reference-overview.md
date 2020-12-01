---
description: DCS API代码、方法和流程的概念信息、描述和定义。
seo-description: Adobe Audience Manager(AAM)的DCS API代码、方法和流程的概念信息、描述和定义。
seo-title: Adobe Audience Manager(AAM)的DCS API参考概述
title: DCS API 参考概述
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 13%

---


# DCS API 参考概述

[!DNL DCS API]代码、方法和进程的概念信息、说明和定义。

* [DCS API 方法](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   使用GET或POST方法将数据发送到[!DNL DCS API]。

* [DCS 错误代码、消息和示例](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   由按代码ID以数字顺序列出的数据收集服务器(DCS)生成的错误代码和消息。

* [ID监控和列入阻止列表](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   DCS监视它接收的ID，并将短时间内以异常高速率发送的ID添加到阻止列表。

* [DCS 区域 ID、位置和主机名](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   对DCS进行调用时，需要使用区域DCS服务器主机名。 这是因为DCS将信息存储在地理位置接近站点访客的数据中心中。 如果将查询发送到错误的DCS，则这些调用将正常工作，但这些调用效率低下，可能会延迟响应。 要发出DCS请求，请将区域ID与其相应的区域主机名匹配，并使用正确的主机名组成查询。

* [格式化 DCS 调用中的键值对](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   发出呼叫时，DCS以标准或序列化格式接受密钥值数据。 有关如何格式化标准和序列化键值数据的信息，请查阅本节。

* [争用条件和错误处理](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   介绍如何防止竞态情况和DCS错误处理。

* [DCS API 调用支持的属性](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   列表并描述可传递到数据收集服务器(DCS)的语法和支持的属性（或键值对）。 此信息有助于您格式化DCS请求并了解此系统返回的参数。
