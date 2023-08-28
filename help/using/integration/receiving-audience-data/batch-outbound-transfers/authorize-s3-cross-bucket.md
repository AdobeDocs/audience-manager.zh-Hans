---
description: 为使用Amazon Simple Storage Service (Amazon S3)的客户而执行的出站数据传输流程需要我们请求您的Amazon S3访问密钥和密钥，以将出站数据文件传送到您的存储段。
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: 利用出站文件的 Amazon S3 跨帐户存储段权限
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 7302fafa537ad15144a64cc96f7150c5b0233c12
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 12%

---

# 利用出站文件的 Amazon S3 跨帐户存储段权限 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

此 [!UICONTROL Outbound Data Transfer] 客户使用的流程 [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3])需要我们向您的 [!DNL Amazon S3] 访问密钥和密钥，以便将出站数据文件传送到存储段。

如果你不想分享你的 [!DNL Amazon S3] 访问密钥和密钥，请联系您的 [!DNL Audience Manager] 顾问或客户关怀团队，他们将设置 [!DNL Cross-Account Bucket Permissions] 为了你。

您只需添加我们的 [!DNL Amazon S3] 允许列表的帐户ID [!DNL S3] 您希望在其中接收出站数据文件的存储段，如 [Amazon S3文档](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). 您的 [!DNL Audience Manager] 顾问或客户关怀团队将为您提供我们的 [!DNL Amazon S3] 帐户ID。
