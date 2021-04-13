---
description: 此地图包含主要Audience Manager系统。 它直观地表示数据如何流入、流出和流入Audience Manager组件。
seo-description: 此地图包含主要Audience Manager系统。 它直观地表示数据如何流入、流出和流入Audience Manager组件。
seo-title: 平台架构数据流图
solution: Audience Manager
title: 平台架构数据流图
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: 系统组件
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---

# 平台架构：数据流程图{#platform-architecture-data-flow-map}

此地图包含主要Audience Manager系统。 它直观地表示数据如何流入、流出和流入Audience Manager组件。

## 如何读取此映射{#compmap}

<!-- 

c_compmap.xml

 -->

在图中，灰色框包含[!DNL Audience Manager]系统。 某些组件完全是内部组件，而其他组件则位于[!DNL Audience Manager]与外部世界之间的边界。 作为[!DNL Audience Manager]客户，内部组件通常是透明的或不可访问的。 但是，有时您可能通过用户界面或数据集成与这些系统互动。 位于包装盒边缘的系统在[!DNL Audience Manager]和外部世界之间收集和发送数据。

颜色定义流入和流出[!DNL Audience Manager]的数据类型。 绿色是客户数据，蓝色是客户数据（访问您网站的人员），橙色是报告数据。

有关系统说明和摘要，请参见数据[操作](../../reference/system-components/components-data-action.md)、[集合](../../reference/system-components/components-data-collection.md)、[处理](../../reference/system-components/components-data-processing.md)和[标签管理](../../reference/system-components/components-tag-management.md)部分。

![](assets/flowmap.png)
