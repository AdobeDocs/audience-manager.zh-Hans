---
description: DCS API代码、方法和进程的概念信息、说明和定义。
seo-description: Adobe Audience Manager(AAM)中DCS API代码、方法和进程的概念信息、描述和定义。
seo-title: Adobe Audience Manager(AAM)中的DCS API参考概述
title: DCS API参考概述
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# DCS API参考概述

DCS API代码、方法和进程的概念信息、说明和定义。

* [DCS API方法](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   使用GET或POST方法将数据发送到DCS API。

* [DCS 错误代码、消息和示例](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   由按代码ID以数字顺序列出的数据收集服务器(DCS)生成的错误代码和消息。

* [ID监控和黑名单](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-blacklisting.md)

   DCS监视其接收的ID，并列出在短时间内以异常高的速率发送的ID。

* [DCS区域ID、位置和主机名](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   对DCS进行调用时需要区域DCS服务器主机名。 这是因为DCS将信息存储在地理位置接近站点访问者的数据中心中。 如果将查询发送到错误的DCS，则这些查询会正常工作，但这些调用效率低下，并且可能会延迟响应。 要发出DCS请求，请将区域ID与其相应的区域主机名匹配，并使用正确的主机名组成查询。

* [格式化DCS调用中的键值对](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   在发出呼叫时，DCS以标准或序列化格式接受键值数据。 有关如何设置标准和序列化键值数据的格式的信息，请查阅本节。

* [竞争条件和错误处理](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   介绍如何防止竞争情况和DCS错误处理。

* [DCS API调用支持的属性](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   列出并描述可传递到数据收集服务器(DCS)的语法和支持的属性（或键值对）。 这些信息可以帮助您格式化DCS请求并了解此系统返回的参数。
