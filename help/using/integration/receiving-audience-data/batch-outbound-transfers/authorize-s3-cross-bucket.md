---
description: 为使用Amazon Simple Storage Service (Amazon S3)的客户而执行的出站数据传输流程需要我们请求您的Amazon S3访问密钥和密钥，以将出站数据文件传送到您的存储段。
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: 利用您出站文件的Amazon S3跨帐户存储段权限
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 9c0254e8a29ffeb0353ed6faa898b74bcae7cef1
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# 利用您出站文件的Amazon S3跨帐户存储段权限 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

使用[!DNL Amazon Simple Storage Service] ([!DNL Amazon S3])的客户的[!UICONTROL Outbound Data Transfer]进程要求我们提供您的[!DNL Amazon S3]访问密钥和密钥，以将出站数据文件传送到您的存储段。

如果您不想与我们共享您的[!DNL Amazon S3]访问密钥和密钥，请联系您的[!DNL Audience Manager]顾问或客户关怀团队，他们将为您设置[!DNL Cross-Account Bucket Permissions]。

您只需将我们的[!DNL Amazon S3]帐户ID添加到您希望接收出站数据文件的[!DNL S3]存储段的允许列表中，如[Amazon S3文档](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)中所述。 您的[!DNL Audience Manager]顾问或客户关怀团队将为您提供我们的[!DNL Amazon S3]帐户ID。

>[!NOTE]
>
>由于Amazon S3对象大小限制，Audience Manager支持最大1 TB的拆分大小。 如果不指定任何拆分大小，将自动应用1 TB限制。

