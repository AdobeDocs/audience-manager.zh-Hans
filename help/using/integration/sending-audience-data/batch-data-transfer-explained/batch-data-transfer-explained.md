---
description: 概述Audience Manager如何与第三方供应商执行异步批处理数据交换。
seo-description: 概述Audience Manager如何与第三方供应商执行异步批处理数据交换。
seo-title: 批量数据传输流程说明
solution: Audience Manager
title: 批量数据传输流程说明
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 7%

---


# 批量数据传输流程说明 {#batch-data-transfer-process-described}

关于如何与第 [!DNL Audience Manager] 三方供应商执行异步批处理数据交换的一般概述。

## 批量数据集成

<!-- c_async.xml -->

批量访客集成过程将数据信息保存在我们的服务器上，并定期将该数据与提供商发送的数据同步。 在以下情况下，异步数据传输过程很有用：

* 无需立即进行数据传输。
* 收集数据以构建大量分段用户池。
* 您希望减少数据差异 `HTTP` 和来自浏览器的调用。

![](assets/s2s_70.png)

## 数据集成步骤

1. 用户访问客户站点。
1. [!DNL Audience Manager] 第三方数据提供者为访客分配唯一ID（通常使用cookie）。
1. [!DNL Audience Manager] 调用第三方数据提供程序以匹配访客ID。
1. 在与第三方数据提供商之间交换访客段数据的 [!DNL Audience Manager] 预定请求（通常在每日间隔内）。
1. 每当处理入站 [!UICONTROL Server-to-Server] 文件时，都会通过电子邮件将收据发送给合作伙伴解决方案，如果配置了，还会将收据发送给合作伙伴。 有关详细信息，请参 [阅入站处理后向合作伙伴发送的示例消息](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md)。
