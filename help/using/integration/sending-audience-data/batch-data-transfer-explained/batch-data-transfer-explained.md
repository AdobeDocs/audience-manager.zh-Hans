---
description: Audience Manager如何与第三方供应商执行异步批量数据交换的一般概述。
seo-description: Audience Manager如何与第三方供应商执行异步批量数据交换的一般概述。
seo-title: 描述的批数据传输流程
solution: Audience Manager
title: 描述的批数据传输流程
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 描述的批数据传输流程 {#batch-data-transfer-process-described}

Audience Manager如何与第三方供应商执行异步批量数据交换的一般概述。

## 批量数据集成

<!-- c_async.xml -->

批量数据集成过程将访客信息保存在我们的服务器上，并定期将该材料与提供商发送的数据同步。 在以下情况下，异步数据传输过程很有用：

* 不需要立即传输数据。
* 收集数据以构建大量细分用户池。
* 您希望减少数据差异和来 `HTTP` 自浏览器的调用。

![](assets/s2s_70.png)

## 数据集成步骤

1. 用户访问客户站点。
1. Audience manager和第三方数据提供者为访客分配一个唯一ID（通常使用cookie）。
1. Audience manager调用第三方数据提供者以匹配访客ID。
1. 在Audience manager和您的第三方数据提供商之间交换访客区段数据的预定请求（通常在每日间隔内）。
1. 每当处理入站文 [!UICONTROL Server-to-Server] 件时，都会通过电子邮件向合作伙伴解决方案发送收据，如果配置了该收据，则会向合作伙伴发送收据。 有关详细信息，请参 [阅入站处理后发送给合作伙伴的示例消息](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md)。