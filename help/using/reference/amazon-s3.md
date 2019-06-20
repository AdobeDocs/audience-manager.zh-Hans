---
description: 有关Amazon Simple Storage Service(Amazon S3)的信息。
seo-description: 有关Amazon Simple Storage Service(Amazon S3)的信息。
seo-title: Amazon S关于
solution: Audience Manager
title: Amazon S关于
uuid: 8197ecdf-df8 f-488d-bsel0-d8 d4205 b42 b4 b4
translation-type: tm+mt
source-git-commit: 212ec8641068a9ed4c620987bb18586ee8c7d519

---


# Amazon S3: About{#amazon-s-about}

有关Amazon Simple Storage Service(Amazon S3)的信息。

作为最佳实践，我们建议使用Amazon S而不是FTP作为一种从中获取文件并向合作伙伴交付文件的方法。Amazon S提供简单的Web服务界面，可用于随时从Web上的任意位置存储和检索任何数据。

使用Amazon S的好处包括：

* **可伸缩性：** Amazon S提供几乎无限的可伸缩性。
* **可靠性和可用性：** Amazon S提供高耐久性和高可用性存储服务。
* **速度：** Amazon S允许快速传输数据。
* **易用性：** Amazon S非常易于使用和实施。您的实施可以在大约一小时内启动和运行。实施FTP目录需要更长时间。
* **多部分上传：** 可以快速、高效地上传大型文件作为多部文件上传。
* **安全性：** Amazon S提供强大的安全性。

   * 所有目录仅可供相应的客户或客户访问。
   * HTTPS协议支持上传和下载。You should always use HTTPS when transferring files in [!DNL Audience Manager].
   * Amazon S3 provides encryption-at-rest for encrypting [outbound data files](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). We use the [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) encryption method, which allows encryption keys to be automatically generated and managed by Amazon S3.

* **调试和备份支持：** Amazon S允许 [!DNL Audience Manager] 保留文件的精确副本以使调试或重新传输更容易。

有关Amazon S的详细信息，请参阅以下资源：

[Amazon Simple Storage Service(Amazon S3)](https://aws.amazon.com/s3/) on the Amazon Web Services网站。

[AWS文档网站上的Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) 入门。
