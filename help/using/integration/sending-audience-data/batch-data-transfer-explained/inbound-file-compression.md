---
description: 作为一个选项，您可以在将数据文件发送到Audience Manager时压缩它们。
seo-description: 作为一个选项，您可以在将数据文件发送到Audience Manager时压缩它们。
seo-title: 入站数据传输文件的文件压缩
solution: Audience Manager
title: 入站数据传输文件的文件压缩
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: 入站数据传输
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 11%

---

# 入站数据传输文件的文件压缩{#file-compression-for-inbound-data-transfer-files}

在将数据文件发送到Audience Manager时，可以压缩它们。

<!-- inbound-file-compression.xml -->

Audience Manager支持对入站异步数据传输进行gzip(`.gz`)压缩。

Audience Manager还支持未压缩文件。

>[!IMPORTANT]
>
>我们不支持对使用gzip(`.gz`)压缩的入站文件进行加密。
>
>要加密和压缩入站文件，请使用[PGP加密](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)。 [!DNL PGP] 加密包括文件压缩。

## Amazon S3压缩

要传送到[!DNL Amazon S3]，必须使用`.gz`或未压缩文件。 压缩文件必须为1 GB或更小。 如果文件较大，请与客户关怀团队讨论文件和传输过程。 尽管[!DNL Audience Manager]可以处理非常大的文件，但可能有办法减小文件大小或提高数据传输的效率。

>[!IMPORTANT]
>
>您的[!DNL FTP]客户端必须使用二进制模式来传输压缩文件或加密文件。 以[!DNL ASCII]模式发送的压缩或加密文件将损坏数据传输文件。

## 最佳实践

* 文件应当压缩为[!DNL .gzip]（并具有[!DNL .gz]文件扩展名）。
* `.gz`压缩文件的最大压缩文件大小为1 GB。
* 最佳拆分大小（用于文件的最快/最早处理）大约为1 GB（未压缩）或200-300 MB压缩。
* [!DNL Amazon S3] 对上传的文件施加了其自身的5 GB文件大小限制。
