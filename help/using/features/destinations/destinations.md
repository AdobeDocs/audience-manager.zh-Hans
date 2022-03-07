---
description: 了解目标（任何第三方系统，如您共享数据的广告服务器或 DSP）的优势、类型和用法。使用 Destination Builder 创建和管理 Cookie、URL 或服务器到服务器目标。
keywords: 集成代码，目标，目标概述，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标
landing-page-description: 了解目标（任何第三方系统，如您共享数据的广告服务器或 DSP）的优势、类型和用法。使用 Destination Builder 创建和管理 Cookie、URL 或服务器到服务器目标。
seo-title: Destinations
solution: Audience Manager
title: 目标
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 865800eb076811db38aec8e98714ad9712804f77
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 15%

---

# [!UICONTROL Destinations] 概述 {#destinations}

在Audience Manager中， [!UICONTROL destination] 是任何第三方系统(广告服务器， [!DNL DSP]、广告网络等) 任何其他系统（广告服务器、DSP、广告网络等）。[!UICONTROL Destination Builder] 是用于创建和管理的工具 [!UICONTROL cookie], [!DNL URL]或 [!UICONTROL server-to-server destinations].

## 用途和优势 {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 和 [!UICONTROL Destination Builder] 允许您创建 [!UICONTROL destinations] 并将有关分段用户的信息发送给您的数据合作伙伴。 这有助于您：

* **Protect数据值：** 而不是将所有用户数据发送到 [!UICONTROL destination], [!UICONTROL Destination Builder] 允许您仅共享有关合格用户的特定信息。
* **对数据采取操作：** 向发送数据 [!UICONTROL destination] 合作伙伴可帮助他们快速开发和定位符合条件的受众区段。
* **减少技术开销：** 企业用户可以设置 [!UICONTROL destinations] 安全地 [!UICONTROL Destination Builder] 界面。 这有助于缩短部署前测试所需的时间。 使用 [!UICONTROL Destination Builder]，您可以创建、管理和删除 [!UICONTROL destinations] 随着业务需求的变化，所有这些都无需经过漫长的开发周期。

## 技术考虑事项 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

数据交付取决于您的数据合作伙伴希望或能够接收 [!UICONTROL destination] 信息。 技术或工程限制可能会阻止 [!UICONTROL destination] 从 [!DNL URL], [!UICONTROL cookie]或 [!UICONTROL server-to-server] 进程。 与您的第三方合作伙伴合作，确定他们可以使用的方法。

## 业务考虑事项 {#business-considerations}

选择一种交付方法而不是另一种交付方法的业务决策取决于您的 [!UICONTROL destination] 合作伙伴，以及您希望使用符合条件的用户信息执行的操作。 例如，如果 [!UICONTROL destination] 无法通过特定提交方法接收数据。 但是，如果没有技术问题，您可以根据要对该数据执行操作的方式发送信息。 例如：

* [!DNL URL]s和 [!UICONTROL cookie-based destinations] 与页面上的用户操作几乎同步工作。
* [!UICONTROL Server-to-server] 方法有助于随着时间的推移构建深层受众区段。

## [!UICONTROL Destination] 类型和典型用法 {#destination-types}

下表中的示例可帮助您了解何时使用特定 [!UICONTROL destination] 以及每种类型之间的差异。

| [!UICONTROL Destination] 键入 | 通常在 | 示例 | 注意事项 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 您需要将数据发送到其他Adobe Experience Cloud解决方案。 | 向Adobe Analytics发送数据。 |  |
| **[!UICONTROL People-Based Destinations]** | 您需要将受众区段发送到基于人员的环境，如Facebook。 | 根据现有客户的购买历史记录，向其提供个性化优惠 | 受众定位通过经过哈希处理的标识符完成。 请参阅 [基于人员的目标](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**服务器到服务器**) | <ul><li>不需要立即进行数据传输。</li><li>收集数据以构建大量合格用户受众池。</li></ul> | 收集一段时间（小时或天）的数据，以在营销活动集中使用，以在以后的日期运行。 | <ul><li>传输有关新访客和以前的网站访客的数据。 </li><li>访客无需再次被看到即可符合其他区段的资格。</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** 或 **Cookie**) | 您需要立即传输数据，以便目标可以立即对符合条件的用户执行操作。 | 从票证购买网站发送数据。 使用 [!UICONTROL URL] 或 [!UICONTROL cookie destination] 以确定用户资格并立即重新定位。 | <ul><li>仅传输有关新访客的数据。 </li><li>必须再次向访客显示才能符合区段资格。</li></ul> |
