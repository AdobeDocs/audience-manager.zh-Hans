---
description: 面向希望将其他系统（离线）中的数据导入Audience Manager的技术和非技术客户的概述。
keywords: 入站、批处理、批量上传、批量数据
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: 将批量数据发送到Audience Manager概述
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 4%

---

# 将批次数据发送到[!DNL Audience Manager]概述 {#send-batch-data-to-audience-manager-overview}

技术客户和非技术客户希望将来自其他系统（离线）的数据引入[!DNL Audience Manager]的概述。

## 优势

您可以在[!DNL Audience Manager]中使其他系统中的数据可用。 我们的系统可帮助您解锁价值并利用您之前收集的用户数据。 这包括有关购买、客户调查、注册数据、[!DNL CRM]数据库等的信息。 虽然每个集成都有其自身的挑战，但它们都具备这些通用步骤。 查看此资料以帮助减少使离线数据联机所需的工作量。

## 步骤1：同步用户ID

在同步过程中，[!DNL Audience Manager]为客户端及其用户分配唯一ID。 这些ID分别称为[!UICONTROL Data Provider ID] ([!UICONTROL DPID])和[!UICONTROL Unique User ID] ([!UICONTROL UUID])。 [!DNL Audience Manager]使用[!UICONTROL DPID]和[!UICONTROL UUID]来识别用户，并使他们符合[!UICONTROL traits]、[!UICONTROL segments]、受众组和报表的条件。 此外，我们的数据收集代码([!UICONTROL DIL])会查找这些ID以从您的网站中捕获访客数据。 完成此步骤后，[!DNL Audience Manager]和离线存储库应包含每个用户记录的相应ID。

有关此步骤的重要注意事项：

* **客户端ID位置：** [!DNL Audience Manager]需要知道您的客户端ID在您的网站上的位置（例如，它是否存储在Cookie、Analytics变量以及页面代码中，等等）。
* **排除[!DNL PII]：**&#x200B;用户ID不得包含个人身份信息([!DNL PII])。
* **区分大小写和内容：**&#x200B;在实时数据同步期间，[!DNL Audience Manager]从您的站点捕获的用户ID必须与从离线存储库传入的ID相对应。 例如，如果离线记录保存有关[!DNL User123]的信息，但您的网站将该ID呈现为[!DNL USER123]，则[!DNL Audience Manager]将它们视为不同的访客。 因此，此访客的联机信息不能与脱机数据库中的相应记录相关联。 ID必须完全匹配。

请参阅入站数据传输的[ID同步](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)。

## 步骤2：数据文件格式

文件名和内容遵循严格的准则。 您&#x200B;*必须*&#x200B;根据本指南中的这些规范命名并组织数据文件。 请参阅：

* [入站数据文件的 Amazon S3 名称要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [入站数据文件内容：语法、变量和示例](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 在线数据可用于离线营销工作

在使离线数据联机时，您仍可以将此信息用于离线营销活动。 为此，[!DNL Audience Manager]将特征和区段信息导出到您选择的[!DNL FTP]或[!DNL Amazon S3]位置。 请联系您的合作伙伴解决方案经理，以获取更多信息或帮助。

## 环境

[!DNL Audience Manager]为文件流失提供了以下环境：

| 环境 | 服务 | 位置 |
|---------|----------|---------|
| 生产 | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| Beta环境 | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients-sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style="table-layout:auto"}

## 进一步的技术阅读

系统工程师、开发人员或技术/实施团队应查看[描述的数据传输批量流程](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)以及此部分中的其他文章。 这些文章提供了有关传输协议、文件内容和文件名要求的详细信息。
