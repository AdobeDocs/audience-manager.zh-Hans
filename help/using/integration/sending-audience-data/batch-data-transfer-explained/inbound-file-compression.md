---
description: 作为一个选项，您可以在将数据文件发送到Audience Manager时压缩数据文件。
seo-description: 作为一个选项，您可以在将数据文件发送到Audience Manager时压缩数据文件。
seo-title: 入站数据传输文件的文件压缩
solution: Audience Manager
title: 入站数据传输文件的文件压缩
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File Compression for Inbound Data Transfer Files{#file-compression-for-inbound-data-transfer-files}

作为一个选项，您可以在将数据文件发送到Audience Manager时压缩数据文件。

<!-- inbound-file-compression.xml -->

Audience Manager supports gzip ( `.gz`) compression for inbound, asynchronous data transfers.

Audience Manager还支持未压缩的文件。

>[!IMPORTANT]
>
>我们当前不支持在同一个入站数据文件上进行加密和压缩。You can select to either [encrypt](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) or compress your inbound files.

## Amazon S压缩

For delivery to [!DNL Amazon S3], you must use `.gz` or uncompressed files. 压缩的文件必须为GB或更小。如果文件较大，请与客户关怀讨论文件和传输流程。Although [!DNL Audience Manager] can handle very large files, there may be ways to reduce the file size or make transfer of data more efficient.

>[!IMPORTANT]
>
>[!DNL FTP] 客户端必须使用二进制模式来传输压缩或加密的文件。Compressed or encrypted files sent in [!DNL ASCII] mode will corrupt the data transfer file.

## 最佳实践

* Files should be [!DNL .gzip] compressed (and have a [!DNL .gz] file extension.)
* `.gz` 压缩文件的最大压缩文件大小为GB。
* 最佳拆分大小为文件最快/最早处理，压缩约GB未压缩或压缩200-300MB。
* [!DNL Amazon S3] 对上传的文件施加5GB的文件大小限制。