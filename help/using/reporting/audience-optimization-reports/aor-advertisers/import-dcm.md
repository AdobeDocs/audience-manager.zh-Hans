---
description: 设置Google组，以将Google Campaign Manager数据文件导入Audience Manager。 此部分中的内容概述了集成过程，并为您提供指向Google Campaign Manager资源的链接，以帮助您快速入门。
seo-description: 设置Google组，以将Google Campaign Manager数据文件导入Audience Manager。 此部分中的内容概述了集成过程，并为您提供指向Google Campaign Manager资源的链接，以帮助您快速入门。
seo-title: 将Google Campaign Manager数据文件导入Audience Manager
solution: Audience Manager
title: 将Google Campaign Manager数据文件导入Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization 报表
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 3%

---

# 将Google Campaign Manager数据文件导入Audience Manager{#import-dcm-data-files-into-audience-manager}

设置[!DNL Google]组，将[!DNL Google Campaign Manager]数据文件导入Audience Manager。 此部分中的内容概述了集成过程，并为您提供了指向[!DNL Google Campaign Manager]资源的链接，以帮助您快速入门。

## 集成摘要

[!DNL Google Campaign Manager] 是 [!DNL Google] 推出的 [!DNL DoubleClick for Advertisers] (DFA) 的替代产品。与DFA类似， [!DNL Google Campaign Manager]客户可以在[!DNL Audience Manager]中导入、查看和处理其数据。 但[!DNL Audience Manager]无法直接访问和导入您的[!UICONTROL Data Transfer]和[!UICONTROL Match Table]文件。 要导入这些文件，需要客户自行完成。

但是，[DoubleClick Campaign Manager Help](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456)中详细记录了设置过程。 此外，您还可以查看下面列出的步骤以开始操作。

>[!CAUTION]
>
>[!DNL Google Campaign Manager] 数据文件包含所有广告商或客户的数据。如果需要忽略特定的客户端，则必须先编辑文件，然后才能将其提供给[!DNL Audience Manager]。

## 数据传输频率和可用性

[!DNL Audience Manager] 每天检查并传输一次数据。数据通常在[!DNL Audience Manager] 24小时后才可用。

## 步骤

1. [创建群组](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   组控制对[!DNL Google Campaign Manager]数据的访问。 最终，您将邀请并添加[!DNL Audience Manager]到此组。

1. [验证Google云存储状态](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456)。

   Google云存储包含包含[!UICONTROL Data Transfer]和[!UICONTROL Match Tables]的数据存储段。 您需要设置存储段，或确保新组有权访问现有数据存储存储段。

1. [获取数据文件URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456)。

   与您的[!DNL Google Campaign Manager]客户经理或平台解决方案顾问合作。 它们将为您提供指向数据文件的URL。 [!DNL Google] 可能会在未来版本中更改存储段和文件名的格式。再次重申，请与您的[!DNL Google Campaign Manager]客户经理合作，确保您使用的格式正确。

1. [设置存储段权限](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)。

   [!DNL Cloud Storage Manager]允许您控制数据共享和存储段访问。 为您的组授予对包含[!UICONTROL Data Transfer]和[!UICONTROL Match Table]文件的存储段的读取权限。

1. [设置数据共享](https://support.google.com/dcm/partner/answer/6206106?hl=en)。

   共享的[!DNL Google Campaign Manager]用户ID经过加密以保护隐私。 加密在数据传输文件的末尾添加2列： `PartnerId1`和`PartnerId2`。 这些列包含特定于接收这些文件的每个公司的编码用户ID。

   作为经授权的第三方，[!DNL Audience Manager]可以接收[!DNL Google Campaign Manager]数据，但无法对ID进行解码。 但是，在[!DNL Audience Manager]侧，我们知道编码的ID与我们的ID有何匹配。 这意味着我们可以满怀信心地准确匹配和同步用户。

   >[!NOTE]
   >如果您已经与另外2个第三方合作伙伴共享数据，则无法将[!DNL Google Campaign Manager]文件导入[!DNL Audience Manager]。

1. 邀请[!DNL Audience Manager]加入组。

   在创建群组并授予其访问数据存储段的权限后，邀请[!DNL Audience Manager]加入群组。 向DFA-AAM@adobe.com发送电子邮件邀请。 确保包含步骤3中的数据文件URL。 我们的内部团队将与您合作，以验证接受邀请后是否可访问。 1.在[!DNL Audience Manager]用户界面中为[!DNL Google Campaign Manager]数据设置两个数据源。

   将数据源命名为`Advertiser Analytics: DCM Platform`和`Advertiser Analytics: AAM+DCM Platform`。 在[创建数据源](../../../features/manage-datasources.md#create-data-source)工作流中，将ID类型设置为`Cookie`。 与我们的内部团队共享两个新数据源的ID。

1. 您可以轻松地从导入到[!DNL Audience Manager]的[!DNL Google Campaign Manager]文件创建特征。 请参阅[可操作的日志文件](../../../integration/media-data-integration/actionable-log-files.md)并请咨询[!DNL Audience Manager]顾问或客户关怀团队为您启用该功能。
