---
description: 设置Google组，将Google Campaign Manager数据文件导入Audience Manager。 此部分中的内容概述了集成过程，并为您提供指向Google Campaign Manager资源的链接，以帮助您快速入门。
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: 将Google Campaign Manager数据文件导入Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# 将Google Campaign Manager数据文件导入Audience Manager {#import-dcm-data-files-into-audience-manager}

设置 [!DNL Google] 组将 [!DNL Google Campaign Manager] 数据文件Audience Manager。 此部分中的内容将汇总集成过程，并提供指向的链接 [!DNL Google Campaign Manager] 可帮助您快速入门的资源。

## 集成摘要

[!DNL Google Campaign Manager] 是 [!DNL Google] 推出的 [!DNL DoubleClick for Advertisers] (DFA) 的替代产品。与DFA类似， [!DNL Google Campaign Manager] 客户可以在 [!DNL Audience Manager]. 但 [!DNL Audience Manager] 无法直接访问和导入 [!UICONTROL Data Transfer] 和 [!UICONTROL Match Table] 文件。 要导入这些文件，需要客户自行完成。

但是，设置过程在 [DoubleClick Campaign Manager帮助](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). 此外，您还可以查看下面列出的步骤以开始操作。

>[!CAUTION]
>
>[!DNL Google Campaign Manager] 数据文件包含所有广告商或客户的数据。 如果需要忽略特定客户端，则必须先编辑文件，然后才能将其提供给 [!DNL Audience Manager].

## 数据传输频率和可用性

[!DNL Audience Manager] 每天检查并传输一次数据。 数据通常在 [!DNL Audience Manager] 24小时后。

## 步骤

1. [创建群组](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   组控制对 [!DNL Google Campaign Manager] 数据。 最终，您将邀请并添加 [!DNL Audience Manager] 到此组。

1. [验证Google云存储状态](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google云存储包含保存您 [!UICONTROL Data Transfer] 和 [!UICONTROL Match Tables]. 您需要设置存储段，或确保新组有权访问现有数据存储存储段。

1. [获取数据文件URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   使用 [!DNL Google Campaign Manager] 客户经理或平台解决方案顾问。 它们将为您提供指向数据文件的URL。 [!DNL Google] 可能会在未来版本中更改存储段和文件名的格式。 再次重申，与 [!DNL Google Campaign Manager] 客户经理，确保您使用的格式正确。

1. [设置存储段权限](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   的 [!DNL Cloud Storage Manager] 允许您控制数据共享和存储段访问。 为您的组授予对包含 [!UICONTROL Data Transfer] 和 [!UICONTROL Match Table] 文件。

1. [设置数据共享](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   共享 [!DNL Google Campaign Manager] 用户ID经过加密以保护隐私。 加密会在数据传输文件的末尾添加2列， `PartnerId1` 和 `PartnerId2`. 这些列包含特定于接收这些文件的每个公司的编码用户ID。

   作为经授权的第三方， [!DNL Audience Manager] 可接收 [!DNL Google Campaign Manager] 数据，但无法对ID进行解码。 但是，在 [!DNL Audience Manager] 另外，我们还知道编码的ID如何与我们的ID匹配。 这意味着我们可以满怀信心地准确匹配和同步用户。

   >[!NOTE]
   >无法导入 [!DNL Google Campaign Manager] 文件到 [!DNL Audience Manager] 如果您已经与另外2个第三方合作伙伴共享数据，则。

1. 邀请 [!DNL Audience Manager] 加入小组。

   在创建群组并授予其访问数据存储段的权限后，请邀请 [!DNL Audience Manager] 加入小组。 向dfaaam@adobe.com发送电子邮件邀请。 确保包含步骤3中的数据文件URL。 我们的内部团队将与您合作，以验证接受邀请后是否可访问。 1.为 [!DNL Google Campaign Manager] 数据 [!DNL Audience Manager] 用户界面。

   命名数据源 `Advertiser Analytics: DCM Platform` 和 `Advertiser Analytics: AAM+DCM Platform`. 在 [创建数据源](../../../features/manage-datasources.md#create-data-source) 工作流中，将ID类型设置为 `Cookie`. 与我们的内部团队共享两个新数据源的ID。

1. 您可以轻松地从 [!DNL Google Campaign Manager] 要导入的文件 [!DNL Audience Manager]. 请参阅 [可操作的日志文件](../../../integration/media-data-integration/actionable-log-files.md) 问你 [!DNL Audience Manager] 顾问或客户关怀团队为您启用该功能。
