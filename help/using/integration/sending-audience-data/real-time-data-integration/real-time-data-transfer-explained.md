---
description: 概述Audience Manager如何与第三方内容提供商执行实时数据传输。
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: 实时数据传输流程说明
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: a03b8192-8410-479f-a326-4cddf10757f6
    internal-label: Inbound data transfers
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%
---

# 实时数据传输流程说明{#real-time-data-transfer-process-described}

概述Audience Manager如何与第三方内容提供商执行实时数据传输。

<!-- real-time-data-transfer-explained.xml -->

## 实时数据传输

实时数据传输会在用户访问您的网站或在您的网站上采取操作时发送和接收区段ID。 通常，当您需要在用户浏览您的库存时立即确定用户资格或划分用户时，同步数据传输非常有用。

## 数据集成步骤

实时数据集成流程的工作方式如下：

1. 用户访问包含Audience Manager代码的客户的网站。
1. Audience Manager加载iframe并对我们的[!UICONTROL Data Collection Server] ([!DNL DCS])进行调用。
1. [!DNL DCS]调用第三方服务器（实时）以检查供应商是否具有有关该用户的任何区段信息。
1. 内容提供程序将有关该用户的区段信息返回到Audience Manager。
1. Audience Manager会收到此区段信息，并可用于定位和构建新特征和区段。

![](assets/rt_reduce70.png)