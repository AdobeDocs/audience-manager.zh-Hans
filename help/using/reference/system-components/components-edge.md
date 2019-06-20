---
description: Audience Manager使用分布式边缘计算拓扑来满足外部源在我们的系统中的需求。
seo-description: Audience Manager使用分布式边缘计算拓扑来满足外部源在我们的系统中的需求。
seo-title: 了解Edge数据中心
solution: Audience Manager
title: 了解Edge数据中心
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Understanding the Edge Data Center{#understanding-the-edge-data-center}

Audience Manager使用分布式边缘计算拓扑来满足外部源在我们的系统中的需求。

## Edge Data Center Basics {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

边缘计算为响应扩散、Internet范围需求提供了改进的性能，因为“边缘”本身是全局边界。This means [!DNL Audience Manager] dynamically places processing closest to the sources of demand and returns data by the shortest possible path. Edge计算有助于维护站点性能，这反过来又保留了网站上的用户体验。The edge data center is a key gateway for moving data in and out of [!DNL Audience Manager].

[!DNL Audience Manager] 边缘数据中心包括：

* **核心服务器：** 这些是主要 [!DNL Audience Manager] 系统。他们更新并向边缘服务器提供数据。

* **边缘服务器：** 通常，这些是应用程序和/或Web服务器。They sit at the boundary between [!DNL Audience Manager] and the Internet. Edge servers, such as the [!UICONTROL DCS] or Akamai systems, typically handle data and requests flowing into and out of [!DNL Audience Manager].

* **负载平衡器：** 管理Internet应用程序固有的计算/处理需求。这些平衡程序防止服务器群集过载，而其他服务器仍空闲。

下图说明了Audience Manager边缘数据中心环境。

![](assets/edge_data_center.png)

## Geographic Distribution and Load Balancing {#geo-dist-balance}

See the [!UICONTROL DCS] section in [Data Collection Components](../../reference/system-components/components-data-collection.md).
