---
description: 將傳遞效能報表記錄檔中的資料放入僅包含ID的表格中。 將非ID中繼資料放在個別的查閱表格中，以協助減少檔案大小和處理時間。
seo-description: Put data in Delivery Performance report log files into tables that contain IDs only. Put non-ID metadata in separate lookup tables to help reduce file size and processing times.
seo-title: Improve Log File Processing Times with Lookup Tables
solution: Audience Manager
title: 使用查找表缩短日志文件处理时间
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Reporting Reference
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 18%

---

# 使用查找表缩短日志文件处理时间{#improve-log-file-processing-times-with-lookup-tables}

將傳遞效能報表記錄檔中的資料放入僅包含ID的表格中。 將非ID中繼資料放在個別的查閱表格中，以協助減少檔案大小和處理時間。

<!-- 

c_lookup_tables.xml

 -->

## 記錄檔中繼資料會增加檔案大小和處理時間

使用的典型記錄檔 [!UICONTROL Delivery Performance] 報告通常包含數千列和數十欄。 它包含數值ID和人類可讀的資訊，例如創意人物、廣告商、插入訂單等名稱。

此非ID資訊稱為 *`metadata`* （亦即，其他資訊的相關資訊），並會寫入記錄檔的每一列。

不過， [!UICONTROL Delivery Performance] 報告主要處理記錄檔中的ID。 中繼資料很實用，但可重複使用。 它會增加檔案大小和資料擷取時間。

## 使用索引表格縮減檔案大小並縮短處理時間

為了協助改善效能，您的主要資料檔案應僅包含ID。 將中繼資料放在個別的查詢（或索引）表格中，並將這些記錄連結至具有這兩個共同關鍵變數的主檔案。

## 查閱表格如何縮減檔案大小

假設您的資料檔案與以下類似。

| 用户 ID | 广告 ID | 广告名称 | 订单 ID | 订购名称 | 广告商 ID | 廣告商名稱 |
|---|---|---|---|---|---|---|
| 1 | 111 | Shoe A | 456 | 運動鞋 | 27 | 公司A |
| 2 | 111 | Shoe A | 456 | 運動鞋 | 27 | 公司A |
| 3 | 111 | Shoe A | 456 | 運動鞋 | 27 | 公司A |
| 4 | 222 | 鞋子B | 789 | 健行 | 14 | 公司B |
| 5 | 222 | 鞋子B | 789 | 健行 | 14 | 公司B |

<br> 

以下是已刪除中繼資料的相同記錄檔。 如果檔案只包含ID，檔案會更小且更易於處理。

| 用户 ID | 广告 ID | 订单 ID | 广告商 ID |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

下方的查閱檔案包含中繼資料，並可連結回含有廣告ID的主檔案。 也請注意大小。 您不需要重複每個廣告商多次，每個廣告商只需要一個參考。

| 广告 ID | 广告名称 | 订购名称 | 廣告商名稱 |
|---|---|---|---|
| 111 | Shoe A | 運動鞋 | 公司A |
| 222 | 鞋子B | 健行 | 公司B |

## API可免除查閱表格的需要

如果您的廣告服務系統有API，則您可能需要在查詢檔案中傳送中繼資料。 我們或許可以透過API取得該資訊。 若是如此，記錄檔應僅包含ID。 我們會與您合作，判斷中繼資料是否可透過API取得。
