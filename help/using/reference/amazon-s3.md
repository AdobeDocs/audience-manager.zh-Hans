---
description: Amazon Simple Storage Service (Amazon S3)的相關資訊。
seo-description: Information about Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3  About
solution: Audience Manager
title: Amazon S3關於
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 1%

---

# Amazon S3：关于{#amazon-s-about}

Amazon Simple Storage Service (Amazon S3)的相關資訊。

作為最佳實務，建議您使用Amazon S3而非FTP作為從合作夥伴取得檔案並將檔案傳送給合作夥伴的方法。 Amazon S3提供簡單的網站服務介面，可用於儲存及擷取任何數量的資料，且隨時可從網路上的任何位置存取。

使用Amazon S3的好處包括：

* **擴充性：** Amazon S3提供幾乎無限的擴充能力。
* **可靠性與可用性：** Amazon S3提供高耐用性和高可用性的儲存服務。
* **速度：** Amazon S3可快速傳輸資料。
* **使用方便：** Amazon S3使用及實作都非常簡單。 您的實作可在約一小時內完成並執行。 實作FTP目錄所需的時間會長很多。
* **多部分上傳：** 上傳多部分檔案時，可以快速有效地上傳大型檔案。
* **安全性：** Amazon S3提供強大的安全性。

   * 只有適當的客戶或使用者端才能存取所有目錄。
   * HTTPS通訊協定支援上傳和下載。 在中傳輸檔案時，您應該一律使用HTTPS [!DNL Audience Manager].
   * Amazon S3提供靜態加密以進行加密 [傳出資料檔案](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). 我們使用 [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) 加密方法，可讓Amazon S3自動產生和管理加密金鑰。

* **偵錯和備份支援：** Amazon S3允許 [!DNL Audience Manager] 以保留檔案的精確副本，使偵錯或重新傳輸更容易。

如需Amazon S3的詳細資訊，請參閱下列資源：

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) ，位於Amazon Web Services網站。

[開始使用Amazon簡單儲存服務](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) AWS檔案網站上的資訊。
