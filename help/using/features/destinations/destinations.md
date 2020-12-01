---
description: 在 Audience Manager 中，目标是您要与之共享数据的任何第三方系统任何其他系统（广告服务器、DSP、广告网络等）。目标生成器是一个用于创建和管理 Cookie、URL 或服务器到服务器目标的工具。
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: 在 Audience Manager 中，目标是您要与之共享数据的任何第三方系统任何其他系统（广告服务器、DSP、广告网络等）。目标生成器是一个用于创建和管理 Cookie、URL 或服务器到服务器目标的工具。
seo-title: 目标
solution: Audience Manager
title: 目标
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 17%

---


# [!UICONTROL Destinations] 概述 {#destinations}

在Audience Manager中，[!UICONTROL destination]是任何第三方系统（广告服务器、[!DNL DSP]和广告网络等） 任何其他系统（广告服务器、DSP、广告网络等）。[!UICONTROL Destination Builder] 是用于创建和管理、 [!UICONTROL cookie]或 [!DNL URL]的工 [!UICONTROL server-to-server destinations]具

## 用途和优势{#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 并可 [!UICONTROL Destination Builder] 以创建细 [!UICONTROL destinations] 分用户的相关信息并将其发送给数据合作伙伴。这有助于您：

* **Protect数据** 值：您只能共享有关合格用 [!UICONTROL destination]户的 [!UICONTROL Destination Builder] 特定信息，而不是将所有用户数据发送到。
* **对数据采取行动：向合** 作伙伴发送数 [!UICONTROL destination] 据可帮助他们快速开发和目标合格的受众细分。
* **降低技术开销：** 商业用户可以在界 [!UICONTROL destinations] 面中安全 [!UICONTROL Destination Builder] 设置。这有助于缩短部署前测试所需的时间。 使用[!UICONTROL Destination Builder]，您可以根据业务需求的变化创建、管理和删除[!UICONTROL destinations]，所有这些都无需经历漫长的开发周期。

## 技术考虑事项 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

数据投放取决于您的数据合作伙伴希望或能够接收[!UICONTROL destination]信息的方式。 技术或工程限制可阻止[!UICONTROL destination]通过[!DNL URL]、[!UICONTROL cookie]或[!UICONTROL server-to-server]进程接收数据。 与您的第三方合作伙伴合作，确定他们可以使用的方法。

## 业务考虑事项 {#business-considerations}

选择一种投放方法而不是另一种方法的业务决策取决于[!UICONTROL destination]合作伙伴的技术能力以及您希望如何处理合格的用户信息。 例如，如果[!UICONTROL destination]无法通过特定投放方法接收数据，技术约束可以限制您的选项。 但是，如果没有技术问题，您可以根据要如何对该数据执行操作来发送信息。 例如：

* [!DNL URL]和几 [!UICONTROL cookie-based destinations] 乎与页面上的用户操作同步工作。
* [!UICONTROL Server-to-server] 方法有利于长期构建深层受众段。

## [!UICONTROL Destination] 类型和典型使用  {#destination-types}

下表中的示例可以帮助您了解何时使用特定[!UICONTROL destination]以及每种类型之间的差异。

| [!UICONTROL Destination] 键入 | 通常在 | 示例 | 注意事项 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 您需要将数据发送到Adobe Experience Cloud的其他解决方案。 | 向Adobe Analytics发送数据。 |  |
| **[!UICONTROL People-Based Destinations]** | 您需要将受众细分发送给基于人的环境，如Facebook。 | 根据现有客户的购买历史向其提供个性化优惠 | 受众定位是通过散列标识符完成的。 请参阅[基于人员的目标](people-based-destinations-overview.md)。 |
| **[!UICONTROL Device-Based Destinations]** (**服务器到服务器**) | <ul><li>无需立即进行数据传输。</li><li>收集受众以构建一个大型合格用户池。</li></ul> | 收集一段时间（小时或天）的活动，以在设置为稍后运行的数据中使用它。 | <ul><li>传输有关新站点和以前站点访客的数据。 </li><li>访客无需再被看到即可获得其他细分。</li></ul> |
| **[!UICONTROL Custom Destinations]** (**** URL或 **Cookie**) | 您需要立即传输数据，以便目标可以立即对合格用户执行操作。 | 从票证购买站点发送数据。 使用[!UICONTROL URL]或[!UICONTROL cookie destination]可确定用户资格并立即重新目标。 | <ul><li>仅传输有关新访客的数据。 </li><li>访客必须重新查看才能符合区段资格。</li></ul> |
