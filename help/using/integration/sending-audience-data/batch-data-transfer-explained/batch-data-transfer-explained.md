---
description: 有关Audience Manager如何与第三方供应商执行异步批量数据交换的一般概述。
seo-description: 有关Audience Manager如何与第三方供应商执行异步批量数据交换的一般概述。
seo-title: 批量数据传输流程说明
solution: Audience Manager
title: 批量数据传输流程说明
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: 入站数据传输
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 8%

---

# 批量数据传输流程说明 {#batch-data-transfer-process-described}

[!DNL Audience Manager]如何与第三方供应商执行异步批量数据交换的一般概述。

## 批量数据集成

<!-- c_async.xml -->

批量数据集成过程会在我们的服务器上保存访客信息，并定期将该材料与提供商发送的数据同步。 在以下情况下，异步数据传输过程非常有用：

* 无需立即进行数据传输。
* 收集数据以构建大量分段用户池。
* 您希望减少来自浏览器的数据差异和`HTTP`调用。

![](assets/s2s_70.png)

## 数据集成步骤

1. 用户访问客户网站。
1. [!DNL Audience Manager] 和第三方数据提供商会为访客分配一个唯一ID（通常使用cookie）。
1. [!DNL Audience Manager] 调用第三方数据提供程序以匹配访客ID。
1. 在[!DNL Audience Manager]与第三方数据提供商之间交换访客区段数据的计划请求（通常为每日间隔）。
1. 每当处理入站[!UICONTROL Server-to-Server]文件时，都会通过电子邮件向合作伙伴解决方案发送回执，如果已配置，则会向合作伙伴发送回执。 有关更多信息，请参阅[入站处理后发送给合作伙伴的示例消息](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md)。
