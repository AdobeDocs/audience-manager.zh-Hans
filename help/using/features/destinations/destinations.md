---
description: 在Audience manager中，目标是任何第三方系统（广告服务器、DSP和网络等）要与之共享数据。 Destination builder是用于创建和管理Cookie、URL或服务器到服务器目标的工具。
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: 在Audience manager中，目标是任何第三方系统（广告服务器、DSP和网络等）要与之共享数据。 Destination builder是用于创建和管理Cookie、URL或服务器到服务器目标的工具。
seo-title: 目标
solution: Audience Manager
title: 目标
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
translation-type: tm+mt
source-git-commit: 431a254f1a70958db29621a59acc6239d2a6b005

---


# Destinations Overview {#destinations}

在Audience manager中，目标是任何第三方系统(广告服 [!DNL DSP]务器、广告网络等)要与之共享数据。 [!UICONTROL Destination Builder] 是用于创建和管理cookie、服务器到服 [!DNL URL]务器目标的工具。

## 用途和优势 {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 并让 [!UICONTROL Destination Builder] 您创建目标，并将细分用户的相关信息发送给您的数据合作伙伴。 这有助于您：

* **** 保护数据价值：您只能共享有关合格用户的特定信息，而 [!UICONTROL Destination Builder] 不是将所有用户数据发送到目标。
* **** 对数据采取操作：向目标合作伙伴发送数据可帮助他们快速开发和定位合格的受众细分。
* **** 降低技术开销：商业用户可以在界面中安全地设置 [!UICONTROL Destination Builder] 目标。 这有助于缩短部署前测试所需的时间。 您 [!UICONTROL Destination Builder]可以随业务需求变化创建、管理和删除目标，而无需经历漫长的开发周期。

## 技术考虑事项 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

数据交付取决于您的数据合作伙伴希望或能够如何接收目标信息。 技术或工程限制可能会阻止目标通过 [!DNL URL]、cookie或服务器到服务器进程接收数据。 与您的第三方合作伙伴合作以确定他们可以使用的方法。

## 业务考虑事项 {#business-considerations}

根据目标合作伙伴的技术能力以及您对合格用户信息的处理情况，决定如何选择一种交付方法而不是另一种交付方法。 例如，如果目标无法通过特定的交付方法接收数据，技术限制可以限制您的选项。 但是，如果没有技术问题，您可以根据要如何对该数据执行操作来发送信息。 例如：

* [!DNL URL]s和基于cookie的目标与页面上的用户操作几乎同步工作。
* 服务器到服务器方法有助于随着时间的推移构建深层受众细分。

## 目标类型和典型用途 {#destination-types}

下表中的示例可以帮助您了解何时使用特定目标以及每种类型之间的差异。

| 目标类型 | 通常在 | 示例 | 注意事项 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 您需要将数据发送到其他Adobe Experience cloud解决方案。 | 向Adobe Analytics发送数据。 |  |
| **[!UICONTROL People-Based Destinations]** | 您需要将受众细分发送到基于人员的环境，如Facebook。 | 根据现有客户的购买历史向其提供个性化的优惠 | 受众定位是通过散列标识符完成的。 查看 [基于人员的目标](people-based-destinations-overview.md) |
| **[!UICONTROL Device-Based Destinations]**(**&#x200B;服务器到服务器&#x200B;**) | <ul><li>无需立即进行数据传输。</li><li>收集数据以构建大量合格用户的受众池。</li></ul> | 收集一段时间（小时或天）的数据，以将其用于营销活动集，以便在以后的日期运行。 | <ul><li>传输有关新访客和先前站点访客的数据。 </li><li>访客不必再被看到即可获得其他区段。</li></ul> |
| **[!UICONTROL Custom Destinations]**(** URL **或** Cookie **) | 您需要立即传输数据，以便目标可以立即对合格用户执行操作。 | 从票证购买站点发送数据。 使用URL或Cookie目标来确定用户资格并立即重新定位。 | <ul><li>仅传输有关新访客的数据。 </li><li>必须再次查看访客才能获得区段资格。</li></ul> |

