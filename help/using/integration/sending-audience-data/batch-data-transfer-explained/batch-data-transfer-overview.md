---
description: 为希望将其他系统（离线）的数据导入Audience manager的技术和非技术客户提供的概述。
keywords: 入站，批，批上传，批数据
seo-description: 为希望将其他系统（离线）的数据导入Audience manager的技术和非技术客户提供的概述。 为此，请使用Audience manager中的批量上传选项。
seo-title: 将批量数据发送到Audience Manager概述
solution: Audience Manager
title: 将批量数据发送到Audience Manager概述
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: 2e3adc8f0b2fe6efd9ca57f1d763ee4476d2edee

---


# 将批量数据发送到Audience Manager概述{#send-batch-data-to-audience-manager-overview}

为希望将其他系统（离线）的数据导入Audience manager的技术和非技术客户提供的概述。

## 优势

<!-- c_offline_to_online.xml -->

您可以在Audience manager中提供来自其他系统的数据。 我们的系统可以帮助您发掘价值并利用您之前收集的用户数据。 这包括有关购买、客户调查、注册数据、数据 [!DNL CRM] 库等的信息。 尽管每个集成都面临着各自的挑战，但它们都有着共同的步骤。 查看此材料有助于减少将离线数据联机所需的工作量。

## 第1步：同步用户ID

在同步过程中，Audience manager会为客户端及其用户分配唯一的ID。 这些ID分别 [!UICONTROL Data Provider ID] 称[!UICONTROL DPID]为( [!UICONTROL Unique User ID] )和([!UICONTROL UUID])。 Audience manager使用和 [!UICONTROL DPID] 识别用 [!UICONTROL UUID] 户，并为其确定特征、区段、受众组和报告的资格。 此外，我们的数据收集代[!UICONTROL DIL]码()会查找这些ID，以从您的网站捕获访客数据。 完成此步骤后，Audience Manager和您的脱机存储库应包含每个用户记录的相应ID。

有关此步骤的重要注意事项：

* **** 客户端ID放置：Audience manager需要了解您的客户端ID在您的网站上的显示位置（例如，它是否存储在cookie、Analytics变量、页面代码等中）。
* **[!DNL PII]排除**:用户ID不得包含个人识别信息([!DNL PII])。
* **** 大小写和内容敏感性：在实时数据同步过程中，Audience manager从您的站点捕获的用户ID必须与从脱机存储库传入的ID相对应。 例如，如果脱机记录包含有关的信 [!DNL User123]息，但您的站点将该ID呈现为 [!DNL USER123]，则Audience manager会将其视为不同的访客。 因此，此访客的在线信息无法与脱机数据库中的相应记录相关联。 ID必须完全匹配。

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

<!-- 

<p> <b>Step 2: Create a Translation File</b> </p> 
<p>A translation file classifies data according to uniform and logical hierarchy. It is a taxonomy that helps you organize information from general categories (e.g., geography) to more precise classifications (e.g., <i>geography > United States > New York</i>). Also, it labels data with to easy to understand names such as "gender=male" or "color=green" instead of with your internal SKUs, abbreviations, or other names. The file lets Audience Manager display this information in a readable, logical manner. You and your data partners must create and share the translation file with Audience Manager before any real-time or server-to-server data transfers can begin. You can update this file on a schedule relevant to your business needs. </p> 
<p>Important considerations about this step: </p> 
<ul id="ul_6A05AECB0BD649B1BF1B34058E9008E2"> 
 <li id="li_39817ED898F14156A77FCAC066FE0968"> <b>Create a comprehensive list:</b> The translation file must include all the possible values that can be passed in on a particular key. For example, if you have category key called "color" and it accepts the values "red," "green," and "blue," the translation file must contain <i>all</i> those elements. </li> 
 <li id="li_19CAD7683BCF45278E2991C1EDBC9903"> <b>Case and content sensitivity:</b> The key-values in the file must match the values actually passed in to Audience Manager from your website. </li> 
</ul> 
<p>See DATA TRANSLATION FILE. </p>

 -->

## 第2步：数据文件格式

文件名和内容遵循严格的准则。 您必 *须根据本指南* 中的这些规范命名和组织数据文件。 请参阅：

* [入站数据文件的 Amazon S3 名称要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [入站数据文件内容：语法、变量和示例](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 在线数据可用于离线营销工作

在将离线数据放到线上时，您仍可以将此信息用于线下营销活动。 为此，Audience manager将特征和细分信息导出到您 [!DNL FTP] 选择的 [!DNL Amazon S3] 位置或位置。 请联系您的合作伙伴解决方案经理以获取更多信息或帮助。

## 环境

Audience manager为文件下载提供了以下环境：

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

系统工程师、开发人员或技术／实施团队应查看“ [Batch Data Transfer Process](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) Descripted”（介绍的批量数据传输过程）和本节中的其他文章。 这些文章提供有关传输协议、文件内容和文件名要求的详细信息。