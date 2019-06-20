---
description: 数据收集组件包括数据收集服务器、DIL API、入站服务器到服务器数据传输以及日志文件。
seo-description: 数据收集组件包括数据收集服务器、DIL API、入站服务器到服务器数据传输以及日志文件。
seo-title: 数据收集组件
solution: Audience Manager
title: 数据收集组件
uuid: 51bb1719-5ff2-4bc7-8eb1-97895e05d08f
translation-type: tm+mt
source-git-commit: 0b9da38fd8b999637bdf6c3fe6af8aa2426eb6ae

---


# Data Collection Components{#data-collection-components}

数据收集组件包括数据收集服务器、DIL API、入站服务器到服务器数据传输以及日志文件。

<!-- 

c_compcollect.xml

 -->

Audience Manager包含以下数据收集组件：

* [数据收集服务器(DCS)和配置文件缓存服务器(PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [数据集成库 (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [入站服务器到服务器](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [日志文件](../../reference/system-components/components-data-collection.md#log-files)

## Data Collection Servers (DCS) and Profile Cache Servers (PCS) {#dcs-pcs}

DCS和PCS协同工作，并单独提供与特征实现、受众细分和数据存储相关的服务。

**[!UICONTROL Data Collection Servers (DCS)]函数**

In [!DNL Audience Manager], the DCS:

* 接收并评估来自事件调用的特征数据。这包括用于按服务器到服务器传输以预定间隔通过预定间隔传递的实时细分和数据的信息。
* Segments users based on their realized traits and the qualification rules you create with [Segment Builder](../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74).
* 创建和管理设备ID和经过身份验证的配置文件ID。其中包括标识符ID、用户ID、声明ID、集成代码等标识符。
* 检查PCS是否为用户在实时事件调用之前已意识到的其他特征。这使DCS能够根据实时数据和历史数据确定用户资格。
* 编写日志文件并将这些文件发送到分析系统以进行存储和处理。

**[!UICONTROL DCS]管理需求[!UICONTROL Global Server Load Balancing (GSLB)]**

[!UICONTROL DCS] 这是地理分布式和负载平衡系统。This means [!DNL Audience Manager] can direct requests to and from a regional data center based on the geographic location of a site visitor. This strategy helps improve response times because a [!UICONTROL DCS] response goes directly to a data center that contains information about that visitor. [!UICONTROL GSLB] 使我们的系统高效，因为相关数据在最接近用户的服务器中缓存。

>[!IMPORTANT]
>
>The [!UICONTROL DCS] only detects web traffic originating from devices that use IPv4.

在事件调用中，地理位置是在更大的JSON数据正文中返回的键值对中捕获的。This key-value pair is the `"dcs_region": region ID` parameter.

![](assets/dcs-map.png)

As a customer, you engage with the [!UICONTROL DCS] indirectly through our data collection code. You can also work directly with the [!UICONTROL DCS] through a set of APIs. See [Data Collection Server (DCS) API Methods and Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

The [!UICONTROL PCS] is a large database (basically, a huge server-side cookie). It stores data received for active users from server-to-server transfers and the [!UICONTROL DCS]. [!UICONTROL PCS] 数据包括设备ID、经过身份验证的配置文件ID及其关联特征。When the [!UICONTROL DCS] receives a real time call, it checks the [!UICONTROL PCS] for other traits a user may belong to or qualify for. And, if a trait is added to a segment at a later time, those trait IDs are added to the [!UICONTROL PCS] and users can qualify for that segment automatically, without a visit to a particular site or app. The [!UICONTROL PCS] helps deepen [!DNL Audience Manager]&#39;s understanding of your users because it can match and segment users in real time or behind the scenes with new and historic trait data. 这种行为为您提供了更完整、准确的用户图片，而不是仅限实时条件。

There are no UI controls that lets our customers work directly with the [!UICONTROL PCS]. Customer access to the [!UICONTROL PCS] is indirect, through its role as a data store and data transfers. The [!UICONTROL PCS] runs on Apache Cassandra.

**清除来自[!UICONTROL PCS]**

As indicated previously, the [!UICONTROL PCS] stores trait IDs for active users. An active user is any user who has been seen by the [edge data servers](../../reference/system-components/components-edge.md) from any domain during the last 14-days. These calls to the [!UICONTROL PCS] keep a user in an active state:

* [!DNL /event] 调用
* [!DNL /ibs] 调用(ID同步)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

[!UICONTROL PCS] 如果17天内它们处于非活动状态，则出现多余的特征。但是，这些特征并不会丢失。它们存储在Hadoop中。If the user is seen again at another time, then Hadoop pushes all of their traits back to the [!UICONTROL PCS], typically within a 24-hour period.

**其他[!UICONTROL DCS/PCS]流程：隐私选择退出**

这些服务器系统处理隐私和用户选择退出请求。如果用户已退出数据收集，则用户cookie信息不会在日志文件中收集。For more information about our privacy policies see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

## 数据集成库 (DIL) {#dil}

[!UICONTROL DIL] 是您放在页面上的用于数据收集的代码。See the [DIL API](../../dil/dil-overview.md) for more information about available services and methods.

## Inbound Server-to-Server {#inbound-outbound-server}

这些系统是接收通过与我们的客户不同的服务器与服务器集成所发送数据的系统。See the documentation on [sending audience data](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) for more information.

## 日志文件 {#log-files}

The [!UICONTROL PCS] creates and writes data to the log files. 它们会发送到其他数据库系统以进行处理、报告和存储。

>[!MORE_ LIKE_ This]
>
>* [Adobe 隐私权中心](https://www.adobe.com/privacy.html)

