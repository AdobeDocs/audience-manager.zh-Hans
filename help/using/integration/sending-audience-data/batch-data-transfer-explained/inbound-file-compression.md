---
description: 作为选项，您可以在将数据文件发送到Audience manager时压缩这些文件。
seo-description: 作为选项，您可以在将数据文件发送到Audience manager时压缩这些文件。
seo-title: 入站数据传输文件的文件压缩
solution: Audience Manager
title: 入站数据传输文件的文件压缩
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
translation-type: tm+mt
source-git-commit: 8d2d841f8e94fd67c2165eb280b85ab18001d77e

---


# 入站数据传输文件的文件压缩{#file-compression-for-inbound-data-transfer-files}

作为选项，您可以在将数据文件发送到Audience manager时压缩这些文件。

<!-- inbound-file-compression.xml -->

Audience manager支持对入站异 `.gz`步数据传输的gzip()压缩。

Audience manager还支持未压缩的文件。

>[!IMPORTANT]
>
>我们目前不支持对同一个入站数据文件进行加密和压缩。 您可以选择加密 [或压缩](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) 入站文件。
>
> 但是，请记住，PGP加密包括内置压缩。

## Amazon S3压缩

要交付到 [!DNL Amazon S3]，您必须使用或未 `.gz` 压缩文件。 压缩文件必须为1 GB或更小。 如果文件较大，请与客户服务部门讨论文件和传输过程。 虽然 [!DNL Audience Manager] 可以处理超大的文件，但可能有办法减小文件大小或提高数据传输的效率。

>[!IMPORTANT]
>
>客户 [!DNL FTP] 端必须使用二进制模式传输压缩或加密的文件。 以模式发送的压缩或加密 [!DNL ASCII] 文件将损坏数据传输文件。

## 最佳实践

* 应压缩文 [!DNL .gzip] 件(并具有文 [!DNL .gz] 件扩展名)。
* 压缩文件的最大压缩 `.gz` 文件大小为1 GB。
* 最佳拆分大小是压缩约1 GB，压缩约200-300 MB，以便最快／最早地处理文件。
* [!DNL Amazon S3] 对上传的文件施加其自己的5 GB文件大小限制。
