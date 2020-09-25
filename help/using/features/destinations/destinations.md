---
description: 在Audience Manager中，目标是任何第三方系统(广告服务器、DSP、广告网络等) 任何其他系统（广告服务器、DSP、广告网络等）。使用目标生成器工具创建和管理cookie、URL或服务器到服务器目标。
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: 在Audience Manager中，目标是任何第三方系统(广告服务器、DSP、广告网络等) 任何其他系统（广告服务器、DSP、广告网络等）。目标生成器是用于创建和管理cookie、URL或服务器到服务器目标的工具。
seo-title: 目标
solution: Audience Manager
title: 目标
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 8027f278aa2b879b6cb277f44caf4b62dc75e2c3
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 6%

---


# [!UICONTROL Destinations] 概述 {#destinations}

在Audience Manager中， [!UICONTROL destination] 是任何第三方系统(广告服 [!DNL DSP]务器、广告网络等) 任何其他系统（广告服务器、DSP、广告网络等）。[!UICONTROL Destination Builder] 是用于创建和管理、 [!UICONTROL cookie]或 [!DNL URL]的工 [!UICONTROL server-to-server destinations]具

## 用途和优势 {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 并可 [!UICONTROL Destination Builder] 以创建细 [!UICONTROL destinations] 分用户的相关信息并将其发送给数据合作伙伴。 这有助于您：

* **Protect数据价值：** 您只能共享有关合格用户的 [!UICONTROL destination]特 [!UICONTROL Destination Builder] 定信息，而不是将所有用户数据发送到。
* **对数据采取措施：** 向合作伙伴发送数 [!UICONTROL destination] 据可帮助他们快速开发和目标符合条件的受众细分。
* **减少技术开销：** 商业用户可以在界 [!UICONTROL destinations] 面中安全地 [!UICONTROL Destination Builder] 设置。 这有助于缩短部署前测试所需的时间。 您可 [!UICONTROL Destination Builder]以根据业务需求变化创 [!UICONTROL destinations] 建、管理和删除，无需经历漫长的开发周期。

## 技术考虑事项 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

数据投放取决于您的数据合作伙伴希望或能够如何接收 [!UICONTROL destination] 信息。 技术或工程限制可能会阻 [!UICONTROL destination] 止通过、或 [!DNL URL]过程 [!UICONTROL cookie]接收 [!UICONTROL server-to-server] 数据。 与您的第三方合作伙伴合作，确定他们可以使用的方法。

## 业务考虑事项 {#business-considerations}

选择一种投放方法而非另一种方法的业务决策取决于您的合作 [!UICONTROL destination] 伙伴的技术能力，以及您希望如何处理合格的用户信息。 例如，如果某个用户无法通过特定投放方法接 [!UICONTROL destination] 收数据，技术约束可以限制您的选项。 但是，如果没有技术问题，您可以根据要如何对该数据执行操作来发送信息。 例如：

* [!DNL URL]和几 [!UICONTROL cookie-based destinations] 乎与页面上的用户操作同步工作。
* [!UICONTROL Server-to-server] 方法有利于长期构建深层受众段。

## [!UICONTROL Destination] 类型和典型使用 {#destination-types}

下表中的示例可以帮助您了解何时使用特定类型以及 [!UICONTROL destination] 每种类型之间的差异。

| [!UICONTROL Destination] 键入 | 通常在 | 示例 | 注意事项 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 您需要将数据发送到Adobe Experience Cloud的其他解决方案。 | 向Adobe Analytics发送数据。 |  |
| **[!UICONTROL People-Based Destinations]** | 您需要将受众细分发送给基于人的环境，如Facebook。 | 根据现有客户的购买历史向其提供个性化优惠 | 受众定位是通过散列标识符完成的。 请参 [阅基于人的目标](people-based-destinations-overview.md)。 |
| **[!UICONTROL Device-Based Destinations]** (**服务器到服务器**) | <ul><li>无需立即进行数据传输。</li><li>收集受众以构建一个大型合格用户池。</li></ul> | 收集一段时间（小时或天）的活动，以在设置为稍后运行的数据中使用它。 | <ul><li>传输有关新站点和以前站点访客的数据。 </li><li>访客无需再被看到即可获得其他细分。</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** 或 **Cookie**) | 您需要立即传输数据，以便目标可以立即对合格用户执行操作。 | 从票证购买站点发送数据。 使用或 [!UICONTROL URL] 确 [!UICONTROL cookie destination] 定用户资格并立即重新目标。 | <ul><li>仅传输有关新访客的数据。 </li><li>访客必须重新查看才能符合区段资格。</li></ul> |
