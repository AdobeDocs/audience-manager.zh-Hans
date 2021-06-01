---
description: DCS API代码、方法和流程的概念信息、描述和定义。
seo-description: Adobe Audience Manager(AAM)中DCS API代码、方法和流程的概念信息、描述和定义。
seo-title: Adobe Audience Manager(AAM)中的DCS API参考概述
title: DCS API 参考概述
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 13%

---

# DCS API 参考概述

[!DNL DCS API]代码、方法和进程的概念信息、描述和定义。

* [DCS API 方法](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   使用GET或POST方法将数据发送到[!DNL DCS API]。

* [DCS 错误代码、消息和示例](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   数据收集服务器(DCS)生成的错误代码和消息按代码ID的数字顺序列出。

* [ID监控和列入阻止列表](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   DCS会监控收到的ID，并将那些在短时间内以异常高的速率发送的ID添加到阻止列表。

* [DCS 区域 ID、位置和主机名](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   对DCS进行调用时需要区域DCS服务器主机名。 这是因为DCS在地理上与站点访客较近的数据中心中存储信息。 如果将查询发送到错误的DCS，则查询将有效，但这些调用效率低下，可能会延迟响应。 要发出DCS请求，请将区域ID与其相应的区域主机名匹配，并使用正确的主机名构建查询。

* [格式化 DCS 调用中的键值对](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   进行调用时，DCS会接受标准或序列化格式的键值数据。 有关如何设置标准和序列化键值数据的格式的信息，请参阅此部分。

* [争用条件和错误处理](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   介绍如何防止争用情况和DCS错误处理。

* [DCS API 调用支持的属性](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   列出并描述可以传递到数据收集服务器(DCS)的语法和支持的属性（或键值对）。 此信息可帮助您设置DCS请求的格式并了解此系统返回的参数。
