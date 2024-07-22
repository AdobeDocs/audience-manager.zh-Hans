---
description: 概述Audience Manager如何与第三方供应商执行异步批量数据交换。
seo-description: A general overview of how Audience Manager performs an asynchronous batch data exchange with a third-party vendor.
seo-title: Batch Data Transfer Process Described
solution: Audience Manager
title: 批量数据传输流程说明
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# 批量数据传输流程说明 {#batch-data-transfer-process-described}

[!DNL Audience Manager]如何与第三方供应商执行异步批处理数据交换的概述。

## 批量数据集成

<!-- c_async.xml -->

批量数据集成过程将访客信息保存在我们的服务器上，并将该资料与提供商定期发送的数据同步。 异步数据传输流程在以下情况下很有用：

* 不需要立即传输数据。
* 正在收集数据以构建大型分段用户池。
* 您希望减少来自浏览器的数据差异和`HTTP`调用。

![](assets/s2s_70.png)

## 数据集成步骤

1. 用户访问客户站点。
1. [!DNL Audience Manager]和第三方数据提供商为访客分配一个唯一ID（通常使用Cookie）。
1. [!DNL Audience Manager]调用第三方数据提供程序以匹配访客ID。
1. 计划的请求（通常按每日间隔）会在[!DNL Audience Manager]和您的第三方数据提供商之间交换访客区段数据。
1. 每当处理入站[!UICONTROL Server-to-Server]文件时，都会通过电子邮件将接收信息发送给合作伙伴解决方案，如果已配置，还会发送给合作伙伴。 有关详细信息，请参阅[入站处理后发送给合作伙伴的示例消息](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md)。
