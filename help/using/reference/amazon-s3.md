---
description: 有关Amazon Simple Storage Service(Amazon S3)的信息。
seo-description: 有关Amazon Simple Storage Service(Amazon S3)的信息。
seo-title: Amazon S3关于
solution: Audience Manager
title: Amazon S3关于
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: 参考
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Amazon S3：关于{#amazon-s-about}

有关Amazon Simple Storage Service(Amazon S3)的信息。

作为最佳实践，我们建议使用Amazon S3而不是FTP作为从合作伙伴获取文件并将文件交付到合作伙伴的方法。 Amazon S3提供了一个简单的Web服务界面，可用于随时从Web上的任何位置存储和检索任意数量的数据。

使用Amazon S3的好处包括：

* **可扩展性：** Amazon S3提供几乎无限的可扩展性。
* **可靠性和可用性：** Amazon S3提供高耐用性和高可用性存储服务。
* **速度：** Amazon S3允许快速数据传输。
* **易于使用：** Amazon S3非常易于使用和实施。您的实施可以在大约一小时内启动并运行。 实施FTP目录需要花费更长的时间。
* **多部分上传：** 大文件可以作为多部分文件上传快速高效地上传。
* **安全性：** Amazon S3提供强大的安全性。

   * 所有目录只能由相应的客户或客户访问。
   * HTTPS协议支持上传和下载。 在[!DNL Audience Manager]中传输文件时，应始终使用HTTPS。
   * Amazon S3提供静态加密，以对[出站数据文件](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)进行加密。 我们使用[SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html)加密方法，该方法允许Amazon S3自动生成和管理加密密钥。

* **调试和备份支持：** Amazon S3允许 [!DNL Audience Manager] 保留文件的精确副本，以便更轻松地进行调试或重新传输。

有关Amazon S3的更多信息，请参阅以下资源：

[Amazon Web Services网站上的Amazon Simple Storage Service(Amazon S3)](https://aws.amazon.com/s3/) 。

[AWS文档网站上的Amazon](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) 简单存储服务入门。
