---
description: 关于客户数据馈送(CMS)文件的常见问题。
seo-description: 关于客户数据馈送(CMS)文件的常见问题。
seo-title: 客户数据馈送常见问题解答
solution: Audience Manager
title: 客户数据馈送常见问题解答
uuid: 7183b3e2-e999-4e1 e-892f-2bab335 c13 b6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feed FAQ{#customer-data-feed-faq}

关于客户数据馈送(CMS)文件的常见问题。

## Amazon S3 Storage {#amazon-s3-storage}

**我的CMS文件存储[!DNL Amazon]在何处？**

Your CDF file is stored in the `aam-cdf` root directory on an [!DNL Amazon S3] server. This default bucket is managed by [!DNL Audience Manager]. See also [Customer Data Feed File Naming Conventions](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**我的存储盒是否安全？**

能。客户只能访问自己的存储空间。您将有权访问存储桶。您将不具有写入权限。

<br> 

**我是否可以自定义存储盒或将文件存储在另一个目录中？**

不会。不提供自定义和替代存储选项。

<br> 

**我的目录缺少一个特定小时的文件。Where is it?**

A missing file means [!DNL Audience Manager] was not able to process your CDF files for that hour. 当我们的服务器处理CMS文件时，通常会发生这种情况。在这种情况下，您的文件不会丢失。在我们的系统有机会追赶之后，它将出现在每小时的目录中。See also, [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**我如何知道CMS文件准备就绪？**

See [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## File Sizes {#file-sizes}

**我应该提供哪些文件大小？How big is an average CDF file?**

很难评估文件大小。而且，每个文件都可以是不同的大小。大小将因小时、小时而异。如果您将收到CMS文件，可以准备管理大量数据。

<br> 

**我将收到多少个文件？**

同样，很难评估这一点。但是，如果您要接收CMS文件，准备管理大量数据会有所帮助。

<br> 

## Data Integrity {#data-integrity}

**如何检查上传到Amazon S的数据完整性？**

Files exceeding 16MiB in size are split into 16MiB chunks and uploaded to [!DNL Amazon S3] using multi-part upload.

[!DNL Amazon] 为多部上传生成 `ETag` 值。它首先计算每个上传部分的单个MD校验和，然后连接到一个字符串。然后，它计算该字符串的MD校验和。The resulting checksum (the `ETag`) is then appended with a hyphen and the total number of parts used for upload. For instance, the `ETag` for a file that was split into 5 parts during upload could look something like this: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**存储CMS文件多长时间？**

数据在8(8)天后被删除。

<br> 

**我可以逆向或过去几天获得CMS文件吗？**

您只能在过去天生成CMS文件。之前天之前的时间间隔的CMS文件无法重新生成。

>[!MORE_ LIKE_ This]
>
>* [客户数据馈送](../features/cdf-files.md)

