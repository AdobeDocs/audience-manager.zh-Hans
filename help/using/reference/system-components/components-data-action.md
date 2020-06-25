---
description: 数据操作组件包括客户数据服务、数据收集服务器、SFTP/S3/HTTP发布者、IRIS和用户档案缓存服务器。
seo-description: 数据操作组件包括客户数据服务、数据收集服务器、SFTP/S3/HTTP发布者、IRIS和用户档案缓存服务器。
seo-title: 数据操作组件
solution: Audience Manager
title: 数据操作组件
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 3%

---


# 数据操作组件{#data-action-components}

数据操作组件包括客户数据服务、数据收集服务器、SFTP/S3/HTTP发布者、IRIS和用户档案缓存服务器。

<!-- 

c_compact.xml

 -->

操作组件是允许您将数据移入和移出的系统 [!DNL Audience Manager] 和流程，并且（因为没有更好的词组）可以处理它。 这些 [!DNL Audience Manager] 组件包括：

## 客户数据信息源 (CDF) {#cdf}

[!UICONTROL CDF] 是每小时向客户发送的文件。 这些ID包含用户ID以及关联的区段ID、特征ID和其他数据。 有关详细信息，请参 [阅客户数据馈送概述](../../features/cdf-files.md)。

## 数据收集服务器(DCS) {#dcs}

请参阅[数据收集组件](../../reference/system-components/components-data-collection.md)。

## SFTP/S3 {#sftp-s3}

发 [!UICONTROL SFTP/S3] 布者从接收同步ID数 [!UICONTROL Outbound Feed Converter]据。 当这些文件准备就绪时， [!UICONTROL SFTP/S3 publishers] 将此数据发送到客户端指定的目标。 这些文件包含同步ID数据，用户ID(UUID)的一对 [!DNL Audience Manager] 多映射为：

* 设备ID/数据提供程序ID(DPUUID)
* 限定的区段ID
* 特征ID

[!DNL Audience Manager] 客户无权访问直接控制的功 [!UICONTROL SFPT/S3 publishers]能 客户在创建数据并将数据发送到目标时间接使用此服务。 该 [!UICONTROL SFTP/S3] 系统本质上是以预定时间间隔运行的自动作业进程。

## IRIS {#iris}

在希腊神话中， [!UICONTROL Iris] 一个快速旅行和传递信息的人物。 这 [!UICONTROL IRIS] 个系统是反映古代人物特点的名称。 现代语言 [!UICONTROL IRIS] 是一种低延迟、高频cookie同步和数据传输服务。

[!UICONTROL IRIS] 与系统使用相同类型的数 [!UICONTROL SFTP/S3] 据。 但是，这 [!UICONTROL IRIS] 种方法不同，因为它以实时方式而不是按设定的时间间隔将数据发送到目标。 这是一个单独的系统， [!UICONTROL SFTP/S3] 因为发布者无法将数据发送到HTTP目标，而且它们不是为实时数据传输而设计的。

没有UI控件可让客户直接使用 [!UICONTROL IRIS]。 客户创建数 [!UICONTROL IRIS] 据并将数据发送到目标时间间接地处理，以及需要快速数据传输的其他流程。

服务和 [!UICONTROL IRIS] 功能的示例包括：

* 为cookie和区段提供快速（30秒内）同步。 它可以同步 [!DNL Audience Manager] cookie和／或合作伙伴cookie。
* 实时数据传输。 [!UICONTROL IRIS] 负责将实时细分资格事件发送给合作伙伴或其他目标。 此数据为JSON格式，并通过HTTP请求发 `POST` 送。

* 批量服务器到服务器数据传输： 如果您与服务器交换大量 [!DNL Audience Manager]数 [!UICONTROL IRIS] 据，则是服务器用来传输数据的系统。

* 可靠的基础架构，可大规模运行并且容错。 强大的 [!UICONTROL IRIS] 系统包括Amazon SQS、Amazon EC2和Cassandra。

**区段映射规则**

要优化与区段目 [!UICONTROL IRIS] 标之间的流量， [!UICONTROL IRIS] 请根据一组规则将区段发送到目标。

1. **新细分资格**: 当设备符合新区段的条件时，会 [!UICONTROL IRIS] 将与该设备关联的所有区段发送到映射到这些区段的所有目标。

1. **新细分取消资格**: 当设备不再符合区段资格时，会将与该设备 [!UICONTROL IRIS] 关联的所有区段资格和取消资格发送到映射到这些区段的所有目标。

1. **目标映射更新**: 更新目标映射时，将 [!UICONTROL IRIS] 与设备关联的所有区段发送到映射到这些区段的所有目标，Audience Manager下次查看设备时。

1. **设备图形更新**: 当任何设备ID从用于评估区段的设备图中添加或删除时，会将与该设备关联的所有区段 [!UICONTROL IRIS] 发送到映射到这些区段的所有目标，Audience Manager下次查看设备时。

>[!IMPORTANT]
>
>如果Audience Manager连续3天未检测到以上任何更新，则会将与设备关联的所有区段 [!UICONTROL IRIS] 发送到映射到这些区段的所有目标，则Audience Manager下次查看设备时将发送。

**示例数据文件**

以下示例包含来自的实时区段数据 [!UICONTROL IRIS]。 请记住，这只是样本数据。 每个客户可能有不同的格式要求，因此内容可能会有所不同。

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

## 用户档案缓存服务器(PCS) {#pcs}

请参阅[数据收集组件](../../reference/system-components/components-data-collection.md)。
