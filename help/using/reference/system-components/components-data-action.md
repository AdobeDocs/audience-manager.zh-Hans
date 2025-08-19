---
description: 数据操作组件包括客户数据馈送、数据收集服务器、SFTP/S3/HTTP发布者、IRIS和配置文件缓存服务器。
seo-description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-title: Data Action Components
solution: Audience Manager
title: 数据操作组件
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: System Components
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 1%

---

# 数据操作组件{#data-action-components}

数据操作组件包括客户数据馈送、数据收集服务器、SFTP/S3/HTTP发布者、IRIS和配置文件缓存服务器。

<!-- 

c_compact.xml

 -->

操作组件是系统和流程，可让您将数据移入和移出[!DNL Audience Manager]，并（由于缺少更好的短语）对其进行处理。 这些[!DNL Audience Manager]组件包括：

## 客户数据信息源 (CDF) {#cdf}

[!UICONTROL CDF]是每小时发送给客户的文件。 它们包含用户ID以及关联的区段ID、特征ID和其他数据。 有关详细信息，请参阅[客户数据馈送概述](../../features/cdf-files.md)。

## 数据收集服务器(DCS) {#dcs}

请参阅[数据收集组件](../../reference/system-components/components-data-collection.md)。

## SFTP/S3 {#sftp-s3}

[!UICONTROL SFTP/S3]发布者从[!UICONTROL Outbound Feed Converter]接收同步的ID数据。 当这些文件就绪时，[!UICONTROL SFTP/S3 publishers]将此数据发送到客户端指定的目标。 这些文件包含同步的ID数据，并将[!DNL Audience Manager]用户ID (UUID)一对多映射到：

* 设备ID/数据提供商ID (DPUUID)
* 符合条件的区段ID
* 特征ID

[!DNL Audience Manager]客户无法访问直接控制[!UICONTROL SFPT/S3 publishers]的功能。 客户在创建数据并将数据发送到目标时间接使用此服务。 [!UICONTROL SFTP/S3]系统本质上是一个按计划时间间隔运行的自动作业进程。

## IRIS {#iris}

在希腊神话中，[!UICONTROL Iris]是一个快速旅行和传递消息的人。 [!UICONTROL IRIS]系统是一个反映此人物在古代世界中特征的命名空间。 用现代术语来说，[!UICONTROL IRIS]是一种低延迟、高频Cookie同步和数据传输服务。

[!UICONTROL IRIS]使用与[!UICONTROL SFTP/S3]系统相同的数据类型。 但是，[!UICONTROL IRIS]不同，因为它实时将数据发送到目标，而不是按设定的时间间隔发送。 这是一个独立的系统，因为[!UICONTROL SFTP/S3]发布者无法将数据发送到HTTP目标，并且不是为实时数据传输而设计的。

没有允许客户直接使用[!UICONTROL IRIS]的UI控件。 客户在创建数据并将数据发送到目标时，以及对于需要快速数据传输的其他流程，会间接使用[!UICONTROL IRIS]。

[!UICONTROL IRIS]服务和功能的示例包括：

* 为Cookie和区段提供快速（在30秒内）的同步。 它可以同步[!DNL Audience Manager] Cookie、合作伙伴Cookie，或同时同步两者。
* 实时数据传输。 [!UICONTROL IRIS]负责向合作伙伴或其他目标发送实时区段鉴别事件。 此数据采用JSON格式，并通过HTTP `POST`请求发送。

* 批量服务器到服务器数据传输：如果您与[!DNL Audience Manager]交换大量数据，[!UICONTROL IRIS]是您的服务器用来传输数据的系统。

* 可靠的基础架构，可大规模工作并具有容错性。 支持[!UICONTROL IRIS]的系统包括Amazon SQS、Amazon EC2和Cassandra。

**区段映射规则**

为了优化[!UICONTROL IRIS]和区段目标之间的流量，[!UICONTROL IRIS]根据一组规则将区段发送到目标。

1. **新区段鉴别**：当设备符合新区段的资格条件时，[!UICONTROL IRIS]会将与该设备关联的所有区段发送到映射到这些区段的所有目标。

1. **新区段取消资格**：当设备不再符合区段的资格时，[!UICONTROL IRIS]会将与该设备关联的所有区段资格和取消资格发送到映射到这些区段的所有目标。

1. **目标映射更新**：当目标映射更新时，[!UICONTROL IRIS]会将与设备相关的所有区段发送到映射到这些区段的所有目标，下次Audience Manager查看该设备时。

1. **设备图更新**：当从用于评估区段的设备图中添加或删除任何设备ID时，[!UICONTROL IRIS]会将与该设备关联的所有区段发送到映射到这些区段的所有目标，下次Audience Manager查看该设备时。

>[!IMPORTANT]
>
>如果Audience Manager连续3天未检测到上述任何更新，[!UICONTROL IRIS]会在下次看到Audience Manager设备时，将与设备关联的所有区段发送到映射到这些区段的所有目标。

**示例数据文件**

以下示例包含来自[!UICONTROL IRIS]的实时区段数据。 请记住，这只是示例数据。 每个客户可能有不同的格式要求，因此内容可能有所不同。

```
{
    "ProcessTime": "Tue Jul 21 19:12:45 UTC 2015",
    "Client_ID": "111111",
    "AAM_Destination_Id": "22222",
    "User_count": "5",
    "Users": [
        {
            "AAM_UUID": "28272096202945091600036434734793744071",
            "DataPartner_UUID": "CAESEFdv5pk-Lurd8vL9Yfb3qFg",
            "Segments": [
                {
                    "Segment_ID": "1200598",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:12 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "35183292386788708387827965829455926157",
            "DataPartner_UUID": "CAESEF_d8blvZjchQ2WTzdB65yk",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:15 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "28012470144260632050402316345856327572",
            "DataPartner_UUID": "CAESEEPfHBiRjhkzvBPXQ-0MFRE|UzCESAAABOnFeHJy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:33 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "18981483751565214534184221210627150539",
            "DataPartner_UUID": "CAK4NDH0ESEE6NBEhoWDkB7s7ZY|VPYFQQAAASXPElL0",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:36 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "04761851136483019318109155624251711702",
            "DataPartner_UUID": "CAESEDkM5aSaKMV8MfaBhgSspmE|VYnTNwAAASzvVhxy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:42 UTC 2015"
                }
            ]
        }
    ]
}
```

## 配置文件缓存服务器(PCS) {#pcs}

请参阅[数据收集组件](../../reference/system-components/components-data-collection.md)。
