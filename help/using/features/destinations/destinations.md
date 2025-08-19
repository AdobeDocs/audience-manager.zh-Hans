---
description: 了解目标（任何第三方系统，如您共享数据的广告服务器或 DSP）的优势、类型和用法。使用 Destination Builder 创建和管理 Cookie、URL 或服务器到服务器目标。
keywords: 集成代码，目标，目标概述，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标，目标
landing-page-description: 了解目标（任何第三方系统，如您共享数据的广告服务器或 DSP）的优势、类型和用法。使用 Destination Builder 创建和管理 Cookie、URL 或服务器到服务器目标。
short-description: 了解目标（任何第三方系统，如您共享数据的广告服务器或 DSP）的优势、类型和用法。使用 Destination Builder 创建和管理 Cookie、URL 或服务器到服务器目标。
seo-title: Destinations
solution: Audience Manager
title: 目标
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 19%

---

# [!UICONTROL Destinations]概述 {#destinations}

在Audience Manager中，[!UICONTROL destination]是您要与其共享数据的任何第三方系统（广告服务器、[!DNL DSP]、广告网络等）。 [!UICONTROL Destination Builder]是您用于创建和管理[!UICONTROL cookie]、[!DNL URL]或[!UICONTROL server-to-server destinations]的工具。

## 目的和优势 {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations]和[!UICONTROL Destination Builder]允许您创建[!UICONTROL destinations]并将有关分段用户的信息发送给您的数据合作伙伴。 这可帮助您：

* **保护数据值：**&#x200B;不是将所有用户数据发送到[!UICONTROL destination]，[!UICONTROL Destination Builder]允许您仅共享有关合格用户的特定信息。
* **对您的数据执行操作：**&#x200B;向[!UICONTROL destination]合作伙伴发送数据可帮助他们快速开发和定位符合条件的受众区段。
* **减少技术开销：**&#x200B;业务用户可以在[!UICONTROL destinations]界面中安全地设置[!UICONTROL Destination Builder]。 这有助于减少部署前测试所需的时间。 使用[!UICONTROL Destination Builder]，您可以根据业务需求的变化创建、管理和删除[!UICONTROL destinations]，而无需经历漫长的开发周期。

## 技术考虑事项 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

数据提交取决于您的数据合作伙伴希望或可以如何接收[!UICONTROL destination]信息。 技术或工程约束可能会阻止[!UICONTROL destination]通过[!DNL URL]、[!UICONTROL cookie]或[!UICONTROL server-to-server]进程接收数据。 与您的第三方合作伙伴合作，确定他们可以使用的方法。

## 业务考虑事项 {#business-considerations}

选择一种传递方法而不是另一种传递方法的业务决策取决于您的[!UICONTROL destination]合作伙伴的技术能力以及您希望如何处理符合条件的用户信息。 例如，如果[!UICONTROL destination]无法通过特定投放方法接收数据，则技术约束可以限制您的选项。 但是，如果没有技术问题，您可以发送基于您希望如何对该数据执行操作的信息。 例如：

* [!DNL URL]和[!UICONTROL cookie-based destinations]与页面上的用户操作几乎同步工作。
* [!UICONTROL Server-to-server]方法有助于随时间生成深层受众区段。

## [!UICONTROL Destination]类型和典型用法 {#destination-types}

下表中的示例可帮助您了解何时使用特定[!UICONTROL destination]以及每种类型之间的差异。

| [!UICONTROL Destination]类型 | 通常用于 | 示例 | 注意事项 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 您需要将数据发送到其他Adobe Experience Cloud解决方案。 | 正在将数据发送到Adobe Analytics。 |  |
| **[!UICONTROL People-Based Destinations]** | 您需要将受众区段发送到基于人员的环境，例如Facebook。 | 根据现有客户的购买历史记录，为其提供个性化优惠 | 受众定位通过哈希标识符完成。 查看[基于人员的目标](people-based-destinations-overview.md)。 |
| **[!UICONTROL Device-Based Destinations]** （**服务器到服务器**） | <ul><li>不需要立即传输数据。</li><li>正在收集数据以构建一个由合格用户组成的大型受众池。</li></ul> | 收集多时（小时或天）的数据，以将其用于设置为在以后日期运行的营销活动。 | <ul><li>传输有关新网站访客和以前网站访客的数据。 </li><li>访客无需再次查看即可获得其他区段的资格。</li></ul> |
| **[!UICONTROL Custom Destinations]** （**URL**&#x200B;或&#x200B;**Cookie**） | 您需要立即传输数据，以便目标可以立即对符合条件的用户执行操作。 | 从购票站点发送数据。 使用[!UICONTROL URL]或[!UICONTROL cookie destination]授予用户资格并立即重新定位。 | <ul><li>仅传输有关新访客的数据。 </li><li>必须再次查看访客才能获得该区段的资格。</li></ul> |
