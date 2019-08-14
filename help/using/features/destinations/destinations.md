---
description: 在Audience Manager中，目标是任何第三方系统(广告服务器、DSP、广告网络等)。您希望与之共享数据的数据。目标生成器是用于创建和管理cookie、URL或服务器到服务器目标的工具。
keywords: 集成代码，目标，目标概述，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标
seo-description: 在Audience Manager中，目标是任何第三方系统(广告服务器、DSP、广告网络等)。您希望与之共享数据的数据。目标生成器是用于创建和管理cookie、URL或服务器到服务器目标的工具。
seo-title: 目标
solution: Audience Manager
title: 目标
uuid: 5c7dbdc-f73 f-46fe-9f12-7685e8 d7334 f
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# 目标概述 {#destinations}

在Audience Manager中，目标是任何第三方系统(广告服务器、 [!DNL DSP]广告网络等)。您希望与之共享数据的数据。[!UICONTROL Destination Builder] 是用于创建和管理cookie、 [!DNL URL]或服务器到服务器目标的工具。

## 用途和优势 {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations][!UICONTROL Destination Builder] 并允许您创建目标并将分段用户信息发送给数据合作伙伴。这有助于您：

* **保护数据值：** 不是将所有用户数据发送到目标，而是 [!UICONTROL Destination Builder] 允许您共享符合条件的用户的特定信息。
* **对您的数据采取行动：** 向目标合作伙伴发送数据可帮助他们快速开发和定位合格受众细分。
* **减少技术开销：** 商业用户可以安全地在 [!UICONTROL Destination Builder] 界面中设置目标。这有助于缩短预先部署测试所需的时间。借助 [!UICONTROL Destination Builder]，您可以在业务需求发生变化时创建、管理和删除目标，而无需在漫长的开发周期中工作。

## 技术考虑事项 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

数据交付取决于您的数据合作伙伴想要或可以接收目标信息的方式。技术或工程限制可能导致目标无法通过 [!DNL URL]、cookie或服务器到服务器流程接收数据。与第三方合作伙伴合作确定他们可以使用的方法。

## 业务考虑事项 {#business-considerations}

在另一种交付方法之间选择一种分发方法的业务决策取决于目标合作伙伴的技术能力以及您希望使用合格用户信息的功能。例如，如果目标无法通过特定的交付方法接收数据，则技术限制可以限制您的选项。但是，如果没有技术问题，则可以根据您希望对该数据采取操作的方式发送信息。例如：

* [!DNL URL]s和cookie提供的目标几乎与页面上的用户操作同步工作。
* 服务器到服务器的方法有利于随着时间的推移构建深度受众细分。

## 目标类型和典型用途 {#destination-types}

下表中的示例可帮助您了解何时使用特定目标以及各个类型之间的差异。

| 目标类型 | 通常使用时 | 示例 | 注意事项 |
|--- |--- |--- |--- |
| **URL** 或 **Cookie** | 您需要立即传输数据，以便目标能够立即对合格用户采取行动。 | 从售票站点发送数据。使用URL或cookie目标确定用户资格并立即重定向目标。 | <ul><li>只传输新访客的相关数据。 </li><li>访客必须再次查看才能获得该区段。</li></ul> |
| **服务器到服务器** | <ul><li>不需要立即进行数据传输。</li><li>收集数据以建立大量符合条件的用户群体。</li></ul> | 随着时间的推移收集数据(小时或天)，以将其用于在以后的日期运行的营销活动集中。 | <ul><li>传输有关新访客和以前访客的数据。 </li><li>访客无需再次查看即可获得其他区段。</li></ul> |
