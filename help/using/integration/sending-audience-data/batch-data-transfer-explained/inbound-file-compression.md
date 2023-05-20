---
description: 或者，您也可以在將資料檔案傳送至Audience Manager時加以壓縮。
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: 入站数据传输文件的文件压缩
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 7%

---

# 入站数据传输文件的文件压缩{#file-compression-for-inbound-data-transfer-files}

將資料檔案傳送至Audience Manager時，您可以加以壓縮。

<!-- inbound-file-compression.xml -->

Audience Manager支援gzip (`.gz`)壓縮以進行輸入、非同步資料傳輸。

Audience Manager也支援未壓縮的檔案。

>[!IMPORTANT]
>
>不支援使用gzip (`.gz`)。
>
>若要加密及壓縮傳入檔案，請使用 [PGP加密](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] 加密包含檔案壓縮。

## Amazon S3壓縮

針對傳遞至 [!DNL Amazon S3]，您必須使用 `.gz` 或未壓縮的檔案。 壓縮檔案的大小必須為1 GB。 如果檔案較大，請與客戶服務討論檔案和傳輸流程。 雖然 [!DNL Audience Manager] 可以處理非常大型的檔案，也許有方法可以縮減檔案大小或提高資料傳輸效率。

>[!IMPORTANT]
>
>您的 [!DNL FTP] 使用者端必須使用二進位模式來傳輸壓縮或加密的檔案。 壓縮或加密的檔案，傳送於 [!DNL ASCII] 模式會損毀資料傳輸檔案。

## 最佳实践

* 檔案應為 [!DNL .gzip] 已壓縮(並具有 [!DNL .gz] 副檔名)。
* 的壓縮檔案大小上限 `.gz` 壓縮檔案為1 GB。
* 最佳的分割大小，適用於最快/最早的檔案處理，大約是1 GB的未壓縮檔案或200-300 MB的壓縮檔案。
* [!DNL Amazon S3] 對上傳的檔案施加自己的5 GB檔案大小限制。
