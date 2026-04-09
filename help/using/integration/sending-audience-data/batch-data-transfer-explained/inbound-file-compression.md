---
description: 作为一个选项，您可以在将数据文件发送到Audience Manager时对其进行压缩。
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: 入站数据传输文件的文件压缩
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
TQID: https://experienceleague.adobe.com/yKIsM5aVmWW3ZEJgMqMWx8jIlGQa79hW9vkWmEXIdxI
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 0%

---

# 入站数据传输文件的文件压缩{#file-compression-for-inbound-data-transfer-files}

将数据文件发送到Audience Manager时，您可以对其进行压缩。

<!-- inbound-file-compression.xml -->

Audience Manager支持对入站异步数据传输进行gzip (`.gz`)压缩。

Audience Manager还支持未压缩文件。

>[!IMPORTANT]
>
>我们不支持对使用gzip (`.gz`)压缩的入站文件进行加密。
>
>若要加密和压缩入站文件，请使用[PGP加密](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)。 [!DNL PGP]加密包含文件压缩。

## Amazon S3压缩

要传递到[!DNL Amazon S3]，您必须使用`.gz`或未压缩文件。 压缩文件必须等于或小于1 GB。 如果文件较大，请与客户关怀部门讨论文件和传输过程。 虽然[!DNL Audience Manager]可以处理非常大的文件，但可能有一些方法可以减少文件大小或提高数据传输效率。

>[!IMPORTANT]
>
>[!DNL FTP]客户端必须使用二进制模式传输压缩或加密文件。 以[!DNL ASCII]模式发送的压缩或加密文件将损坏数据传输文件。

## 最佳实践

* 文件应是[!DNL .gzip]压缩文件（文件扩展名为[!DNL .gz]）。
* `.gz`压缩文件的最大压缩文件大小为1 GB。
* 最佳拆分大小是大约1 GB的未压缩文件或200-300 MB的压缩文件，可用于最快/最早的文件处理。
* [!DNL Amazon S3]对上载的文件施加自己的5 GB文件大小限制。
