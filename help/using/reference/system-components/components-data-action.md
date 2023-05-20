---
description: 資料動作元件包括客戶資料摘要、資料收集伺服器、SFTP/S3/HTTP發佈者、IRIS和設定檔快取伺服器。
seo-description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-title: Data Action Components
solution: Audience Manager
title: 数据操作组件
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: System Components
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 2%

---

# 数据操作组件{#data-action-components}

資料動作元件包括客戶資料摘要、資料收集伺服器、SFTP/S3/HTTP發佈者、IRIS和設定檔快取伺服器。

<!-- 

c_compact.xml

 -->

動作元件是系統和流程，可讓您在系統中行動資料 [!DNL Audience Manager] 以及（因為缺少更棒的詞句）用它來做事。 这些 [!DNL Audience Manager] 组件包括：

## 客户数据信息源 (CDF) {#cdf}

[!UICONTROL CDF] 是每小时发送给客户的文件。 其中包含用户 Id 以及关联的区段 Id、特征 Id 和其他数据。 有关更多信息，请参阅 [ 客户数据馈送概述 ](../../features/cdf-files.md) 。

## 数据收集服务器（DC） {#dcs}

请参阅[数据收集组件](../../reference/system-components/components-data-collection.md)。

## SFTP/S3 {#sftp-s3}

此 [!UICONTROL SFTP/S3] 發行者會從接收同步的ID資料 [!UICONTROL Outbound Feed Converter]. 當這些檔案準備就緒時， [!UICONTROL SFTP/S3 publishers] 將此資料傳送至使用者端指定的目的地。 這些檔案包含已同步的ID資料，且具有一對多對應 [!DNL Audience Manager] 使用者ID (UUID)至：

* 裝置ID/資料提供者ID (DPUUID)
* 合格的區段ID
* 特征 Id

[!DNL Audience Manager] 客户无权访问直接控件的 [!UICONTROL SFPT/S3 publishers] 功能。 客户在创建数据并将其发送到目标时，可以间接使用此服务。 [!UICONTROL SFTP/S3]系统实际上是以计划的时间间隔运行的自动作业进程。

## 虹膜 {#iris}

在希腊语 mythology 中， [!UICONTROL Iris] 是快速传播和交付消息的一种图表。 [!UICONTROL IRIS]系统是一 namesake，反映了 ancient 世界中此图的特征。在现代术语中， [!UICONTROL IRIS] 是一种低延迟、高频度 Cookie 同步和数据传输服务。

[!UICONTROL IRIS] 適用於與相同的資料型別 [!UICONTROL SFTP/S3] 系統。 不過， [!UICONTROL IRIS] 會有所不同，因為它會即時將資料傳送至目的地，而非以設定的間隔。 這是獨立的系統，因為 [!UICONTROL SFTP/S3] 發佈者無法將資料傳送至HTTP目的地，而且並非設計為即時資料傳輸。

沒有可讓客戶直接使用的UI控制項 [!UICONTROL IRIS]. 客戶使用 [!UICONTROL IRIS] 間接建立資料並將資料傳送至目的地時，以及需要快速資料傳輸的其他程式時。

範例： [!UICONTROL IRIS] 服務和功能包括：

* 為Cookie和區段提供快速（在30秒內）的同步處理。 它可以同步 [!DNL Audience Manager] Cookie 和/或合作伙伴 cookie。
* 实时数据传输。 [!UICONTROL IRIS] 负责将实时区段限定事件发送到合作伙伴或其他目标。 此数据为 JSON 格式，并通过 HTTP `POST` 请求发送。

* 批量服务器到服务器数据传输：如果您与 [!DNL Audience Manager] 之交换大量数据， [!UICONTROL IRIS] 则表示您的服务器与传输数据时所参与的系统。

* 可靠的基础架构，可在规模方面工作且具有容错能力。 电源 [!UICONTROL IRIS] 包括 AMAZON SQS、AMAZON EC2 和 Cassandra 的系统。

**區段對應規則**

若要最佳化兩者之間的流量 [!UICONTROL IRIS] 和區段目的地， [!UICONTROL IRIS] 會根據一組規則將區段傳送至目的地。

1. **新區段資格**：當裝置符合新區段的資格時， [!UICONTROL IRIS] 會將與該裝置相關聯的所有區段傳送至對應至這些區段的所有目的地。

1. **新區段取消資格**：當裝置不再符合區段資格時， [!UICONTROL IRIS] 會將與該裝置相關聯的所有區段資格和取消資格傳送至對應至這些區段的所有目的地。

1. **目的地對應更新**：當更新目的地對應時， [!UICONTROL IRIS] 會將與裝置相關聯的所有區段傳送至對應至這些區段的所有目的地，而Audience Manager下次再看到裝置時。

1. **裝置圖表更新**：在用來評估區段的裝置圖表中，新增或移除任何裝置ID時， [!UICONTROL IRIS] 會將與該裝置相關聯的所有區段傳送至對應至這些區段的所有目的地，而Audience Manager下次再看到該裝置時。

>[!IMPORTANT]
>
>如果 Audience Manager 未连续3天检测以上任何更新， [!UICONTROL IRIS] 则会将所有与设备关联的区段发送到映射到这些区段的所有目标，下一次 Audience Manager 看到设备。

**数据文件示例**

以下示例包含来自的 [!UICONTROL IRIS] 实时区段数据。 请记住，这只是示例数据。 每个客户可能具有不同的格式要求，因此内容可能有所不同。

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

## 設定檔快取伺服器(PCS) {#pcs}

请参阅[数据收集组件](../../reference/system-components/components-data-collection.md)。
