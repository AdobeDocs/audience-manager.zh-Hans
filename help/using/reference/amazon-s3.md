---
description: 有关Amazon简单存储服务(AmazonS3)的信息。
seo-description: 有关Amazon简单存储服务(AmazonS3)的信息。
seo-title: AmazonS3关于
solution: Audience Manager
title: AmazonS3关于
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 1%

---


# Amazon S3：关于{#amazon-s-about}

有关Amazon简单存储服务(AmazonS3)的信息。

作为最佳实践，我们建议将AmazonS3而不是FTP用作从合作伙伴获取文件并将文件交付到合作伙伴的方法。 AmazonS3提供一个简单的Web服务界面，可以随时从Web上的任何位置存储和检索任意数量的数据。

使用AmazonS3的好处包括：

* **可扩展性：** AmazonS3提供几乎无限的可扩展性。
* **可靠性和可用性：** AmazonS3提供高耐久性和高可用性存储服务。
* **速度：** AmazonS3允许快速数据传输。
* **易于使用：** AmazonS3非常易于使用和实施。您的实施可以在大约一小时内启动并运行。 实施FTP目录需要的时间要长得多。
* **多部件上传：大** 型文件可以作为多部件文件上传快速、高效。
* **安全性：** AmazonS3提供强大的安全性。

   * 所有目录只能由相应的客户或客户端访问。
   * HTTPS协议支持上载和下载。 在[!DNL Audience Manager]中传输文件时，应始终使用HTTPS。
   * AmazonS3提供静态加密，用于加密[出站数据文件](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)。 我们使用[SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html)加密方法，该方法允许由AmazonS3自动生成和管理加密密钥。

* **调试和备份支持：** AmazonS3 [!DNL Audience Manager] 允许保留文件的精确副本，从而更轻松地进行调试或重新传输。

有关AmazonS3的详细信息，请参阅以下资源：

[Amazon简单存储服务(AmazonS3)](https://aws.amazon.com/s3/) 在AmazonWeb服务网站上提供。

[从AWS文档网站开始](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) 使用Amazon简单存储服务。
