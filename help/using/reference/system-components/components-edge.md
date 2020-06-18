---
description: Audience Manager使用分布式边缘计算拓扑来满足外部源对我们系统的需求。
seo-description: Audience Manager使用分布式边缘计算拓扑来满足外部源对我们系统的需求。
seo-title: 了解边缘数据中心
solution: Audience Manager
title: 了解边缘数据中心
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---


# 了解边缘数据中心{#understanding-the-edge-data-center}

Audience Manager使用分布式边缘计算拓扑来满足外部源对我们系统的需求。

## Edge Data Center基础知识 {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

边缘计算可提供更好的性能，以响应分散的、在Internet范围内的需求，因为“边缘”本身是一个全球边界。 这意味着 [!DNL Audience Manager] 动态地将处理放在最接近需求来源的位置，并按尽可能最短的路径返回数据。 边缘计算有助于保持网站性能，进而保留网站的用户体验。 边缘数据中心是移入和移出数据的关键网关 [!DNL Audience Manager]。

边缘 [!DNL Audience Manager] 数据中心包括：

* **核心服务器：** 这些是主要的 [!DNL Audience Manager] 系统。 他们更新数据并向边缘服务器提供数据。

* **边缘服务器：** 通常，这些是应用程序和／或Web服务器。 他们坐在与互联网 [!DNL Audience Manager] 之间的边界。 边缘服务器(如 [!DNL DCS] 或Akamai系统)通常处理进出的数据和请求 [!DNL Audience Manager]。

* **负载平衡：** 管理因特网应用程序固有的不均衡计算／处理需求。 这些平衡器可防止服务器群集过载，而其他服务器群集仍处于空闲状态。

下图说明了Audience Manager边缘数据中心环境。

![](assets/edge_data_center.png)

## 地理分布和负载平衡 {#geo-dist-balance}

请参阅 [!DNL DCS] 数据收集 [组件中的部分](../../reference/system-components/components-data-collection.md)。
