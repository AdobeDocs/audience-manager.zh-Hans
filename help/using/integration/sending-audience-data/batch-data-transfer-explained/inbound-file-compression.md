---
description: 作为一种选项，您可以在将数据文件发送到Audience Manager时压缩它们。
seo-description: 作为一种选项，您可以在将数据文件发送到Audience Manager时压缩它们。
seo-title: 入站数据传输文件的文件压缩
solution: Audience Manager
title: 入站数据传输文件的文件压缩
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 10%

---


# 入站数据传输文件的文件压缩{#file-compression-for-inbound-data-transfer-files}

在将数据文件发送到Audience Manager时，可以压缩它们。

<!-- inbound-file-compression.xml -->

Audience Manager支持对入站异步数据传输的gzip(`.gz`)压缩。

Audience Manager还支持未压缩的文件。

>[!IMPORTANT]
>
>我们不支持对使用gzip(`.gz`)压缩的入站文件进行加密。
>
>要加密和压缩入站文件，请使用[PGP加密](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)。 [!DNL PGP] 加密包括文件压缩。

## AmazonS3压缩

要投放到[!DNL Amazon S3]，必须使用`.gz`或未压缩文件。 压缩文件必须为1 GB或更小。 如果文件较大，请与客户服务部讨论文件和传输过程。 尽管[!DNL Audience Manager]可以处理非常大的文件，但可能有方法减小文件大小或提高数据传输的效率。

>[!IMPORTANT]
>
>您的[!DNL FTP]客户端必须使用二进制模式传输压缩或加密的文件。 以[!DNL ASCII]模式发送的压缩或加密文件将损坏数据传输文件。

## 最佳实践

* 文件应压缩[!DNL .gzip]（文件扩展名为[!DNL .gz]）。
* `.gz`压缩文件的最大压缩文件大小为1 GB。
* 最佳拆分大小是压缩约1 GB未压缩或200-300 MB的大小，以便最快／最早地处理文件。
* [!DNL Amazon S3] 对上传的文件施加其自己的5 GB文件大小限制。
