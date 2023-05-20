---
description: Audience Manager會根據這些規格，將批次資料傳送給協力廠商內容提供者。
seo-description: Adobe Audience Manager (AAM) sends batch data to third-party content providers according to these specifications.
seo-title: Batch Outbound Data Transfers in Adobe Audience Manager (AAM)
title: 批量出站数据传输
feature: Outbound Data Transfers
exl-id: 1fdcc971-3a71-4033-8501-ef3d1f1f0f47
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 19%

---

# 批量出站数据传输

Audience Manager會根據這些規格，將批次資料傳送給協力廠商內容提供者。

* [出站数据文件名：语法和示例](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)

   說明用來命名傳出資料檔案的必要欄位、語法和慣例。

* [設定批次資料傳輸整合](batch-server-configuration.md)

   說明設定批次資料傳輸整合的方法。

* [用于日志文件传输的传输控制文件](/help/using/integration/receiving-audience-data/batch-outbound-transfers/transfer-control-files.md)

   傳輸控制(.info)檔案會提供有關檔案傳輸的中繼資料資訊，以便合作夥伴可以確認Audience Manager已正確處理檔案傳輸。

* [出站模板宏](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)

   列出可用來建立輸出範本的巨集。 這些包括檔案名稱巨集、標頭巨集和內容巨集。

* [出站宏示例](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

   如何使用部分通用巨集建立輸出檔案範本的範例。

* [利用出站文件的 Amazon S3 跨帐户存储段权限](/help/using/integration/receiving-audience-data/batch-outbound-transfers/authorize-s3-cross-bucket.md)

   使用Amazon Simple Storage Service (Amazon S3)之客戶的傳出資料傳輸程式需要我們要求您的Amazon S3存取金鑰和秘密金鑰，以將傳出資料檔案傳送至您的貯體。
