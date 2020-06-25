---
description: 设置一个Google组，将您的DoubleClick活动管理器(DCM)数据文件导入Audience Manager。 本节内容概括了集成过程，并为您提供了指向DCM资源的链接，以帮助您快速入门。
seo-description: 设置一个Google组，将您的DoubleClick活动管理器(DCM)数据文件导入Audience Manager。 本节内容概括了集成过程，并为您提供了指向DCM资源的链接，以帮助您快速入门。
seo-title: 将 DCM 数据文件导入 Audience Manager
solution: Audience Manager
title: 将 DCM 数据文件导入 Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 8%

---


# 将 DCM 数据文件导入 Audience Manager {#import-dcm-data-files-into-audience-manager}

设置一个Google组，将您的DoubleClick活动管理器(DCM)数据文件导入Audience Manager。 本节内容概括了集成过程，并为您提供了指向DCM资源的链接，以帮助您快速入门。

## 集成摘要

DCM 是 [!DNL Google] 推出的 [!DNL DoubleClick for Advertisers] (DFA) 的替代产品。与 DFA 类似，DCM 客户也可以在 [!DNL Audience Manager] 中导入、查看和处理其数据。但无 [!DNL Audience Manager] 法直接访问和导入您 [!UICONTROL Data Transfer] 的和 [!UICONTROL Match Table] 文件。 要导入这些文件，需要客户自行完成。

但是，DoubleClick活动管理器帮助中详细记录了 [设置过程](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456)。 此外，您还可以查看下面列出的步骤以开始操作。

>[!CAUTION]
>
>DCM数据文件包含所有广告商或客户的数据。 如果需要忽略特定客户端，则必须先编辑这些文件，然后才能将它们提供给 [!DNL Audience Manager]。

## 数据传输频率和可用性

[!DNL Audience Manager] 每天检查并传输一次数据。 数据通常在24 [!DNL Audience Manager] 小时后可用。

## 步骤

1. [创建群组](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   组控制对DCM数据的访问。 最终，您将邀请并添加 [!DNL Audience Manager] 到此组。

1. [验证Google Cloud存储状态](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456)。

   Google Cloud存储包含保存您和的数 [!UICONTROL Data Transfer] 据桶 [!UICONTROL Match Tables]。 您需要设置存储段或确保新组有权访问现有数据存储存储段。

1. [获取数据文件URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456)。

   与DCM客户经理或平台解决方案顾问合作。 他们将为您提供数据文件的URL。 [!DNL Google] 可能会更改将来版本中存储段和文件名的格式。 同样，请与DCM客户经理合作，确保使用正确的格式。

1. [设置存储段权限](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)。

   您可 [!DNL Cloud Storage Manager] 以控制数据共享和存储段访问。 为您的组授予对包含您和文件的存储段的读 [!UICONTROL Data Transfer] 取 [!UICONTROL Match Table] 权限。

1. [设置数据共享](https://support.google.com/dcm/partner/answer/6206106?hl=en)。

   共享DCM用户ID经过加密以保护隐私。 Encryption会向数据传输文件的末尾添加2列， `PartnerId1` 以及 `PartnerId2`。 这些列包含特定于接收这些文件的每个公司的编码用户ID。

   作为授权的第三方， [!DNL Audience Manager] 可以接收DCM数据，但无法解码ID。 但是，从侧面 [!DNL Audience Manager] ，我们了解编码ID与我们的ID的匹配情况。 这意味着我们可以自信、准确地匹配和同步用户。

   >[!NOTE]
   >如果已与另外两个 [!DNL Audience Manager] 第三方合作伙伴共享数据，则无法将DCM文件导入。

1. 邀 [!DNL Audience Manager] 请加入组。

   在创建组并授予其对数据存储段的访问权限后，请 [!DNL Audience Manager] 邀请加入该组。 向DFA-AAM@adobe.com发送电子邮件邀请。 请务必包含步骤3中的数据文件URL。 我们的内部团队将与您合作，在接受邀请后验证访问权限。 1.在用户界面中为DCM数据设置两 [!DNL Audience Manager] 个数据源。

   命名数据源 `Advertiser Analytics: DCM Platform` 和 `Advertiser Analytics: AAM+DCM Platform`。 在“创 [建数据源](../../../features/manage-datasources.md#create-data-source) ”工作流中，将ID类型设置为 `Cookie`。 与我们的内部团队共享两个新数据源的ID。

1. 您可以轻松地从导入到的DCM文件创建特征 [!DNL Audience Manager]。 请参 [阅可操作的日志](../../../integration/media-data-integration/actionable-log-files.md) 文件，并请您 [!DNL Audience Manager] 的顾问或客户服务部门为您启用该功能。
