---
description: DCS API代码、方法和过程的概念信息、描述和定义。
seo-description: Conceptual information, descriptions, and definitions for DCS API code, methods, and processes in Adobe Audience Manager (AAM).
seo-title: DCS API Reference Overview in Adobe Audience Manager (AAM)
title: DCS API参考概述
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---

# DCS API参考概述

[!DNL DCS API]代码、方法和进程的概念信息、描述和定义。

* [DCS API方法](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

  使用GET或POST方法将数据发送到[!DNL DCS API]。

* [DCS错误代码、消息和示例](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

  数据收集服务器(DCS)生成的错误代码和消息，按代码ID以数字顺序列出。

* [ID监控和列入阻止列表](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

  DCS将监控其接收到的ID，并将那些在短时间内以异常高的速率发送的ID添加到阻止列表中。

* [DCS区域ID、位置和主机名](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

  调用DCS时需要区域DCS服务器主机名。 这是因为DCS在地理位置靠近站点访客的数据中心中存储信息。 如果您将查询发送到错误的DCS，则查询将起作用，但这些调用效率低下，并且可能会延迟响应。 要发出DCS请求，请将区域ID与其对应的区域主机名相匹配，然后使用正确的主机名形成查询。

* [格式化DCS调用中的键值对](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

  进行调用时，DCS接受标准格式或序列化格式的键值数据。 有关如何设置标准键值数据和序列化键值数据的格式的信息，请参阅此部分。

* [争用条件和错误处理](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

  介绍如何防止出现争用情况和DCS错误处理。

* [DCS API调用支持的属性](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

  列出并描述了可传递到数据收集服务器(DCS)的语法和支持的属性（或键值对）。 此信息可帮助您格式化DCS请求并了解此系统返回的参数。
