---
description: 数据收集组件包括数据收集服务器、DIL API、入站服务器到服务器数据传输和日志文件。
seo-description: Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.
seo-title: Data Collection Components
solution: Audience Manager
title: 数据收集组件
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 3%

---

# 数据收集组件{#data-collection-components}

数据收集组件包括数据收集服务器、DIL API、入站服务器到服务器数据传输和日志文件。

<!-- 

c_compcollect.xml

 -->

Audience Manager包含以下数据收集组件：

* [数据收集服务器(DCS)和配置文件缓存服务器(PC)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [数据集成库 (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [入站服务器到服务器](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [日志文件](../../reference/system-components/components-data-collection.md#log-files)

## 数据收集服务器(DCS)和配置文件缓存服务器(PCS) {#dcs-pcs}

DCS和PCS可协同工作，分别提供与特征实现、受众分段和数据存储相关的服务。

**[!UICONTROL Data Collection Servers (DCS)]函数**

在[!DNL Audience Manager]中，DCS：

* 接收并评估来自事件调用的特征数据。 这包括用于实时分段的信息以及服务器到服务器传输按计划时间间隔传入的数据。
* 根据用户已实现的特性和您使用[区段生成器](../../features/segments/segment-builder.md)创建的资格规则来划分用户。
* 创建并管理设备ID和已验证的配置文件ID。 这包括标识符，例如数据提供程序ID、用户ID、声明的ID、集成代码等。
* 在PC中检查用户在实时事件调用之前已实现的其他特征。 这样，DCS即可根据实时数据和历史数据来决定用户资格。
* 写入日志文件并将其发送到Analytics系统以进行存储和处理。

**[!DNL DCS]通过[!UICONTROL Global Server Load Balancing (GSLB)]**&#x200B;管理需求

[!DNL DCS]是地理上分布且负载平衡的系统。 这意味着[!DNL Audience Manager]可以根据站点访客的地理位置向区域数据中心发出请求，也可以从区域数据中心发出请求。 此策略有助于缩短响应时间，因为[!DNL DCS]响应将直接发送到包含该访客相关信息的数据中心。 [!UICONTROL GSLB]使我们的系统变得高效，因为相关数据已缓存在距离用户最近的服务器中。

>[!IMPORTANT]
>
>[!DNL DCS]仅检测来自使用IPv4的设备的Web流量。

在事件调用中，地理位置被捕获到在较大的JSON数据体中返回的键值对中。 此键值对是`"dcs_region": region ID`参数。

![](assets/dcs-map.png)

作为客户，您通过我们的数据收集代码间接与[!DNL DCS]互动。 您还可以通过一组API直接使用[!DNL DCS]。 请参阅[数据收集服务器(DCS) API方法和代码](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)。

**[!UICONTROL Profile Cache Servers (PCS)]**

[!UICONTROL PCS]是一个大型数据库（基本上是一个大型服务器端Cookie）。 它可以存储通过服务器到服务器传输和 [!DNL DCS] 接收的有关活动用户的数据。[!UICONTROL PCS]数据包含设备ID、经过身份验证的配置文件ID以及与这些ID关联的特征。 当[!DNL DCS]收到实时调用时，它将检查[!UICONTROL PCS]中用户可能属于或符合条件的其他特征。 此外，如果某个特征在稍后添加到区段，则这些特征ID将会添加到[!UICONTROL PCS]，用户便会自动符合该区段的资格条件，而无需访问特定网站或应用程序。 [!UICONTROL PCS]有助于深化[!DNL Audience Manager]对您的用户的理解，因为它可以使用新的和历史特征数据实时匹配和分段用户，或者在后台进行分段。 与仅通过实时资格认证相比，这种行为可让您更全面、更准确地了解用户。

没有允许我们的客户直接使用[!UICONTROL PCS]的UI控件。 客户对[!UICONTROL PCS]的访问是间接的，通过其作为数据存储和数据传输的角色。 [!UICONTROL PCS]在Apache Cassandra上运行。

**正在从[!UICONTROL PCS]**&#x200B;中清除非活动ID

如前所述，[!UICONTROL PCS]存储了活动用户的特征ID。 活动用户是过去14天内[边缘数据服务器](../../reference/system-components/components-edge.md)从任何域看到的任何用户。 对[!UICONTROL PCS]的这些调用将用户保留在活动状态：

* [!DNL /event]呼叫
* [!DNL /ibs]调用（ID同步）

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

如果[!UICONTROL PCS]在17天内不活动，则会刷新特征。 但是，这些特征不会丢失。 它们存储在Hadoop中。 如果某个用户在其他时间再次被看到，则Hadoop会将其所有特征推送回[!UICONTROL PCS]，通常在24小时内。

**其他[!UICONTROL DCS/PCS]进程：隐私选择退出**

这些服务器系统处理隐私和用户选择退出请求。 如果用户已选择退出数据收集，则不会收集日志文件中的用户Cookie信息。 有关隐私政策的更多信息，请参阅[Adobe隐私中心](https://www.adobe.com/cn/privacy/advertising-services.html)。

## 数据集成库 (DIL) {#dil}

[!UICONTROL DIL]是您放置在页面上用于数据收集的代码。 有关可用服务和方法的更多信息，请参阅[DIL API](../../dil/dil-overview.md)。

## 入站服务器到服务器 {#inbound-outbound-server}

这些系统接收通过我们的客户端的各种服务器到服务器集成发送的数据。 有关详细信息，请参阅有关[发送受众数据](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md)的文档。

## 日志文件 {#log-files}

[!UICONTROL PCS]创建数据并将数据写入日志文件。 这些数据库被发送到其他数据库系统进行处理、报告和存储。

>[!MORELIKETHIS]
>
>* [Adobe 隐私权中心](https://www.adobe.com/cn/privacy.html)
