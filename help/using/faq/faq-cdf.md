---
description: 关于客户数据信息源 (CDF) 文件的常见问题解答。
seo-description: Frequently asked questions about Customer Data Feed (CDF) files.
seo-title: Customer Data Feed FAQ
solution: Audience Manager
title: 客户数据信息源常见问题解答
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
feature: Customer Data Feeds
exl-id: a948accc-6bec-4748-bcc8-2b77acf6b96a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 98%

---

# 客户数据信息源常见问题解答{#customer-data-feed-faq}

关于客户数据信息源 (CDF) 文件的常见问题解答。

## Amazon S3存储 {#amazon-s3-storage}

**我的 CDF 文件存储在 [!DNL Amazon] 上的什么位置？**

您的 CDF 文件存储在 [!DNL Amazon S3] 服务器的 `aam-cdf` 根目录中。此默认存储段由 [!DNL Audience Manager] 管理。另请参阅[客户数据信息源文件命名约定](../features/cdf-files.md#cdf-naming-conventions)。

<br> 

**我的存储段安全吗？**

安全。客户只能访问自己的存储空间。您将拥有存储段的只读访问权限。您没有写入权限。

<br> 

**我可以自定义存储段或将文件存储在其他目录中吗？**

不能。自定义和替代存储选项不可用。

<br> 

**我的目录在某一特定小时内缺失了一个文件。这个文件位于何处？**

缺少文件意味着 [!DNL Audience Manager] 在该小时内无法处理您的 CDF 文件。如果服务器在处理 CDF 文件时发生延迟，通常会出现这种情况。在这种情况下，您的文件并没有缺失。我们的系统有机会赶上处理进度后，在接下来的每小时，该文件都会显示在目录中。另请参阅[客户数据信息源文件处理通知](../features/cdf-files.md#cdf-file-processing-notifications)。

<br> 

**我如何知道 CDF 文件何时准备就绪？**

请参阅[客户数据信息源文件处理通知](../features/cdf-files.md#cdf-file-processing-notifications)。

<br> 

## 文件大小 {#file-sizes}

**我应会收到哪种大小的文件？平均 CDF 文件有多大？**

我们很难估计文件大小。而且，每个文件具有不同的大小。大小会随时间的变化而变化。如果您要接收 CDF 文件，最好做好管理大量数据的准备。

<br> 

**我将收到多少个文件？**

同样，我们也很难估计这一点。但是，如果您要接收 CDF 文件，最好做好管理大量数据的准备。

<br> 

## 数据完整性 {#data-integrity}

**如何检查上传到 Amazon S3 的数据的完整性？**

[!DNL Amazon] 会将大型文件拆分为较小分块，然后使用分块上传将它们上传到 [!DNL Amazon S3]。之后，它将为分块上传生成一个 `ETag` 值。首先，它会计算每个已上传分块的单个 MD5 校验和，然后将它们串联为单个字符串。接着，它会计算字符串的 MD5 校验和。最后，生成的校验和 (`ETag`) 将附加一个连字符和上传的分块总数。例如，如果文件在上传期间被拆分为 5 个分块，则其 `ETag` 可能会如下所示：`2c51427d19021e88cf3395365895b6d4-5`

<br> 

## 数据保留 {#data-retension}

**CDF 文件会存储多长时间？**

数据在八 (8) 天后会被删除。

<br> 

**我是否可以获取以前或前几天的 CDF 文件？**

您只能生成过去 8 天的 CDF 文件，而不能重新生成过去 8 天之前的 CDF 文件。

>[!MORELIKETHIS]
>
>* [客户数据信息源](../features/cdf-files.md)
