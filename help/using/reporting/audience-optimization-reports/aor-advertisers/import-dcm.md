---
description: 设置Google组，将您的Google Campaign Manager数据文件导入Audience Manager。 此部分中的内容总结了集成过程，并提供了指向Google Campaign Manager资源的链接以帮助您入门。
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: 将Google Campaign Manager数据文件导入Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 2%

---

# 将Google Campaign Manager数据文件导入Audience Manager {#import-dcm-data-files-into-audience-manager}

设置[!DNL Google]组以将您的[!DNL Google Campaign Manager]数据文件导入Audience Manager。 此部分中的内容总结了集成过程，并为您提供了指向[!DNL Google Campaign Manager]资源的链接以帮助您入门。

## 集成摘要

[!DNL Google Campaign Manager]是[!DNL Google]的[!DNL DoubleClick for Advertisers] (DFA)的替代项。 与DFA类似，[!DNL Google Campaign Manager]客户可以在[!DNL Audience Manager]中导入、查看和处理其数据。 但[!DNL Audience Manager]无法直接访问和导入您的[!UICONTROL Data Transfer]和[!UICONTROL Match Table]文件。 要导入这些文件，需要客户自行完成。

但是，设置过程在[DoubleClick Campaign Manager帮助](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456)中有详细记录。 此外，您还可以查看下面列出的步骤以开始操作。

>[!CAUTION]
>
>[!DNL Google Campaign Manager]数据文件包含您的所有广告商或客户端的数据。 如果您需要忽略特定客户端，则必须先编辑文件，然后才能在[!DNL Audience Manager]中使用它们。

## 数据传输频率和可用性

[!DNL Audience Manager]每天检查并传输一次数据。 数据通常在24小时后的[!DNL Audience Manager]内可用。

## 步骤

1. [创建组](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456)。

   组控制对您的[!DNL Google Campaign Manager]数据的访问。 最终，您将邀请并添加[!DNL Audience Manager]到此组。

1. [验证您的Google Cloud Storage状态](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456)。

   Google Cloud Storage包含保存[!UICONTROL Data Transfer]和[!UICONTROL Match Tables]的数据桶。 您需要设置存储段，或确保您的新组有权访问现有数据存储存储段。

1. [获取数据文件URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456)。

   与您的[!DNL Google Campaign Manager]客户经理或平台解决方案顾问合作。 它们将为您提供数据文件的URL。 [!DNL Google]可能会更改未来版本中存储段和文件名的格式。 再次重申，请与您的[!DNL Google Campaign Manager]客户经理合作，确保您使用正确的格式。

1. [设置存储段权限](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)。

   [!DNL Cloud Storage Manager]允许您控制数据共享和分段访问。 向您的组授予对包含[!UICONTROL Data Transfer]和[!UICONTROL Match Table]文件的存储段的读取权限。

1. [设置数据共享](https://support.google.com/dcm/partner/answer/6206106?hl=en)。

   已加密共享[!DNL Google Campaign Manager]用户ID以保护隐私。 加密在数据传输文件的末尾添加2列，`PartnerId1`和`PartnerId2`。 这些列包含特定于接收这些文件的每个公司的编码用户ID。

   作为经授权的第三方，[!DNL Audience Manager]可以接收[!DNL Google Campaign Manager]数据，但无法对ID进行解码。 但是，在[!DNL Audience Manager]端，我们知道编码的ID与我们的ID如何匹配。 这意味着，我们可以有把握且准确地匹配和同步用户。

   >[!NOTE]
   >如果您已与2个其他第三方合作伙伴共享数据，则无法将[!DNL Google Campaign Manager]文件导入[!DNL Audience Manager]。

1. 邀请[!DNL Audience Manager]加入群。

   在您创建组并授予其访问数据桶的权限后，请邀请[!DNL Audience Manager]加入该组。 向dfaaam@adobe.com发送邀请电子邮件。 请务必包含步骤3中的数据文件URL。 接受邀请后，我们的内部团队将与您一起验证访问权限。 1.在[!DNL Google Campaign Manager]用户界面中为[!DNL Audience Manager]数据设置两个数据源。

   命名数据源`Advertiser Analytics: DCM Platform`和`Advertiser Analytics: AAM+DCM Platform`。 在[创建数据源](../../../features/manage-datasources.md#create-data-source)工作流中，将ID类型设置为`Cookie`。 与我们的内部团队共享两个新数据源的ID。

1. 您可以根据导入到[!DNL Google Campaign Manager]中的[!DNL Audience Manager]文件轻松创建特征。 查看[可操作的日志文件](../../../integration/media-data-integration/actionable-log-files.md)，并请求您的[!DNL Audience Manager]顾问或客户关怀团队为您启用该功能。
