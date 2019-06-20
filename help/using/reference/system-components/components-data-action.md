---
description: 数据操作组件包括客户数据源、数据收集服务器、SFTP/S3/HTTP发布者、IIS和配置文件缓存服务器。
seo-description: 数据操作组件包括客户数据源、数据收集服务器、SFTP/S3/HTTP发布者、IIS和配置文件缓存服务器。
seo-title: 数据操作组件
solution: Audience Manager
title: 数据操作组件
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Action Components{#data-action-components}

数据操作组件包括客户数据源、数据收集服务器、SFTP/S3/HTTP发布者、IIS和配置文件缓存服务器。

<!-- 

c_compact.xml

 -->

Action components are systems and processes that let you move data in and out of [!DNL Audience Manager] and (for the lack of a better phrase) do things with it. These [!DNL Audience Manager] components include:

## Customer Data Feeds (CDF) {#cdf}

[!UICONTROL CDF] 是每小时发送给客户的文件。其中包含用户ID以及关联的区段ID、特征ID和其他数据。For more information, see [Customer Data Feed Overview](../../features/cdf-files.md).

## Data Collection Server (DCS) {#dcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

[!UICONTROL SFTP/S3] 发布者接收来自.的同步ID数据 [!UICONTROL Outbound Feed Converter]。When these files are ready, the [!UICONTROL SFTP/S3 publishers] send this data to a destination specified by the client. These files contain synchronized ID data with a one-to-many mapping of [!DNL Audience Manager] user IDs (UUID) to:

* 设备ID/数据提供者ID(DPUUID)
* 合格的区段ID
* 特征ID

[!DNL Audience Manager] 客户无权访问直接控制的功能 [!UICONTROL SFPT/S3 publishers]。客户在创建数据并将其发送到目的地时间接使用此服务。The [!UICONTROL SFTP/S3] system is, essentially, an automated job process that runs at scheduled intervals.

## IRIS {#iris}

In Greek mythology, [!UICONTROL Iris] is a figure who travels and delivers messages rapidly. [!UICONTROL IRIS] 系统是一个反映此图特征来自古代世界的命名图。In modern terms, [!UICONTROL IRIS] is a low-latency, high-frequency cookie synchronization and data transfer service.

[!UICONTROL IRIS] 与 [!UICONTROL SFTP/S3] 系统的类型相同。However, [!UICONTROL IRIS] is different because it sends data to destinations in real time rather than at set intervals. This is a separate system because the [!UICONTROL SFTP/S3] publishers can&#39;t send data to an HTTP destination and they&#39;re not designed for real-time data transfers.

There are no UI controls that let customers work directly with [!UICONTROL IRIS]. Customers work with [!UICONTROL IRIS] indirectly when they create and send data to destinations, and for other processes that require rapid data transfers.

[!UICONTROL IRIS] 服务和功能的示例包括：

* 快速(在30秒内)同步cookie和区段。It can synchronize the [!DNL Audience Manager] cookie, partner cookies, or both.
* 实时数据传输。[!UICONTROL IRIS] 负责向合作伙伴或其他目标发送实时细分资格事件。This data is JSON-formatted and sent via an HTTP `POST` request.

* Bulk server-to-server data transfers: If you exchange large amounts of data with [!DNL Audience Manager], [!UICONTROL IRIS] is the system that your servers engage with to transfer data.

* 可靠地大规模工作并且容错的可靠基础结构。Systems that power [!UICONTROL IRIS] include Amazon SQS, Amazon EC2, and Cassandra.

**区段映射规则**

To optimize traffic between [!UICONTROL IRIS] and segment destinations, [!UICONTROL IRIS] sends segments to destinations based on a set of rules.

1. **新的细分资格**：当设备符合新的区段条件时， [!UICONTROL IRIS] 将与该设备关联的所有区段发送到映射到这些区段的所有目标。

1. **新的细分折扣**：当设备不再符合区段资格时， [!UICONTROL IRIS] 将与该设备相关的所有区段资格和资格发送到映射到这些区段的所有目标。

1. **目标映射更新**：当目标映射更新时，Audience Manager下次看到设备时 [!UICONTROL IRIS] 将与设备关联的所有区段发送到映射到这些区段的所有目标。

1. **设备图表更新**：当任何设备ID从用于评估区段的设备图表中添加或删除任何设备ID时，在Audience Manager下次看到设备时 [!UICONTROL IRIS] ，将与该设备关联的所有区段发送到映射到这些区段的所有目标。

>[!IMPORTANT]
>
>If Audience Manager doesn&#39;t detect any of the updates above for 3 consecutive days, [!UICONTROL IRIS] sends all segments associated to a device to all of the destinations mapped to these segments, the next time Audience Manager sees the device.

**示例数据文件**

The following example contains real-time segment data from [!UICONTROL IRIS]. 请记住，这只是示例数据。每个客户可能具有不同的格式要求，因此内容可能会有所不同。

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

## Profile Cache Server (PCS) {#pcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).
