---
description: 为希望将来自其他系统（离线）的数据引入Audience Manager的技术客户和非技术客户提供的概述。
keywords: inbound, batch, batch upload, batch data
seo-description: 为希望将来自其他系统（离线）的数据引入Audience Manager的技术客户和非技术客户提供的概述。 为此，请在Audience Manager中使用批上传选项。
seo-title: 向Audience Manager发送批数据概述
solution: Audience Manager
title: 向Audience Manager发送批数据概述
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 3%

---


# 向Audience Manager发送批数据概述 {#send-batch-data-to-audience-manager-overview}

针对希望将其他系统（离线）数据引入的技术客户和非技术客户的概述 [!DNL Audience Manager]。

## 优势

<!-- c_offline_to_online.xml -->

您可以在中提供来自其他系统的数据 [!DNL Audience Manager]。 我们的系统可以帮助您发掘价值并利用您之前收集的用户数据。 这包括有关购买、客户调查、注册数据、数 [!DNL CRM] 据库等的信息。 虽然每个集成都有其自身的挑战，但它们都有这些共同步骤。 查看此材料有助于减少使离线数据联机所需的工作量。

## 第1步： 同步用户ID

在同步过程中， [!DNL Audience Manager] 为客户端及其用户分配唯一的ID。 这些ID分别 [!UICONTROL Data Provider ID] 称[!UICONTROL DPID]为 [!UICONTROL Unique User ID] ()[!UICONTROL UUID]和()。 [!DNL Audience Manager] 使用 [!UICONTROL DPID] 和 [!UICONTROL UUID] 来识别用户，并确定他们的特征、区段、受众组和报告。 此外，我们的数据收集代[!UICONTROL DIL]码()会查找这些ID，以从您的网站捕获访客数据。 完成此步骤后，脱 [!DNL Audience Manager] 机存储库应包含每个用户记录的相应ID。

有关此步骤的重要注意事项：

* **客户端ID放置：** [!DNL Audience Manager] 需要了解您的客户端ID在您的网站上的显示位置(例如，它是否存储在cookie、Analytics变量、页面代码等中)。
* **排除[!DNL PII]:** 用户ID不得包含个人识别信息([!DNL PII])。
* **区分大小写和内容：** 在实时数据同步过程中，从站点捕获的用户ID必 [!DNL Audience Manager] 须与从脱机存储库传入的ID相对应。 例如，如果脱机记录包含有关的信 [!DNL User123]息，但您的站点将该ID呈现 [!DNL USER123]为，则Audience Manager将这些访客视为不同的。 因此，此访客的联机信息不能与脱机数据库中的相应记录相关联。 ID必须完全匹配。

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## 第2步： 数据文件格式

文件名和内容遵循严格的准则。 您必 *须根据* 本指南中的这些规范命名和组织数据文件。 请参阅：

* [入站数据文件的 Amazon S3 名称要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [入站数据文件内容： 语法、变量和示例](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 在线数据可用于离线营销工作

在线离线数据时，您仍可以将此信息用于线下活动。 为此，请将 [!DNL Audience Manager] 特征和区段信息导出到您 [!DNL FTP] 选择 [!DNL Amazon S3] 的某个或位置。 请联系您的合作伙伴解决方案经理以获取更多信息或协助。

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

## 进一步的技术阅读

系统工程师、开发人员或技术／实施团队应查 [看“描述的批量数据传输过程](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) ”以及本节中的其他文章。 这些文章提供有关传输协议、文件内容和文件名要求的详细信息。