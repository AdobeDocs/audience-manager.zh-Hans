---
description: 要将数据从您自己的Amazon S3存储段发送到Audience Manager，您必须首先请求配置专用的Amazon S3角色。
solution: Audience Manager
title: 利用您入站文件的Amazon S3跨帐户存储段权限
feature: Inbound Data Transfers
source-git-commit: 17cee6971ca1d5cda8f272558a46220227fc51f7
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# 利用您入站文件的Amazon S3跨帐户存储段权限 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

要将数据从您自己的Amazon S3存储段发送到Audience Manager，您必须首先请求配置专用的Amazon S3角色。

为此，请执行以下步骤：

1. 请联系客户关怀团队并请求提供向Audience Manager发送文件的替代方法。
2. 为客户关怀提供 [!DNL Amazon Resource Name (ARN)] 用于发送文件的Amazon S3帐户中的角色。 _在联系客户关怀团队之前，必须创建此角色_. 配置完成后，客户关怀团队将为您提供 [!DNL Amazon Resource Name (ARN)] 对于新创建的角色。
3. 编辑现有Amazon S3角色的权限，承担由客户关怀团队提供的角色。

>[!NOTE]
>
>将集客数据传输到Audience ManagerAmazon S3存储段时，请确保使用 `bucket-owner-full-control` [访问控制列表](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) 以便Audience Manger正确处理数据。
>
>Amazon Web Services命令的示例： `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`

