---
description: 数据操作组件包括客户数据服务、数据收集服务器、SFTP/S3/HTTP发布者、IRIS和配置文件缓存服务器。
seo-description: 数据操作组件包括客户数据服务、数据收集服务器、SFTP/S3/HTTP发布者、IRIS和配置文件缓存服务器。
seo-title: 数据操作组件
solution: Audience Manager
title: 数据操作组件
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 数据操作组件{#data-action-components}

数据操作组件包括客户数据服务、数据收集服务器、SFTP/S3/HTTP发布者、IRIS和配置文件缓存服务器。

<!-- 

c_compact.xml

 -->

操作组件是允许您将数据移入和移出的系统和流程， [!DNL Audience Manager] 并且（因为没有更好的短语）可以对数据执行操作。 这些 [!DNL Audience Manager] 组件包括：

## 客户数据馈送(CDF) {#cdf}

[!UICONTROL CDF] 是每小时向客户发送的文件。 这些ID包含用户ID以及关联的区段ID、特征ID和其他数据。 有关详细信息，请参 [阅客户数据馈送概述](../../features/cdf-files.md)。

## 数据收集服务器(DCS) {#dcs}

请参阅 [数据收集组件](../../reference/system-components/components-data-collection.md)。

## SFTP/S3 {#sftp-s3}

发布 [!UICONTROL SFTP/S3] 者会从中接收同步的ID数据 [!UICONTROL Outbound Feed Converter]。 当这些文件准备就绪时， [!UICONTROL SFTP/S3 publishers] 将此数据发送到客户端指定的目标。 这些文件包含同步ID数据，用户ID(UUID)的一对多映 [!DNL Audience Manager] 射将映射到：

* 设备ID/数据提供者ID(DPUUID)
* 限定的区段ID
* 特征ID

[!DNL Audience Manager] 客户无权访问直接控制的功能 [!UICONTROL SFPT/S3 publishers]。 客户在创建数据并将数据发送到目标时间接使用此服务。 本 [!UICONTROL SFTP/S3] 质上，该系统是以预定时间间隔运行的自动作业进程。

## IRIS {#iris}

在希腊神话中， [!UICONTROL Iris] 一个快速传播和传递信息的人物。 这 [!UICONTROL IRIS] 个系统是反映这个古代人物特征的名称。 在现代语言中， [!UICONTROL IRIS] 这是一种低延迟、高频Cookie同步和数据传输服务。

[!UICONTROL IRIS] 与系统使用相同类型的数 [!UICONTROL SFTP/S3] 据。 但是，这 [!UICONTROL IRIS] 是不同的，因为它以实时而非设置的时间间隔将数据发送到目标。 这是一个单独的系统，因 [!UICONTROL SFTP/S3] 为发布者无法将数据发送到HTTP目标，而且它们并非设计用于实时数据传输。

没有UI控件可让客户直接使用 [!UICONTROL IRIS]。 客户在创建数 [!UICONTROL IRIS] 据并将数据发送到目标时间接合作，以及处理需要快速数据传输的其他流程。

服务和 [!UICONTROL IRIS] 功能的示例包括：

* 为cookie和区段提供快速（30秒内）同步。 它可以同步 [!DNL Audience Manager] cookie和／或合作伙伴cookie。
* 实时数据传输。 [!UICONTROL IRIS] 负责向合作伙伴或其他目标发送实时细分资格事件。 此数据采用JSON格式，并通过HTTP请求发 `POST` 送。

* 批量服务器到服务器数据传输：如果您与服务器交换大量数 [!DNL Audience Manager]据， [!UICONTROL IRIS] 则服务器使用的系统是用来传输数据的。

* 可靠的基础架构，可大规模运行并且容错。 强大的系 [!UICONTROL IRIS] 统包括Amazon SQS、Amazon EC2和Cassandra。

**区段映射规则**

要优化与区段目 [!UICONTROL IRIS] 标之间的流量，请 [!UICONTROL IRIS] 根据一组规则将区段发送到目标。

1. **新细分资格**:当设备符合新区段的条件时，将与该设 [!UICONTROL IRIS] 备关联的所有区段发送到映射到这些区段的所有目标。

1. **新细分取消资格**:当设备不再符合区段资格时，会将与该设备关联的所有区段资格和 [!UICONTROL IRIS] 取消资格发送到映射到这些区段的所有目标。

1. **目标映射更新**:更新目标映射时，将与设备关联的 [!UICONTROL IRIS] 所有区段发送到映射到这些区段的所有目标，此时Audience manager将在下次查看设备时发送。

1. **设备图形更新**:当任何设备ID从用于评估区段的设备图中添加或删除时， [!UICONTROL IRIS] Audience Manager会将与该设备关联的所有区段发送到映射到这些区段的所有目标，此时Audience Manager会下次看到设备。

>[!IMPORTANT]
>
>如果Audience manager连续3天未检测到以上任何更新，则会将与设备关联的所有区段发送到映射到这些区段的所有目标，此时Audience manager将下次看到设备。 [!UICONTROL IRIS]

**范例数据文件**

以下示例包含来自的实时区段数据 [!UICONTROL IRIS]。 请记住，这只是样本数据。 每位客户可能具有不同的格式要求，因此内容可能会有所不同。

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

请参阅 [数据收集组件](../../reference/system-components/components-data-collection.md)。
