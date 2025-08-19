---
description: Audience Manager使用分布式边缘计算拓扑来满足外部来源对系统提出的需求。
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: 了解边缘数据中心
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# 了解边缘数据中心{#understanding-the-edge-data-center}

Audience Manager使用分布式边缘计算拓扑来满足外部来源对系统提出的需求。

## 边缘数据中心基础知识 {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

由于“边缘”本身就是全局边界，因此边缘计算提供了改进的性能，以响应分布的、整个互联网的需求。 这意味着[!DNL Audience Manager]动态地将处理放在距离需求源最近的位置，并以尽可能短的路径返回数据。 边缘计算可帮助保持站点性能，进而保护您网站上的用户体验。 边缘数据中心是将数据移入和移出[!DNL Audience Manager]的关键网关。

[!DNL Audience Manager]边缘数据中心包括：

* **核心服务器：**&#x200B;这些是主要的[!DNL Audience Manager]系统。 它们更新并向边缘服务器提供数据。

* **边缘服务器：**&#x200B;通常这些是应用程序和/或Web服务器。 它们位于[!DNL Audience Manager]和Internet之间的边界。 边缘服务器（如[!DNL DCS]或Akamai系统）通常处理流入和流出[!DNL Audience Manager]的数据和请求。

* **负载平衡器：**&#x200B;管理Internet应用程序中固有的不均匀计算/处理需求。 这些平衡器可防止服务器群集在其他人处于空闲状态时过载。

下图说明了Audience Manager边缘数据中心环境。

![](assets/edge_data_center.png)

## 地理分配和负载平衡 {#geo-dist-balance}

请参阅[!DNL DCS]数据收集组件[中的](../../reference/system-components/components-data-collection.md)部分。
