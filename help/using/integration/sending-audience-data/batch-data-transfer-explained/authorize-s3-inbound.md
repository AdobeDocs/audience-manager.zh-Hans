---
description: 要将数据从您自己的Amazon S3存储段发送到Audience Manager，您必须首先请求配置专用的Amazon S3角色。
solution: Audience Manager
title: 利用您入站文件的Amazon S3跨帐户存储段权限
feature: Inbound Data Transfers
exl-id: 56ecea5a-0621-4720-9e4c-f9086294c31f
TQID: https://experienceleague.adobe.com/DR-nafoDKl-1VPK2xwq-iqpwkuTYk2nN3ywOycVJ3jM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 191
ht-degree: 0%

---

# 利用您入站文件的Amazon S3跨帐户存储段权限 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

要将数据从您自己的Amazon S3存储段发送到Audience Manager，您必须首先请求配置专用的Amazon S3角色。

为此，请执行以下步骤：

1. 联系客户关怀团队并请求使用其他方法将文件发送到Audience Manager。
2. 为客户关怀团队提供Amazon S3帐户中用于发送文件的角色的[!DNL Amazon Resource Name (ARN)]。 _必须先创建此角色，然后才能联系客户关怀团队_。 配置完成后，客户关怀团队将为您提供新创建角色的[!DNL Amazon Resource Name (ARN)]。
3. 编辑现有Amazon S3角色的权限，承担由客户关怀团队提供的角色。

>[!NOTE]
>
>将入站数据传输到Audience Manager Amazon S3存储段时，请确保使用`bucket-owner-full-control` [访问控制列表](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html)，以便Audience Manger正确处理数据。
>
>Amazon Web Services命令的示例： `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`
