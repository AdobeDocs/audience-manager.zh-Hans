---
description: Audience manager如何与第三方内容提供商进行实时数据传输的一般概述。
seo-description: Audience manager如何与第三方内容提供商进行实时数据传输的一般概述。
seo-title: 描述的实时数据传输过程
solution: Audience Manager
title: 描述的实时数据传输过程
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
translation-type: tm+mt
source-git-commit: ea95df8531c00c183f22b09a4a78fc6b35ee279d

---


# 描述的实时数据传输过程{#real-time-data-transfer-process-described}

Audience manager如何与第三方内容提供商进行实时数据传输的一般概述。

<!-- real-time-data-transfer-explained.xml -->

## 实时数据传输

实时数据传输以用户访问或在您的网站上执行操作的方式发送和接收区段ID。 通常，当用户在库存中导航时，需要立即确定用户资格或对用户进行细分时，同步数据传输会很有用。

## 数据集成步骤

实时数据集成过程的工作方式如下：

1. 用户访问包含Audience manager代码的客户站点。
1. Audience manager加载iframe并调用我们的( [!UICONTROL Data Collection Server][!UICONTROL DCS])。
1. 该服 [!UICONTROL DCS] 务器（实时）调用第三方服务器以检查供应商是否具有有关该用户的任何区段信息。
1. 内容提供商会将有关该用户的细分信息返回给Audience Manager。
1. Audience manager接收此区段信息，并使其可用于定位和构建新特征和区段。

![](assets/rt_reduce70.png)