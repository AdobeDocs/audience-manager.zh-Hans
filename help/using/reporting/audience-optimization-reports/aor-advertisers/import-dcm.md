---
description: 设置一个Google组，将您的Google活动管理器数据文件导入Audience Manager。 本节内容概括了整合过程，并为您提供了指向Google活动管理器资源的链接，帮助您快速入门。
seo-description: 设置一个Google组，将您的Google活动管理器数据文件导入Audience Manager。 本节内容概括了整合过程，并为您提供了指向Google活动管理器资源的链接，帮助您快速入门。
seo-title: 将Google活动管理器数据文件导入Audience Manager
solution: Audience Manager
title: 将Google活动管理器数据文件导入Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 97129b435ab8e13def14bc85dcaab8254b2c4bda
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 3%

---


# 将Google活动管理器数据文件导入Audience Manager{#import-dcm-data-files-into-audience-manager}

设置[!DNL Google]组，将[!DNL Google Campaign Manager]数据文件导入Audience Manager。 本节内容概括了集成过程，并为您提供了指向[!DNL Google Campaign Manager]资源的链接，以帮助您快速入门。

## 集成摘要

[!DNL Google Campaign Manager] 是 [!DNL Google] 推出的 [!DNL DoubleClick for Advertisers] (DFA) 的替代产品。与DFA类似，[!DNL Google Campaign Manager]客户可以在[!DNL Audience Manager]中导入、视图和处理其数据。 但[!DNL Audience Manager]不能直接访问和导入您的[!UICONTROL Data Transfer]和[!UICONTROL Match Table]文件。 要导入这些文件，需要客户自行完成。

但是，[DoubleClick活动管理器帮助](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456)中详细记录了设置过程。 此外，您还可以查看下面列出的步骤以开始操作。

>[!CAUTION]
>
>[!DNL Google Campaign Manager] 数据文件包含所有广告商或客户的数据。如果需要忽略特定客户端，则必须先编辑这些文件，然后才能将它们提供给[!DNL Audience Manager]。

## 数据传输频率和可用性

[!DNL Audience Manager] 每天检查并传输一次数据。数据通常在[!DNL Audience Manager] 24小时后可用。

## 步骤

1. [创建群组](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   组控制对[!DNL Google Campaign Manager]数据的访问。 最后，您将邀请并将[!DNL Audience Manager]添加到此组。

1. [验证Google Cloud存储状态](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456)。

   Google Cloud存储包含保存[!UICONTROL Data Transfer]和[!UICONTROL Match Tables]的数据存储段。 您需要设置存储段或确保新组有权访问现有数据存储存储段。

1. [获取数据文件URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456)。

   与您的[!DNL Google Campaign Manager]客户经理或平台解决方案顾问合作。 他们将为您提供数据文件的URL。 [!DNL Google] 可能会更改将来版本中存储段和文件名的格式。同样，请与您的[!DNL Google Campaign Manager]客户经理合作，确保您使用的格式正确。

1. [设置存储段权限](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)。

   使用[!DNL Cloud Storage Manager]可以控制数据共享和存储段访问。 为您的组授予对包含[!UICONTROL Data Transfer]和[!UICONTROL Match Table]文件的存储桶的读取权限。

1. [设置数据共享](https://support.google.com/dcm/partner/answer/6206106?hl=en)。

   共享的[!DNL Google Campaign Manager]用户ID经过加密以保护隐私。 加密将向数据传输文件`PartnerId1`和`PartnerId2`的末尾添加2列。 这些列包含特定于接收这些文件的每个公司的编码用户ID。

   作为授权的第三方，[!DNL Audience Manager]可以接收[!DNL Google Campaign Manager]数据，但无法解码ID。 但是，在[!DNL Audience Manager]端，我们知道编码ID与我们的ID如何匹配。 这意味着我们可以自信、准确地匹配和同步用户。

   >[!NOTE]
   >如果您已经与另外两个第三方合作伙伴共享数据，则无法将[!DNL Google Campaign Manager]文件导入[!DNL Audience Manager]。

1. 邀请[!DNL Audience Manager]加入组。

   创建组并授予它对数据存储段的访问权限后，请邀请[!DNL Audience Manager]加入该组。 向DFA-AAM@adobe.com发送电子邮件邀请。 请务必包含步骤3中的数据文件URL。 我们的内部团队将与您合作，在接受邀请后验证访问权限。 1.在[!DNL Audience Manager]用户界面中为[!DNL Google Campaign Manager]数据设置两个数据源。

   将数据源命名为`Advertiser Analytics: DCM Platform`和`Advertiser Analytics: AAM+DCM Platform`。 在[创建数据源](../../../features/manage-datasources.md#create-data-source)工作流中，将ID类型设置为`Cookie`。 与我们的内部团队共享两个新数据源的ID。

1. 您可以轻松地从导入到[!DNL Audience Manager]的[!DNL Google Campaign Manager]文件创建特征。 请参阅[可操作的日志文件](../../../integration/media-data-integration/actionable-log-files.md)并请您的[!DNL Audience Manager]顾问或客户关怀为您启用该功能。
