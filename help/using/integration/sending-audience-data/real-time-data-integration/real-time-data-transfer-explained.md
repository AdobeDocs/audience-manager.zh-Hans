---
description: 概述Audience Manager如何与第三方内容提供商进行实时数据传输。
seo-description: 概述Audience Manager如何与第三方内容提供商进行实时数据传输。
seo-title: 介绍的实时数据传输流程
solution: Audience Manager
title: 介绍的实时数据传输流程
uuid: b68781b-3b7a-442d-8e34-2db2474849a4
translation-type: tm+mt
source-git-commit: ea95df8531c00c183f22b09a4a78fc6b35ee279d

---


# Real-Time Data Transfer Process Described{#real-time-data-transfer-process-described}

概述Audience Manager如何与第三方内容提供商进行实时数据传输。

<!-- real-time-data-transfer-explained.xml -->

## 实时数据传输

实时数据传输将细分ID作为用户访问或在您的网站上进行操作，以供用户访问或采取行动。通常，当用户在您的库存中导航时需要立即确定或对用户进行分组时，同步数据传输很有用。

## 数据集成步骤

实时数据集成流程如下所示：

1. 用户访问包含Audience Manager代码的客户站点。
1. Audience Manager loads an iframe and makes a call to our [!UICONTROL Data Collection Server] ( [!UICONTROL DCS]).
1. The [!UICONTROL DCS] calls the third-party server (in real time) to check if the vendor has any segment information about the user.
1. 内容提供商将有关该用户的区段信息返回Audience Manager。
1. Audience Manager收到此细分信息，使其可用于定位和构建新特征和区段。

![](assets/rt_reduce70.png)