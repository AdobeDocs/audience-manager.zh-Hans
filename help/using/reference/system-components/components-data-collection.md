---
description: 数据收集组件包括数据收集服务器、DILAPI、入站服务器到服务器数据传输和日志文件。
seo-description: 数据收集组件包括数据收集服务器、DILAPI、入站服务器到服务器数据传输和日志文件。
seo-title: 数据收集组件
solution: Audience Manager
title: 数据收集组件
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: 系统组件
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 7%

---

# 数据收集组件{#data-collection-components}

数据收集组件包括数据收集服务器、DILAPI、入站服务器到服务器数据传输和日志文件。

<!-- 

c_compcollect.xml

 -->

Audience Manager包含以下数据收集组件：

* [数据收集服务器(DCS)和配置文件缓存服务器(PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [数据集成库 (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [入站服务器到服务器](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [日志文件](../../reference/system-components/components-data-collection.md#log-files)

## 数据收集服务器(DCS)和配置文件缓存服务器(PCS){#dcs-pcs}

DCS和PCS协同工作，分别提供与特征实现、受众分段和数据存储相关的服务。

**[!UICONTROL Data Collection Servers (DCS)]函数**

在[!DNL Audience Manager]中，DCS:

* 通过事件调用接收并评估特征数据。 这包括用于实时分段的信息以及通过服务器到服务器传输按计划时间间隔传入的数据。
* 根据用户已实现的特征和您使用[区段生成器](../../features/segments/segment-builder.md)创建的资格规则对用户进行分段。
* 创建和管理设备ID和经过验证的配置文件ID。 这包括数据提供程序ID、用户ID、声明的ID、集成代码等标识符。
* 检查PCS中用户在实时事件调用之前已实现的其他特征。 这样，DCS便可以根据实时数据和历史数据确定用户资格。
* 写入日志文件，并将这些文件发送到分析系统以进行存储和处理。

**[!DNL DCS]通过管理需求[!UICONTROL Global Server Load Balancing (GSLB)]**

[!DNL DCS]是一个地理上分布的负载均衡系统。 这意味着[!DNL Audience Manager]可以根据站点访客的地理位置向区域数据中心发送请求和从区域数据中心发送请求。 此策略有助于缩短响应时间，因为[!DNL DCS]响应会直接发送到包含该访客相关信息的数据中心。 [!UICONTROL GSLB] 可提高系统的效率，因为相关数据会缓存在最接近用户的服务器中。

>[!IMPORTANT]
>
>[!DNL DCS]仅检测来自使用IPv4的设备的Web流量。

在事件调用中，地理位置是在较大的JSON数据正文中返回的键值对中捕获的。 此键值对是`"dcs_region": region ID`参数。

![](assets/dcs-map.png)

作为客户，您需要通过我们的数据收集代码间接与[!DNL DCS]进行交互。 您还可以通过一组API直接与[!DNL DCS]一起使用。 请参阅[数据收集服务器(DCS)API方法和代码](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)。

**[!UICONTROL Profile Cache Servers (PCS)]**

[!UICONTROL PCS]是大型数据库（基本上是大型服务器端Cookie）。 它可以存储通过服务器到服务器传输和 [!DNL DCS] 接收的有关活动用户的数据。[!UICONTROL PCS] 数据包含设备 ID、经过验证的配置文件 ID 以及与这些 ID 关联的特征。当[!DNL DCS]收到实时调用时，它会检查[!UICONTROL PCS]中用户可能属于或有资格参加的其他特征。 此外，如果稍后将某个特征添加到区段，则这些特征ID会添加到[!UICONTROL PCS]，用户无需访问特定网站或应用程序即可自动符合该区段的条件。 [!UICONTROL PCS]有助于加深[!DNL Audience Manager]对用户的了解，因为它可以实时或在后台使用新的历史特征数据进行用户匹配和细分。 与仅从实时资格获得相比，这种行为可让您更完整、更准确地了解用户。

没有UI控件可允许我们的客户直接使用[!UICONTROL PCS]。 客户通过其数据存储和数据传输角色间接访问[!UICONTROL PCS]。 [!UICONTROL PCS]在Apache Cassandra上运行。

**从[!UICONTROL PCS]**

如前所述，[!UICONTROL PCS]存储活动用户的特征ID。 活动用户是指在过去14天中从任何域中看到[边缘数据服务器](../../reference/system-components/components-edge.md)的任何用户。 对[!UICONTROL PCS]的这些调用将用户保持活动状态：

* [!DNL /event] 调用
* [!DNL /ibs] 调用（ID同步）

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

如果特征处于不活动状态17天，则[!UICONTROL PCS]会刷新特征。 但是，这些特征并未丢失。 它们存储在Hadoop中。 如果用户在另一次被再次看到，则Hadoop会将其所有特征推送回[!UICONTROL PCS]，通常是在24小时内。

**其他 [!UICONTROL DCS/PCS] 过程：隐私选择退出**

这些服务器系统处理隐私请求和用户选择退出请求。 如果用户选择退出数据收集，则不会在日志文件中收集用户Cookie信息。 有关我们的隐私政策的更多信息，请参阅[Adobe隐私中心](https://www.adobe.com/cn/privacy/advertising-services.html)。

## 数据集成库 (DIL) {#dil}

[!UICONTROL DIL] 是您放置在页面上以进行数据收集的代码。有关可用服务和方法的更多信息，请参阅[DILAPI](../../dil/dil-overview.md) 。

## 入站服务器到服务器{#inbound-outbound-server}

这些系统接收通过与客户端的各种服务器到服务器集成发送的数据。 有关更多信息，请参阅[发送受众数据](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md)的文档。

## 日志文件 {#log-files}

[!UICONTROL PCS]会创建数据并将其写入日志文件。 这些数据库将发送到其他数据库系统，以便进行处理、报告和存储。

>[!MORELIKETHIS]
>
>* [Adobe 隐私中心](https://www.adobe.com/cn/privacy.html)

