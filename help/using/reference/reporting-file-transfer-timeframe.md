---
description: Audience Manager每天都會收到大量資料。 這會影響處理您的資料和產生報告結果所需的時間。 本節中的內容說明這些時間間隔如何影響您的Audience Manager帳戶。 此外，此處說明的時間範圍與排程僅是一般准則。 這些排程不構成與資料傳送相關的服務等級協定(SLA)或承諾。 Adobe保留隨時變更時間範圍與排程的權利，恕不另行通知。
seo-description: Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.
seo-title: How Data Delivery and File Processing Times Affect Reports
solution: Audience Manager
title: 数据传输和文件处理时间对报表有何影响
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: Reference
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 4%

---

# 数据传输和文件处理时间对报表有何影响{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager每天都會收到大量資料。 這會影響處理您的資料和產生報告結果所需的時間。 本節中的內容說明這些時間間隔如何影響您的Audience Manager帳戶。 此外，此處說明的時間範圍與排程僅是一般准則。 這些排程不構成與資料傳送相關的服務等級協定(SLA)或承諾。 Adobe保留隨時變更時間範圍與排程的權利，恕不另行通知。

## 報表編號 {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

下表列出並說明一般報表和即時報表中的時間間隔。


| 数据类型 | 描述 |
|---|---|
| 即時資料 | 今天的即時數字是小時00:00到23:59:59 UTC從昨天。 |
| 一般報表資料 | 中的資料 [一般報表](../reporting/general-reports.md#general-reports-overview) 取決於其他工單處理的成功完成情況以及特定日期所接收的資料量。 大部分時間， [!UICONTROL General Report] 資料應於每日18:00 UTC更新。 |

## 傳入和傳出檔案傳輸 {#inbound-outbound-file-transfers}

[!DNL Audience Manager] 處理並傳送傳入和傳出 [!UICONTROL Server-to-Server (S2S)] 根據本節所述的排程傳輸檔案。 根據這些排程和截止時間，您可能會看到即時區段數和總區段數之間出現差異。

| 文件类型 | 描述 |
|---|---|
| 傳入檔案擷取（離線資料） | 檔案處理每天執行兩次。 這些程式會擷取資料，並準備進行傳送。 檔案傳送時間不一，因為會受到需要處理的客戶資料總量所影響。 從檔案以Audience Manager上傳到資料可用於報告和啟用之前，延遲時間最長為48小時。 |
| 傳出（匯出）檔案 | 檔案處理和傳送每天大約在14:00 UTC進行。 請記住，處理和傳送會受到這些檔案總數和大小的影響。 在某些情況下，檔案處理可能會延遲長達24小時。 發生此情況時，Audience Manager會在特定日期傳送2個檔案，而非1個。 在極少數情況下，如果Audience Manager必須完全停止處理檔案，我們會通知客戶。 基於這些條件，很難估計傳出資料的傳送時間。 若要判斷您是否收到完整的檔案集，請檢查時間戳記並尋找任何遺失的天數。 這是13位數的UNIX UTC時間戳記，記錄檔案建立時間。 另請參閱 [即時傳出資料傳輸](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| 廣告伺服器記錄檔 | 當每小時檔案準備就緒時，會近乎即時執行檔案處理，以擷取記錄檔記錄。 準備檔案以供報告的程式每天執行一次。 檔案傳送時間不一，因為會受到需要處理的客戶資料總量所影響。 從上傳檔案至Audience Manager到資料可用於報告和啟動這段時間，最多可等待48小時。 |

>[!MORELIKETHIS]
>
>* [入站客户数据摄取常见问题解答](../faq/faq-inbound-data-ingestion.md)

