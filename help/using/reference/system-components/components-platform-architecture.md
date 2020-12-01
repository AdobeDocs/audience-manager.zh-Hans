---
description: 此地图包含主要Audience Manager系统。 它以可视方式表示数据如何流入、流出和在Audience Manager组件之间流动。
seo-description: 此地图包含主要Audience Manager系统。 它以可视方式表示数据如何流入、流出和在Audience Manager组件之间流动。
seo-title: 平台架构数据流图
solution: Audience Manager
title: 平台架构数据流图
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 2%

---


# 平台架构：数据流程图{#platform-architecture-data-flow-map}

此地图包含主要Audience Manager系统。 它以可视方式表示数据如何流入、流出和在Audience Manager组件之间流动。

## 如何读取此映射{#compmap}

<!-- 

c_compmap.xml

 -->

在图中，灰色框包含[!DNL Audience Manager]系统。 某些组件完全是内部组件，而其他组件则位于[!DNL Audience Manager]与外部世界之间的边界。 作为[!DNL Audience Manager]客户，内部组件通常是透明的或不可访问的。 但是，有时您可能通过用户界面或数据集成与这些系统交互。 包装盒边缘的系统会收集数据并在[!DNL Audience Manager]和外部世界之间发送。

颜色定义流入和流出[!DNL Audience Manager]的数据类型。 绿色是客户数据，蓝色是客户数据（访问您网站的人员），橙色是报告数据。

有关系统说明和摘要，请参见数据[操作](../../reference/system-components/components-data-action.md)、[集合](../../reference/system-components/components-data-collection.md)、[处理](../../reference/system-components/components-data-processing.md)和[标签管理](../../reference/system-components/components-tag-management.md)部分。

![](assets/flowmap.png)

