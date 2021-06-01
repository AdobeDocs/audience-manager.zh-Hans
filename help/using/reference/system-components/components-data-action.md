---
description: 数据操作组件包括客户数据馈送、数据收集服务器、SFTP/S3/HTTP发布者、IRIS和配置文件缓存服务器。
seo-description: 数据操作组件包括客户数据馈送、数据收集服务器、SFTP/S3/HTTP发布者、IRIS和配置文件缓存服务器。
seo-title: 数据操作组件
solution: Audience Manager
title: 数据操作组件
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: 系统组件
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 3%

---

# 数据操作组件{#data-action-components}

数据操作组件包括客户数据馈送、数据收集服务器、SFTP/S3/HTTP发布者、IRIS和配置文件缓存服务器。

<!-- 

c_compact.xml

 -->

操作组件是允许您在[!DNL Audience Manager]中移入和移出数据的系统和流程，并且（因为缺少更好的短语）可以使用它执行各种操作。 这些[!DNL Audience Manager]组件包括：

## 客户数据信息源 (CDF) {#cdf}

[!UICONTROL CDF] 是每小时发送给客户的文件。这些ID包含用户ID以及关联的区段ID、特征ID和其他数据。 有关更多信息，请参阅[客户数据馈送概述](../../features/cdf-files.md)。

## 数据收集服务器(DCS) {#dcs}

请参阅[数据收集组件](../../reference/system-components/components-data-collection.md)。

## SFTP/S3 {#sftp-s3}

[!UICONTROL SFTP/S3]发布者从[!UICONTROL Outbound Feed Converter]接收同步的ID数据。 当这些文件准备就绪时，[!UICONTROL SFTP/S3 publishers]会将此数据发送到客户端指定的目标。 这些文件包含已同步的ID数据，该数据具有[!DNL Audience Manager]用户ID(UUID)到以下对象的一对多映射：

* 设备ID/数据提供程序ID(DPUUID)
* 限定的区段ID
* 特征ID

[!DNL Audience Manager] 客户无权访问直接控制的功 [!UICONTROL SFPT/S3 publishers]能。客户在创建数据并将其发送到目标时间接使用此服务。 [!UICONTROL SFTP/S3]系统本质上是以预定时间间隔运行的自动作业进程。

## 虹膜 {#iris}

在希腊神话中，[!UICONTROL Iris]是一个迅速传递信息的人。 [!UICONTROL IRIS]系统是一个名称，它反映了古代世界中这个数字的特征。 在现代术语中，[!UICONTROL IRIS]是一种低延迟、高频率的Cookie同步和数据传输服务。

[!UICONTROL IRIS] 可与系统使用相同类型的 [!UICONTROL SFTP/S3] 数据。但是，[!UICONTROL IRIS]不同，因为它会实时向目标发送数据，而不是以设置的间隔发送。 这是一个单独的系统，因为[!UICONTROL SFTP/S3]发布者无法将数据发送到HTTP目标，而且设计不用于实时数据传输。

没有UI控件可让客户直接使用[!UICONTROL IRIS]。 客户在创建数据并将数据发送到目标以及需要快速数据传输的其他流程时，会间接使用[!UICONTROL IRIS]。

[!UICONTROL IRIS]服务和功能的示例包括：

* 为Cookie和区段提供快速（在30秒内）同步。 它可以同步[!DNL Audience Manager] Cookie和/或合作伙伴Cookie。
* 实时数据传输。 [!UICONTROL IRIS] 负责向合作伙伴或其他目标发送实时区段鉴别事件。此数据采用JSON格式，并通过HTTP `POST`请求发送。

* 批量服务器到服务器数据传输：如果您与[!DNL Audience Manager]交换大量数据，则[!UICONTROL IRIS]是您的服务器用于传输数据的系统。

* 可靠的基础架构，可大规模运行，并且具有容错能力。 为[!UICONTROL IRIS]供电的系统包括Amazon SQS、Amazon EC2和Cassandra。

**区段映射规则**

为优化[!UICONTROL IRIS]和区段目标之间的流量，[!UICONTROL IRIS]会根据一组规则将区段发送到目标。

1. **新区段资格**:当设备符合新区段的条件时，会 [!UICONTROL IRIS] 将与该设备关联的所有区段发送到映射到这些区段的所有目标。

1. **新区段取消资格**:当设备不再符合区段的条件时，会将与 [!UICONTROL IRIS] 该设备关联的所有区段资格和取消资格发送到映射到这些区段的所有目标。

1. **目标映射更新**:更新目标映射时，会将与 [!UICONTROL IRIS] 设备关联的所有区段发送到映射到这些区段的所有目标，这样Audience Manager下次会看到该设备时。

1. **设备图更新**:当从用于评估区段的设备图中添加或删除任何设备ID时， [!UICONTROL IRIS] 会将与该设备关联的所有区段发送到映射到这些区段的所有目标，则下次Audience Manager查看设备时。

>[!IMPORTANT]
>
>如果Audience Manager连续3天未检测到以上任何更新，则[!UICONTROL IRIS]会将与设备关联的所有区段发送到映射到这些区段的所有目标，则Audience Manager下次会看到该设备时。

**示例数据文件**

以下示例包含[!UICONTROL IRIS]中的实时区段数据。 请记住，这仅是示例数据。 每个客户可能有不同的格式要求，因此内容可能会有所不同。

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
