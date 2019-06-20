---
description: Audience Manager如何与第三方供应商进行异步批量数据交换的一般概述。
seo-description: Audience Manager如何与第三方供应商进行异步批量数据交换的一般概述。
seo-title: 介绍的批量数据传输流程
solution: Audience Manager
title: 介绍的批量数据传输流程
uuid: a9eee940-151c-44f8-9fe9-4ab47d8fa45c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Batch Data Transfer Process Described {#batch-data-transfer-process-described}

Audience Manager如何与第三方供应商进行异步批量数据交换的一般概述。

## 批量数据集成

<!-- c_async.xml -->

批量数据集成过程可节省服务器上的访客信息，并将该材料与提供商定期发送的数据同步。异步数据传输过程在以下情况下很有用：

* 不需要进行即时数据传输。
* 收集数据以构建大量细分用户。
* You want to reduce data discrepancies and `HTTP` calls from the browser.

![](assets/s2s_70.png)

## 数据集成步骤

1. 用户访问客户站点。
1. Audience Manager和第三方数据提供商为访客分配唯一ID(通常使用cookie)。
1. Audience Manager调用第三方数据提供商以匹配访客ID。
1. 计划的请求通常在每天间隔内，在Audience Manager与您的第三方数据提供商之间交换访客区段数据。
1. Whenever an inbound [!UICONTROL Server-to-Server] file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner. For more information, see [Sample Message to Partners after Inbound Processing](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).