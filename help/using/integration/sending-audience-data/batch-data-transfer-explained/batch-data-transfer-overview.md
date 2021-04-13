---
description: 面向希望将来自其他系统（离线）的数据引入Audience Manager的技术客户和非技术客户的概述。
keywords: 入站，批，批上传，批数据
seo-description: 面向希望将来自其他系统（离线）的数据引入Audience Manager的技术客户和非技术客户的概述。 为此，请在Audience Manager中使用批上传选项。
seo-title: 将批量数据发送到 Audience Manager 概述
solution: Audience Manager
title: 将批量数据发送到 Audience Manager 概述
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: 入站数据传输
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 7%

---

# 将批处理数据发送到[!DNL Audience Manager]概述{#send-batch-data-to-audience-manager-overview}

技术客户和非技术客户希望将来自其他系统（离线）的数据导入[!DNL Audience Manager]的概述。

## 优势

您可以在[!DNL Audience Manager]中使来自其他系统的数据可用。 我们的系统可以帮助您发掘价值并利用您之前收集的用户数据。 这包括有关购买、客户调查、注册数据、[!DNL CRM]数据库等的信息。 尽管每个集成都面临着各自的挑战，但它们都有共同的步骤。 查看此材料有助于减少将线下数据联机所需的工作量。

## 第1步：同步用户ID

在同步过程中，[!DNL Audience Manager]将唯一ID分配给客户端及其用户。 这些ID分别称为[!UICONTROL Data Provider ID]([!UICONTROL DPID])和[!UICONTROL Unique User ID]([!UICONTROL UUID])。 [!DNL Audience Manager] 使用和 [!UICONTROL DPID] 标 [!UICONTROL UUID] 识用户，并确定他们 [!UICONTROL traits]是否适 [!UICONTROL segments]合、受众组和报告。此外，我们的数据收集代码([!UICONTROL DIL])会查找这些ID以从您的网站捕获访客数据。 完成此步骤后，[!DNL Audience Manager]和脱机存储库应包含每个用户记录的相应ID。

有关此步骤的重要注意事项：

* **客户端ID位** [!DNL Audience Manager] 置：需要了解您的客户端ID在您的网站上的显示位置（例如，它是否存储在Cookie、Analytics变量、页面代码等中）。
* **排除： [!DNL PII]用** 户ID不得包含个人可识别信息([!DNL PII])。
* **区分大小写和内容敏** 感性：在实时数据同步期间，从您的站点捕获的用户ID必 [!DNL Audience Manager] 须与从脱机存储库传入的ID相对应。例如，如果脱机记录包含有关[!DNL User123]的信息，但您的站点将该ID呈现为[!DNL USER123]，则[!DNL Audience Manager]会将这些信息视为不同的访客。 因此，此访客的联机信息无法与脱机数据库中的相应记录关联。 ID必须完全匹配。

请参阅[入站数据传输的ID同步](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)。

## 第2步：数据文件格式

文件名和内容遵循严格的准则。 您&#x200B;*必须*&#x200B;根据本指南中的这些规范命名和组织数据文件。 请参阅：

* [入站数据文件的 Amazon S3 名称要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [入站数据文件内容：语法、变量和示例](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 在线数据可用于离线营销工作

当您使离线数据联机时，您仍可以将此信息用于离线活动。 为此，[!DNL Audience Manager]将特征和区段信息导出到您选择的[!DNL FTP]或[!DNL Amazon S3]位置。 请联系您的合作伙伴解决方案经理，获取更多信息或帮助。

## 环境

[!DNL Audience Manager] 为文件下拉提供以下环境:

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 环境 </th> 
   <th colname="col02" class="entry"> 服务 </th> 
   <th colname="col2" class="entry"> 位置 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <b>生产</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p> <code> ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <b>测试版环境</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p><code> sandbox-ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 进一步技术阅读

系统工程师、开发人员或技术/实施团队应查看[描述的批处理数据传输过程](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)和本节中的其他文章。 这些文章提供有关传输协议、文件内容和文件名要求的详细信息。
