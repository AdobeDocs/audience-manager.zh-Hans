---
description: 有关Audience Manager如何与第三方内容提供商执行实时数据传输的一般概述。
seo-description: 有关Audience Manager如何与第三方内容提供商执行实时数据传输的一般概述。
seo-title: 描述的实时数据传输过程
solution: Audience Manager
title: 描述的实时数据传输过程
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: 入站数据传输
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 1%

---


# 描述的实时数据传输过程{#real-time-data-transfer-process-described}

有关Audience Manager如何与第三方内容提供商执行实时数据传输的一般概述。

<!-- real-time-data-transfer-explained.xml -->

## 实时数据传输

当用户访问您的网站或对您的网站采取操作时，实时数据传输会发送和接收区段ID。 通常，当您需要在库存中导航或立即划分用户区段时，同步数据传输非常有用。

## 数据集成步骤

实时数据集成过程的工作方式如下：

1. 用户访问包含Audience Manager代码的客户网站。
1. Audience Manager加载iframe并调用我们的[!UICONTROL Data Collection Server]([!DNL DCS])。
1. [!DNL DCS]会（实时）调用第三方服务器以检查供应商是否具有有关用户的任何区段信息。
1. 内容提供者返回有关要Audience Manager的用户的区段信息。
1. Audience Manager接收此区段信息，并将其用于定位和构建新特征和区段。

![](assets/rt_reduce70.png)