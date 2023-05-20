---
description: Audience Manager使用分散式邊緣運算拓撲，滿足外部來源對我們的系統的需求。
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
ht-degree: 4%

---

# 了解边缘数据中心{#understanding-the-edge-data-center}

Audience Manager使用分散式邊緣運算拓撲，滿足外部來源對我們的系統的需求。

## Edge Datacenter基本需知 {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge運算提供更優異的效能，因應Internet廣泛需求，因為「邊緣」本身就是全球邊界。 這表示 [!DNL Audience Manager] 以動態方式將處理放在最接近需求來源的位置，並依照最短的可能路徑傳回資料。 Edge Computing有助於維持網站效能，進而保留網站的使用者體驗。 邊緣資料中心是進出資料的重要閘道 [!DNL Audience Manager].

此 [!DNL Audience Manager] 邊緣資料中心包含：

* **核心伺服器：** 這些是主要 [!DNL Audience Manager] 系統。 它們會更新資料並提供給Edge伺服器。

* **邊緣伺服器：** 這些通常是應用程式和/或Web伺服器。 它們位於兩者之間的邊界 [!DNL Audience Manager] 以及網際網路。 邊緣伺服器，例如 [!DNL DCS] 或Akamai系統，通常會處理流入和流出的資料和請求 [!DNL Audience Manager].

* **負載平衡器：** 管理網際網路應用程式固有的不均衡運算/處理需求。 這些平衡器可防止伺服器叢集超載，而其他叢集則維持閒置狀態。

下圖說明Audience Manager邊緣資料中心環境。

![](assets/edge_data_center.png)

## 地理分配和負載平衡 {#geo-dist-balance}

請參閱 [!DNL DCS] 中的區段 [資料收集元件](../../reference/system-components/components-data-collection.md).
