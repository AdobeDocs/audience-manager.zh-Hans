---
description: 概述Audience Manager如何与第三方内容提供商进行实时数据传输。
seo-description: 概述Audience Manager如何与第三方内容提供商进行实时数据传输。
seo-title: 描述的实时数据传输过程
solution: Audience Manager
title: 描述的实时数据传输过程
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# 描述的实时数据传输过程{#real-time-data-transfer-process-described}

概述Audience Manager如何与第三方内容提供商进行实时数据传输。

<!-- real-time-data-transfer-explained.xml -->

## 实时数据传输

实时数据传输以用户访问或在您的网站上采取操作的方式发送和接收区段ID。 通常，当您需要在用户浏览库存时立即确定用户资格或对用户进行细分时，同步数据传输会很有用。

## 数据集成步骤

实时数据集成过程的工作方式如下：

1. 用户访问包含Audience Manager代码的客户站点。
1. Audience Manager加载iframe并调用我们的[!UICONTROL Data Collection Server]([!DNL DCS])。
1. [!DNL DCS]将实时调用第三方服务器，以检查供应商是否具有有关该用户的任何细分信息。
1. 内容提供者会将有关该用户的区段信息返回给Audience Manager。
1. Audience Manager接收此细分信息，并使其可用于定位和构建新特征和细分。

![](assets/rt_reduce70.png)