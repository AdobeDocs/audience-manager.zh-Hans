---
description: 此地图包含主要Audience Manager系统。 它直观地表示数据如何流入、流出和在Audience Manager组件之间流动。
seo-description: 此地图包含主要Audience Manager系统。 它直观地表示数据如何流入、流出和在Audience Manager组件之间流动。
seo-title: 平台架构数据流图
solution: Audience Manager
title: 平台架构数据流图
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: 系统组件
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---

# 平台架构：数据流程图{#platform-architecture-data-flow-map}

此地图包含主要Audience Manager系统。 它直观地表示数据如何流入、流出和在Audience Manager组件之间流动。

## 如何阅读此地图 {#compmap}

<!-- 

c_compmap.xml

 -->

在图中，灰色框包含[!DNL Audience Manager]系统。 某些组件完全是内部组件，而其他组件则位于[!DNL Audience Manager]与外部世界之间的边界。 作为[!DNL Audience Manager]客户，内部组件通常是透明的或不可访问的。 但是，有时您可能会通过用户界面或数据集成与这些系统进行交互。 盒边缘的系统收集并发送[!DNL Audience Manager]和外部世界之间的数据。

颜色定义流入和流出[!DNL Audience Manager]的数据类型。 绿色表示客户数据，蓝色表示客户数据（访问您网站的人员），橙色表示用于报告的数据。

有关系统描述和摘要，请参见数据[action](../../reference/system-components/components-data-action.md)、[collection](../../reference/system-components/components-data-collection.md)、[processing](../../reference/system-components/components-data-processing.md)和[tag management](../../reference/system-components/components-tag-management.md)部分。

![](assets/flowmap.png)
