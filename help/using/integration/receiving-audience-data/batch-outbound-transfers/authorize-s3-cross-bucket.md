---
description: 对于使用Amazon简单存储服务(AmazonS3)的客户，“出站传输”过程要求我们要求您提供AmazonS3访问密钥和密钥，以便将出站数据文件传送到您的存储桶。
seo-description: 对于使用Amazon简单存储服务(AmazonS3)的客户，“出站传输”过程要求我们要求您提供AmazonS3访问密钥和密钥，以便将出站数据文件传送到您的存储桶。
seo-title: 利用出站文件的 Amazon S3 跨帐户存储段权限
solution: Audience Manager
title: 利用出站文件的 Amazon S3 跨帐户存储段权限
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 14%

---


# 利用出站文件的 Amazon S3 跨帐户存储段权限 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

对于使用[!DNL Amazon Simple Storage Service]([!DNL Amazon S3])的客户，[!UICONTROL Outbound Data Transfer]流程要求我们要求您提供[!DNL Amazon S3]访问密钥和密钥，以便将出站数据文件传送到您的存储桶。

如果您不想与我们共享您的[!DNL Amazon S3]访问密钥和密钥，请与您的[!DNL Audience Manager]顾问或客户关怀部门联系，他们将为您设置[!DNL Cross-Account Bucket Permissions]。 您只需将我们的[!DNL Amazon S3]帐户ID添加到[!DNL S3]存储段的允许列表，您就可以接收出站数据文件，如[AmazonS3文档](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)中所述。 您的[!DNL Audience Manager]顾问或客户关怀团队将为您提供我们的[!DNL Amazon S3]帐户ID。