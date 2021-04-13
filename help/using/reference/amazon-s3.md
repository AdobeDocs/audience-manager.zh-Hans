---
description: 有关Amazon Simple 存储 Service(Amazon S3)的信息。
seo-description: 有关Amazon Simple 存储 Service(Amazon S3)的信息。
seo-title: Amazon S3关于
solution: Audience Manager
title: Amazon S3关于
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: 参考
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Amazon S3：关于{#amazon-s-about}

有关Amazon Simple 存储 Service(Amazon S3)的信息。

作为最佳实践，我们建议使用Amazon S3而不是FTP作为从合作伙伴处获取文件并将文件传送到合作伙伴的方法。 Amazon S3提供一个简单的Web服务界面，可用于随时从Web上的任何位置存储和检索任意数量的数据。

使用Amazon S3的好处包括：

* **可伸缩性：** Amazon S3提供几乎无限的可伸缩性。
* **可靠性和可用性：** Amazon S3提供高耐用性和高可用性存储服务。
* **速度：** Amazon S3允许快速数据传输。
* **易用性：** Amazon S3非常易于使用和实施。您的实施可以在大约一小时内启动并运行。 实施FTP目录需要更长的时间。
* **多部件上传：大** 文件可以作为多部件文件上传快速、高效地上传。
* **安全性：** Amazon S3提供强大的安全性。

   * 所有目录只能由相应的客户或客户访问。
   * HTTPS协议支持上载和下载。 在[!DNL Audience Manager]中传输文件时，应始终使用HTTPS。
   * Amazon S3为加密[出站数据文件](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)提供静态加密。 我们使用[SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html)加密方法，该方法允许由Amazon S3自动生成和管理加密密钥。

* **调试和备份支持：** Amazon S3允 [!DNL Audience Manager] 许保留文件的精确副本，从而使调试或重新传输更容易。

有关Amazon S3的详细信息，请参阅以下资源：

[Amazon简单存储服务(Amazon S3)](https://aws.amazon.com/s3/) 访问Amazon Web Services网站。

[从AWS文档网站上的Amazon ](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) Simple 存储 Service入门。
