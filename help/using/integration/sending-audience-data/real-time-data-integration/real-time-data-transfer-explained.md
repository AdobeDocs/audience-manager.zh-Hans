---
description: 有关Audience Manager如何与第三方内容提供商执行实时数据传输的概述。
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: 实时数据传输流程说明
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---


# 实时数据传输流程说明{#real-time-data-transfer-process-described}

有关Audience Manager如何与第三方内容提供商执行实时数据传输的概述。

<!-- real-time-data-transfer-explained.xml -->

## 实时数据传输

实时数据传输会在用户访问您的网站或在您的网站上采取操作时发送和接收区段ID。 通常，当您需要在用户浏览您的库存时立即确定用户资格或划分用户时，同步数据传输非常有用。

## 数据集成步骤

实时数据集成流程的工作方式如下：

1. 用户访问包含Audience Manager代码的客户的网站。
1. Audience Manager加载iframe并对我们的[!UICONTROL Data Collection Server] ([!DNL DCS])进行调用。
1. [!DNL DCS]调用第三方服务器（实时）以检查供应商是否具有有关该用户的任何区段信息。
1. 内容提供程序将返回有关该用户的区段信息以进行Audience Manager。
1. Audience Manager会收到此区段信息，并可用于定位和构建新特征和区段。

![](assets/rt_reduce70.png)