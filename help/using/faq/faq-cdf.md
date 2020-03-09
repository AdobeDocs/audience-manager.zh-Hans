---
description: 关于客户数据馈送(CDF)文件的常见问题解答。
seo-description: 关于客户数据馈送(CDF)文件的常见问题解答。
seo-title: 客户数据馈送常见问题解答
solution: Audience Manager
title: 客户数据馈送常见问题解答
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
translation-type: tm+mt
source-git-commit: 7018705c130bf7c65f3a69da5e4bd9e0666423bc

---


# 客户数据馈送常见问题解答{#customer-data-feed-faq}

关于客户数据馈送(CDF)文件的常见问题解答。

## Amazon S3存储 {#amazon-s3-storage}

**我的CDF文件存储在何处[!DNL Amazon]?**

您的CDF文件存储在服 `aam-cdf` 务器的根目录 [!DNL Amazon S3] 中。 此默认存储段由管理 [!DNL Audience Manager]。 另请参阅 [客户数据馈送文件命名约定](../features/cdf-files.md#cdf-naming-conventions)。

<br> 

**我的存储桶安全吗？**

能。客户只能访问自己的存储空间。 您将拥有对存储存储段的只读访问权限。 您将没有写访问权限。

<br> 

**我是否可以自定义存储桶或将文件存储在另一个目录中？**

不会。自定义和备用存储选项不可用。

<br> 

**我的目录在特定小时内缺少一个文件。 在哪？**

缺少文件表 [!DNL Audience Manager] 示该小时内无法处理您的CDF文件。 这通常在我们的服务器处理CDF文件时发生。 在这种情况下，您的文件不会丢失。 在我们的系统有机会赶上后，它将显示在稍后每小时的目录中。 另请参阅客 [户数据馈送文件处理通知](../features/cdf-files.md#cdf-file-processing-notifications)。

<br> 

**我如何知道CDF文件何时准备就绪？**

请参阅 [客户数据馈送文件处理通知](../features/cdf-files.md#cdf-file-processing-notifications)。

<br> 

## 文件大小 {#file-sizes}

**我应该期望哪种文件大小？ 平均CDF文件有多大？**

很难估计文件大小。 而且，每个文件的大小可以不同。 大小因小时和日而异。 如果您要接收CDF文件，则有助于准备好管理大量数据。

<br> 

**我将收到多少个文件？**

同样，很难估计这一点。 但是，如果您要接收CDF文件，则有助于准备好管理大量数据。

<br> 

## 数据完整性 {#data-integrity}

**如何检查上传到Amazon S3的数据的完整性？**

[!DNL Amazon] 将大文件拆分为较小的部分，并使用多 [!DNL Amazon S3] 部分上传将其上传到。 然后，它为多 `ETag` 部分上传生成一个值。 它首先计算每个上传部分的单个MD5校验和，然后将它们连接到单个字符串中。 然后，计算字符串的MD5校验和。 然后，生成的校验 `ETag`和()会附加连字符以及用于上传的部件总数。 例如，在上 `ETag` 传期间被拆分为5个部分的文件的外观可能类似于： `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**您存储CDF文件多长时间？**

数据将在八(8)天后删除。

<br> 

**我是否可以逆向获得CDF文件，或者以前几天获得？**

您只能生成过去8天的CDF文件。 无法重新生成间隔早于过去8天的CDF文件。

>[!MORELIKETHIS]
>
>* [客户数据馈送](../features/cdf-files.md)

