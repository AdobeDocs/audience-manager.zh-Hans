---
description: 概述Audience Manager如何与第三方供应商执行异步批处理数据交换。
seo-description: 概述Audience Manager如何与第三方供应商执行异步批处理数据交换。
seo-title: 批量数据传输流程说明
solution: Audience Manager
title: 批量数据传输流程说明
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 8%

---

# 批量数据传输流程说明 {#batch-data-transfer-process-described}

[!DNL Audience Manager]如何与第三方供应商执行异步批处理数据交换的一般概述。

## 批量数据集成

<!-- c_async.xml -->

批量访客集成过程将数据信息保存在我们的服务器上，并定期将该材料与提供商发送的数据同步。 在以下情况下，异步数据传输过程很有用：

* 不需要立即传输数据。
* 收集数据以构建大量细分用户池。
* 您希望减少数据差异和来自浏览器的`HTTP`调用。

![](assets/s2s_70.png)

## 数据集成步骤

1. 用户访问客户站点。
1. [!DNL Audience Manager] 而第三方数据提供者则为访客分配唯一ID（通常使用cookie）。
1. [!DNL Audience Manager] 调用第三方数据提供程序以匹配访客ID。
1. 在[!DNL Audience Manager]和第三方访客提供程序之间交换数据段数据的计划请求（通常在每日间隔内）。
1. 每当处理入站[!UICONTROL Server-to-Server]文件时，都会通过电子邮件将收据发送给合作伙伴解决方案，如果配置了，还会发送给合作伙伴。 有关详细信息，请参阅[入站处理后向合作伙伴发送的示例消息](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md)。
