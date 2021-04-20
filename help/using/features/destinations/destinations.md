---
description: 在 Audience Manager 中，“目标”是指您要与之共享数据的任何第三方系统任何其他系统（广告服务器、DSP、广告网络等）。“目标生成器”是一个用于创建和管理 Cookie、URL 或服务器到服务器目标的工具。
keywords: 集成代码，目标，目标概述，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标
landing-page-description: 目标是要与其共享数据的任何第三方系统，如广告服务器或 DSP。使用目标生成器创建和管理 Cookie、URL 或服务器到服务器目标。
seo-title: 目标
solution: Audience Manager
title: 目标
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
translation-type: tm+mt
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 15%

---

# [!UICONTROL Destinations] 概述 {#destinations}

在Audience Manager中，[!UICONTROL destination]是任何第三方系统（广告服务器、[!DNL DSP]和广告网络等） 任何其他系统（广告服务器、DSP、广告网络等）。[!UICONTROL Destination Builder] 是您用于创建和管理、 [!UICONTROL cookie]或 [!DNL URL]的工 [!UICONTROL server-to-server destinations]具

## 用途和优势{#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 让您 [!UICONTROL Destination Builder] 创建细分 [!UICONTROL destinations] 用户的相关信息并将其发送给您的数据合作伙伴。这有助于您：

* **Protect数据值：** 您仅可共享有关合格用户的特 [!UICONTROL destination]定 [!UICONTROL Destination Builder] 信息，而不是将所有用户数据发送到。
* **对您的数据采取行动：向合** 作伙伴发送数 [!UICONTROL destination] 据可帮助他们快速开发和目标合格的受众细分。
* **降低技术开销：** 商业用户可以在界 [!UICONTROL destinations] 面中安全 [!UICONTROL Destination Builder] 设置。这有助于缩短部署前测试所需的时间。 使用[!UICONTROL Destination Builder]，您可以根据业务需求的变化创建、管理和删除[!UICONTROL destinations]，而无需经历漫长的开发周期。

## 技术考虑事项 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

数据投放取决于您的数据合作伙伴希望或能够接收[!UICONTROL destination]信息。 技术或工程限制可防止[!UICONTROL destination]通过[!DNL URL]、[!UICONTROL cookie]或[!UICONTROL server-to-server]进程接收数据。 与您的第三方合作伙伴合作，确定他们可以使用的方法。

## 业务考虑事项 {#business-considerations}

选择一种投放方法而不是另一种方法的业务决策取决于[!UICONTROL destination]合作伙伴的技术能力以及您对合格用户信息要做什么。 例如，如果[!UICONTROL destination]无法通过特定投放方法接收数据，技术约束可以限制您的选项。 但是，如果没有技术问题，您可以根据要如何对该数据执行操作来发送信息。 例如：

* [!DNL URL]并几乎 [!UICONTROL cookie-based destinations] 与页面上的用户操作同步工作。
* [!UICONTROL Server-to-server] 方法有助于随着时间推移构建深度受众段。

## [!UICONTROL Destination] 类型和典型使用  {#destination-types}

下表中的示例可以帮助您了解何时使用特定[!UICONTROL destination]以及每种类型之间的差异。

| [!UICONTROL Destination] 键入 | 通常在 | 示例 | 注意事项 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 您需要将数据发送到其他Adobe Experience Cloud解决方案。 | 向Adobe Analytics发送数据。 |  |
| **[!UICONTROL People-Based Destinations]** | 您需要将受众细分发送到基于人的环境，如Facebook。 | 根据现有客户的购买历史，为其提供个性化的优惠 | 受众定位是通过散列标识符完成的。 请参阅[基于人员的目标](people-based-destinations-overview.md)。 |
| **[!UICONTROL Device-Based Destinations]** (**服务器到服务器**) | <ul><li>不需要立即进行数据传输。</li><li>收集受众以构建一个大型的合格用户池。</li></ul> | 收集一段时间（小时或天）的活动，以在设置为稍后运行的数据中使用它。 | <ul><li>传输有关新站点和以前站点访客的数据。 </li><li>访客不必再被看到即可获得其他细分。</li></ul> |
| **[!UICONTROL Custom Destinations]** (**** URL或 **Cookie**) | 您需要立即传输数据，以便目标可以立即对合格用户执行操作。 | 从票证购买站点发送数据。 使用[!UICONTROL URL]或[!UICONTROL cookie destination]可确定用户资格并立即重新目标。 | <ul><li>仅传输有关新访客的数据。 </li><li>访客必须再次查看才能符合区段资格。</li></ul> |
