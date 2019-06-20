---
description: 设置Google组，将DoubleClick Campaign Manager(DCM)数据文件引入Audience Manager。本部分中的内容总结了集成过程，并为您提供了指向DCM资源的链接，帮助您入门。
seo-description: 设置Google组，将DoubleClick Campaign Manager(DCM)数据文件引入Audience Manager。本部分中的内容总结了集成过程，并为您提供了指向DCM资源的链接，帮助您入门。
seo-title: 将DCM数据文件导入Audience Manager
solution: Audience Manager
title: 将DCM数据文件导入Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272 bebcd60
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Import DCM Data Files Into Audience Manager {#import-dcm-data-files-into-audience-manager}

设置Google组，将DoubleClick Campaign Manager(DCM)数据文件引入Audience Manager。本部分中的内容总结了集成过程，并为您提供了指向DCM资源的链接，帮助您入门。

## 集成摘要

DCM 是 [!DNL Google] 推出的 [!DNL DoubleClick for Advertisers] (DFA) 的替代产品。与 DFA 类似，DCM 客户也可以在 [!DNL Audience Manager] 中导入、查看和处理其数据。But [!DNL Audience Manager] cannot directly access and import your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files. 要导入这些文件，需要客户自行完成。

However, the set up procedure is well documented in the [DoubleClick Campaign Manager Help](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). 此外，您还可以查看下面列出的步骤以开始。

>[!CAUTION]
>
>DCM数据文件包含所有广告商或客户的数据。If you need to omit specific clients, then you must edit the files before making them available to [!DNL Audience Manager].

## 数据传输频率和可用性

[!DNL Audience Manager] 每天检查并传输数据。Data is usually available in [!DNL Audience Manager] after 24-hours.

## 步骤

1. [创建群组](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   组可控制对DCM数据的访问。Eventually, you&#39;ll invite and add [!DNL Audience Manager] to this group.

1. [验证您的Google Cloud存储状态](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456)。

   Google Cloud Storage contains the data bucket that holds your [!UICONTROL Data Transfer] and [!UICONTROL Match Tables]. 您将需要设置一个桶或确保您的新组有权访问现有数据存储桶。

1. [获取数据文件URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456)。

   与您的DCM客户经理或平台解决方案顾问合作。它们将为您提供数据文件的URL。[!DNL Google] 可能会在将来的版本中更改桶和文件名的格式。再次与您的DCM客户经理合作，确保您使用的是正确的格式。

1. [设置桶权限](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)。

   The [!DNL Cloud Storage Manager] lets you control data sharing and bucket access. Give your group read access to the bucket that contains your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files.

1. [设置数据共享](https://support.google.com/dcm/partner/answer/6206106?hl=en)。

   共享的DCM用户ID经过加密以保护隐私。Encryption adds 2 columns to the end of your Data Transfer file, `PartnerId1` and `PartnerId2`. 这些列包含特定于接收这些文件的每个公司的编码用户ID。

   As an authorized third-party, [!DNL Audience Manager] can receive DCM data, but cannot decode the IDs. However, on the [!DNL Audience Manager] side, we know how the encoded IDs match our IDs. 这意味着我们可以准确、准确地匹配和同步用户。

   >[!NOTE]
   >[!DNL Audience Manager] 如果您已经与其他个第三方合作伙伴共享数据，则无法将DCM文件导入其中。

1. Invite [!DNL Audience Manager] to join the group.

   After you create a group and give it access to a data bucket, invite [!DNL Audience Manager] to join the group. 向DFA-AAM@adobe.com发送邀请电子邮件。请务必包含步骤中的数据文件URL。我们的内部团队将与您一起验证接受邀请后的访问权限。1. Set up two data sources for DCM data in the [!DNL Audience Manager] User Interface.

   Name the data sources `Advertiser Analytics: DCM Platform` and `Advertiser Analytics: AAM+DCM Platform`. In the [Create Data Sources](../../../features/manage-datasources.md#create-data-source) workflow, set the ID type to `Cookie`. 与内部团队共享这两个新数据源的ID。

1. You can easily create traits from the DCM files you import into [!DNL Audience Manager]. See [Actionable Log Files](../../../integration/media-data-integration/actionable-log-files.md) and ask your [!DNL Audience Manager] consultant or Customer Care to enable the feature for you.
