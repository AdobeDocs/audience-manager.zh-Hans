---
description: 此地图包含主要Audience Manager系统。它以可视方式呈现数据流入、退出和在Audience Manager组件中的流向。
seo-description: 此地图包含主要Audience Manager系统。它以可视方式呈现数据流入、退出和在Audience Manager组件中的流向。
seo-title: 平台体系架构数据流地图
solution: Audience Manager
title: 平台体系架构数据流地图
uuid: d845af1d-f448-4f4 c-948e-b2 c89 f125086
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Platform Architecture: Data Flow Map{#platform-architecture-data-flow-map}

此地图包含主要Audience Manager系统。它以可视方式呈现数据流入、退出和在Audience Manager组件中的流向。

## How to read this map {#compmap}

<!-- 

c_compmap.xml

 -->

In the map, the gray box contains [!DNL Audience Manager] systems. Some components are completely internal and others sit on the boundary between [!DNL Audience Manager] and the outside world. As an [!DNL Audience Manager] customer, internal components are often transparent or inaccessible. 但是，有时您可能会通过用户界面或数据集成与这些系统互动。Systems on the edge of the box collect and send data between [!DNL Audience Manager] and the outside world.

Colors define the type of data that flows in and out of [!DNL Audience Manager]. 绿色是客户数据，蓝色是客户数据(访问您的站点的人)，橙色是用于报告的数据。

For system descriptions and summaries see the data [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [processing](../../reference/system-components/components-data-processing.md), and [tag management](../../reference/system-components/components-tag-management.md) sections.

![](assets/flowmap.png)

