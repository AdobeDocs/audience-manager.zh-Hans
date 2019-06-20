---
description: DCS API代码、方法和进程的概念信息、描述和定义。
seo-description: Adobe Audience Manager(AAM)中DCS API代码、方法和流程的概念信息、描述和定义。
seo-title: Adobe Audience Manager(AAM)中的DCS API参考概述
title: DCS API参考概述
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# DCS API参考概述

DCS API代码、方法和进程的概念信息、描述和定义。

* [DCS API方法](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   使用GET或POST方法将数据发送到DCS API。

* [DCS 错误代码、消息和示例](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   由数据收集服务器(DCS)生成的错误代码和消息，按代码ID列出。

* [ID监控和黑名单](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-blacklisting.md)

   DCS会监视接收到的ID并列入黑名单，这些ID在短时间内以异常高的速率发送。

* [DCS区域ID、位置和主机名](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   需要使用区域DCS服务器主机名才能调用DCS。这是因为DCS存储在地理位置接近站点访客的数据中心中的信息。如果您将其发送到错误的DCS，则您的查询将工作，但这些调用效率低下，并且可能会延迟响应。要发出DCS请求，请将区域ID与相应的区域主机名匹配，并使用适当的主机名构成查询。

* [在DCS调用中格式化键值对](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   进行呼叫时，DCS以标准或序列化格式接受键值数据。查看本节以了解有关如何格式化标准和序列化密钥值数据的信息。

* [竞争条件和错误处理](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   介绍如何防止竞争条件和DCS错误处理。

* [DCS API调用的支持属性](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   列出并描述可传入数据收集服务器(DCS)的语法和支持的属性(或密钥值对)。此信息可帮助您格式化DCS请求并了解此系统返回的参数。
