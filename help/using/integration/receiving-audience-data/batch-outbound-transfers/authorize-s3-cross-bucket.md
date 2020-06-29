---
description: 对于使用Amazon Simple Data Service(Amazon S3)的存储，客户的出站传输过程要求我们要求您提供Amazon S3访问密钥和密钥，以便将出站数据文件传送到您的存储桶。
seo-description: 对于使用Amazon Simple Data Service(Amazon S3)的存储，客户的出站传输过程要求我们要求您提供Amazon S3访问密钥和密钥，以便将出站数据文件传送到您的存储桶。
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

对于 [!UICONTROL Outbound Data Transfer] 使用() [!DNL Amazon Simple Storage Service] 的客户，该流程[!DNL Amazon S3]要求我们请求您的访问密钥和 [!DNL Amazon S3] 密钥，以便将出站数据文件传送到您的存储桶。

如果您不想与我们共享您 [!DNL Amazon S3] 的访问密钥和密钥，请与您的顾 [!DNL Audience Manager] 问或客户服务部门联系，他们会为您 [!DNL Cross-Account Bucket Permissions] 设置。 您只需将我们的帐 [!DNL Amazon S3] 户ID添加到要接收出站数据 [!DNL S3] 文件的存储段的允许列表，如Amazon S3文 [档中所述](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)。 您 [!DNL Audience Manager] 的顾问或客户关怀将为您提供我们的 [!DNL Amazon S3] 帐户ID。