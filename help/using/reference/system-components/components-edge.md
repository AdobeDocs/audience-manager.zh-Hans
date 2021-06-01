---
description: Audience Manager使用分布式边缘计算拓扑来满足外部源对我们系统的需求。
seo-description: Audience Manager使用分布式边缘计算拓扑来满足外部源对我们系统的需求。
seo-title: 了解边缘数据中心
solution: Audience Manager
title: 了解边缘数据中心
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: 系统组件
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# 了解边缘数据中心{#understanding-the-edge-data-center}

Audience Manager使用分布式边缘计算拓扑来满足外部源对我们系统的需求。

## 边缘数据中心基础知识{#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

边缘计算可提供更高的性能，以响应分散的、在Internet范围内的需求，因为“边缘”本身是全局边界。 这意味着[!DNL Audience Manager]会动态地将处理放在最接近需求源的位置，并按尽可能最短的路径返回数据。 边缘计算有助于保持网站性能，进而保留您网站上的用户体验。 边缘数据中心是用于将数据移入和移出[!DNL Audience Manager]的关键网关。

[!DNL Audience Manager]边缘数据中心包括：

* **核心服务器：** 这些是主要的 [!DNL Audience Manager] 系统。它们会更新并向边缘服务器提供数据。

* **边缘服务器：** 通常指应用程序和/或Web服务器。它们位于[!DNL Audience Manager]和Internet之间的边界。 边缘服务器（如[!DNL DCS]或Akamai系统）通常处理流入和流出[!DNL Audience Manager]的数据和请求。

* **负载平衡器：** 管理Internet应用程序中固有的不均衡的计算/处理需求。这些平衡器可防止服务器群集过载，而其他服务器群集则保持闲置状态。

下图说明了Audience Manager边缘数据中心环境。

![](assets/edge_data_center.png)

## 地理分布和负载平衡{#geo-dist-balance}

请参阅[数据收集组件](../../reference/system-components/components-data-collection.md)中的[!DNL DCS]部分。
