---
description: 有关Amazon Simple Storage Service(Amazon S3)的信息。
seo-description: 有关Amazon Simple Storage Service(Amazon S3)的信息。
seo-title: Amazon S3关于
solution: Audience Manager
title: Amazon S3关于
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
translation-type: tm+mt
source-git-commit: 212ec8641068a9ed4c620987bb18586ee8c7d519

---


# Amazon S3:关于{#amazon-s-about}

有关Amazon Simple Storage Service(Amazon S3)的信息。

作为最佳实践，我们建议使用Amazon S3而不是FTP作为从合作伙伴获取文件并将文件交付到合作伙伴的方法。 Amazon S3提供简单的Web服务界面，可用于随时随地从Web上的任何位置存储和检索任意数量的数据。

使用Amazon S3的好处包括：

* **** 可伸缩性：Amazon S3提供几乎无限的可扩展性。
* **** 可靠性和可用性：Amazon S3提供高耐久性和高可用性存储服务。
* **** 速度：Amazon S3允许快速数据传输。
* **** 易用性：Amazon S3易于使用和实施。 您的实施可以在大约一小时内启动并运行。 实施FTP目录需要更长的时间。
* **** 多部件上传：通过多部件文件上传，可以快速、高效地上传大型文件。
* **** 安全性：Amazon S3提供强大的安全性。

   * 所有目录只能由相应的客户或客户端访问。
   * HTTPS协议支持上载和下载。 在中传输文件时，应始终使用HTTPS [!DNL Audience Manager]。
   * Amazon S3提供静态加密，用于加密出站 [数据文件](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)。 我们使用 [SSE-S3加密方法](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) ，该方法允许Amazon S3自动生成和管理加密密钥。

* **** 调试和备份支持：Amazon S3允许保 [!DNL Audience Manager] 留文件的精确副本，从而简化调试或重新传输。

有关Amazon S3的详细信息，请参阅以下资源：

[Amazon Web services网站上的Amazon Simple Storage Service(Amazon S3)](https://aws.amazon.com/s3/) 。

[从AWS文档网站上的Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) 入门。
