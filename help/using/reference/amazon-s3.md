---
description: 有关Amazon简单存储服务(Amazon S3)的信息。
seo-description: Information about Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3  About
solution: Audience Manager
title: Amazon S3关于
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Amazon S3：关于{#amazon-s-about}

有关Amazon简单存储服务(Amazon S3)的信息。

作为最佳实践，我们建议使用Amazon S3而不是FTP作为从合作伙伴获取文件并将文件交付给合作伙伴的方法。 Amazon S3提供了一个简单的Web服务界面，可用于随时随地在Web上存储和检索任意数量的数据。

使用Amazon S3的好处包括：

* **可扩展性：** Amazon S3提供了几乎无限的可扩展性。
* **可靠性和可用性：** Amazon S3提供高耐用性和高可用性存储服务。
* **速度：** Amazon S3允许快速数据传输。
* **易用性：** Amazon S3非常易于使用和实施。 您的实施可以在大约一小时内启动并运行。 实施FTP目录所需的时间要长得多。
* **多部分上载：**&#x200B;可以快速高效地上载大型文件作为多部分文件上载。
* **安全性：** Amazon S3提供了强大的安全性。

   * 只有相应的客户或客户才能访问所有目录。
   * HTTPS协议支持上传和下载。 在[!DNL Audience Manager]中传输文件时应始终使用HTTPS。
   * Amazon S3为加密[出站数据文件](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)提供了静态加密。 我们使用[SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html)加密方法，该方法允许由Amazon S3自动生成和管理加密密钥。

* **调试和备份支持：** Amazon S3允许[!DNL Audience Manager]保留文件的精确副本，以便更轻松地调试或重新传输。

有关Amazon S3的更多信息，请参阅以下资源：

Amazon Web Services网站上的[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/)。

在Amazon文档网站上[开始使用AWS Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html)。
