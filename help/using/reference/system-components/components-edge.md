---
description: Audience manager使用分布式边缘计算拓扑来满足外部来源对我们系统的需求。
seo-description: Audience manager使用分布式边缘计算拓扑来满足外部来源对我们系统的需求。
seo-title: 了解边缘数据中心
solution: Audience Manager
title: 了解边缘数据中心
uuid: 4177e66-99f4-453d-94dd-058c6182c8d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 了解边缘数据中心{#understanding-the-edge-data-center}

Audience manager使用分布式边缘计算拓扑来满足外部来源对我们系统的需求。

## 边缘数据中心基础知识 {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

边缘计算可提供更好的性能，以响应扩散的、互联网范围内的需求，因为“边缘”本身是全局边界。 这意味着 [!DNL Audience Manager] 动态地将处理放在最接近需求来源的位置，并按尽可能最短的路径返回数据。 边缘计算有助于保持网站性能，进而保持网站的用户体验。 边缘数据中心是移入和移出数据的关键网关 [!DNL Audience Manager]。

边缘 [!DNL Audience Manager] 数据中心包括：

* **** 核心服务器：这些是主要的 [!DNL Audience Manager] 系统。 它们会更新数据并提供给边缘服务器。

* **** 边缘服务器：通常，这些是应用程序和／或Web服务器。 他们坐在与互联网 [!DNL Audience Manager] 的边界。 边缘服务器(如Akamai [!UICONTROL DCS] 系统)通常处理流入和流出的数据和请求 [!DNL Audience Manager]。

* **** 负载平衡器：管理Internet应用程序固有的不均衡的计算／处理需求。 这些平衡器可以防止服务器群集过载，而其他服务器群集仍然空闲。

下图说明了Audience Manager边缘数据中心环境。

![](assets/edge_data_center.png)

## 地理分布和负载平衡 {#geo-dist-balance}

请参阅数 [!UICONTROL DCS] 据收集 [组件中的部分](../../reference/system-components/components-data-collection.md)。
