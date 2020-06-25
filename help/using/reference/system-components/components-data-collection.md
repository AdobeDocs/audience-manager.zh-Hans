---
description: 数据收集组件包括数据收集服务器、DIL API、入站服务器到服务器数据传输和日志文件。
seo-description: 数据收集组件包括数据收集服务器、DIL API、入站服务器到服务器数据传输和日志文件。
seo-title: 数据收集组件
solution: Audience Manager
title: 数据收集组件
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 7%

---


# 数据收集组件{#data-collection-components}

数据收集组件包括数据收集服务器、DIL API、入站服务器到服务器数据传输和日志文件。

<!-- 

c_compcollect.xml

 -->

Audience Manager包含以下数据收集组件：

* [数据收集服务器(DCS)和用户档案缓存服务器(PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [数据集成库 (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [入站服务器到服务器](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [日志文件](../../reference/system-components/components-data-collection.md#log-files)

## 数据收集服务器(DCS)和用户档案缓存服务器(PCS) {#dcs-pcs}

DCS和PCS协同工作，分别提供与特征实现、受众细分和数据存储相关的服务。

**[!UICONTROL Data Collection Servers (DCS)]函数&#x200B;**

在 [!DNL Audience Manager]DCS中：

* 从事件调用接收和评估特征数据。 这包括用于实时细分的信息以及按预定时间间隔通过服务器到服务器传输传入的数据。
* 根据用户的已实现特征和您使用Segment Builder创建的资格规则对用 [户进行细分](../../features/segments/segment-builder.md)。
* 创建和管理设备ID和经过身份验证的用户档案ID。 这包括诸如数据提供者ID、用户ID、声明的ID、集成代码等标识符。
* 检查PCS在实时事件调用之前是否已经实现其他特征。 这样，DCS可以根据实时数据和历史数据来确定用户资格。
* 写入日志文件，并将其发送到分析系统以进行存储和处理。

**[!DNL DCS]通过[!UICONTROL Global Server Load Balancing (GSLB)]**

The [!DNL DCS] is a geographically distributed and load-balanced system. 这意味着 [!DNL Audience Manager] 可以根据站点访客的地理位置，将请求定向到区域数据中心和从区域数据中心发出请求。 此策略有助于缩短响应时间，因 [!DNL DCS] 为响应会直接发送到包含该访客信息的数据中心。 [!UICONTROL GSLB] 由于相关数据缓存在最接近用户的服务器中，因此我们的系统更高效。

>[!IMPORTANT]
>
>仅检 [!DNL DCS] 测来自使用IPv4的设备的Web流量。

在事件调用中，地理位置在较大的JSON数据体中返回的键值对中捕获。 此键值对是参 `"dcs_region": region ID` 数。

![](assets/dcs-map.png)

作为客户，您通过我们的数 [!DNL DCS] 据收集代码间接进行接洽。 您还可以通过一 [!DNL DCS] 组API直接使用。 See [Data Collection Server (DCS) API Methods and Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

它是 [!UICONTROL PCS] 一个大型数据库（基本上是一个巨大的服务器端cookie）。 它可以存储通过服务器到服务器传输和 [!DNL DCS] 接收的有关活动用户的数据。[!UICONTROL PCS] 数据包含设备 ID、经过验证的配置文件 ID 以及与这些 ID 关联的特征。当收 [!DNL DCS] 到实时呼叫时，它检查用户 [!UICONTROL PCS] 可能属于或符合的其他特征。 而且，如果某个特征稍后添加到区段，则这些特征ID会添加到该区段 [!UICONTROL PCS] ，用户无需访问特定站点或应用程序即可自动获得该区段的资格。 它 [!UICONTROL PCS] 有助于 [!DNL Audience Manager]加深对用户的了解，因为它可以实时或在后台使用新的历史特征数据匹配和细分用户。 与仅通过实时资格验证相比，此行为可为您提供更完整、准确的用户信息。

没有UI控件可让我们的客户直接使用 [!UICONTROL PCS]。 客户通过其作 [!UICONTROL PCS] 为数据存储和数据传输的角色间接访问。 阿帕 [!UICONTROL PCS] 奇·卡桑德拉。

**从[!UICONTROL PCS]**

如前所示，存储 [!UICONTROL PCS] 活动用户的特征ID。 活动用户是过去14天内从任何域 [的边缘数据](../../reference/system-components/components-edge.md) 服务器看到的任何用户。 用户处于活 [!UICONTROL PCS] 动状态的以下调用：

* [!DNL /event] 呼叫
* [!DNL /ibs] 调用（ID同步）

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

如果 [!UICONTROL PCS] 特征在17天内处于非活动状态，则该特征将刷新。 但是，这些特征并没有丢失。 它们存储在Hadoop中。 如果用户在另一时间再次被看到，则Hadoop会将其所有特征推回 [!UICONTROL PCS]Hadoop，通常在24小时内。

**其他[!UICONTROL DCS/PCS]过程： 隐私选择退出**

这些服务器系统处理隐私和用户选择退出请求。 如果用户已选择退出数据收集，则不会在日志文件中收集用户Cookie信息。 有关我们的隐私政策的更多信息，请参 [阅Adobe隐私中心](https://www.adobe.com/cn/privacy/advertising-services.html)。

## 数据集成库 (DIL) {#dil}

[!UICONTROL DIL] 是您放在页面上进行数据收集的代码。 有关可 [用服务和方法](../../dil/dil-overview.md) ，请参阅DIL API。

## 入站服务器到服务器 {#inbound-outbound-server}

这些系统接收通过各种服务器到服务器集成与客户端发送的数据。 有关详细信息， [请参阅有关发送受众](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) 数据的文档。

## 日志文件 {#log-files}

创建 [!UICONTROL PCS] 数据并将其写入日志文件。 这些数据库会发送到其他报告库系统，以便进行处理、存储。

>[!MORELIKETHIS]
>
>* [Adobe 隐私中心](https://www.adobe.com/cn/privacy.html)

