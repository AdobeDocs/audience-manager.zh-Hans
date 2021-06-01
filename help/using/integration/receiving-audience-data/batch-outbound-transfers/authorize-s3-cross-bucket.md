---
description: 对于使用Amazon Simple Storage Service(Amazon S3)的客户，“出站数据传输”流程要求我们请求您的Amazon S3访问密钥和密钥，以便将出站数据文件交付到存储段。
seo-description: 对于使用Amazon Simple Storage Service(Amazon S3)的客户，“出站数据传输”流程要求我们请求您的Amazon S3访问密钥和密钥，以便将出站数据文件交付到存储段。
seo-title: 利用出站文件的 Amazon S3 跨帐户存储段权限
solution: Audience Manager
title: 利用出站文件的 Amazon S3 跨帐户存储段权限
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: 出站数据传输
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 14%

---

# 利用出站文件的 Amazon S3 跨帐户存储段权限 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

对于使用[!DNL Amazon Simple Storage Service]([!DNL Amazon S3])的客户，[!UICONTROL Outbound Data Transfer]流程要求我们请求您的[!DNL Amazon S3]访问密钥和密钥，以便将出站数据文件传送到存储段。

如果您不想与我们共享[!DNL Amazon S3]访问密钥和密钥，请联系您的[!DNL Audience Manager]顾问或客户关怀团队，他们将为您设置[!DNL Cross-Account Bucket Permissions]。 您只需将我们的[!DNL Amazon S3]帐户ID添加到要在其中接收出站数据文件的[!DNL S3]存储段的允许列表中，如[Amazon S3文档](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)中所述。 您的[!DNL Audience Manager]顾问或客户关怀团队将为您提供我们的[!DNL Amazon S3]帐户ID。
