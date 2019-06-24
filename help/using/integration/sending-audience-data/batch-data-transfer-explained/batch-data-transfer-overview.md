---
description: 概述希望将数据从其他系统(脱机)引入Audience Manager的技术和非技术客户的概述。
keywords: inacted
seo-description: 概述希望将数据从其他系统(脱机)引入Audience Manager的技术和非技术客户的概述。
seo-title: 将批处理数据发送到Audience Manager概述
solution: Audience Manager
title: 将批处理数据发送到Audience Manager概述
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# Send Batch Data to Audience Manager Overview{#send-batch-data-to-audience-manager-overview}

概述希望将数据从其他系统(脱机)引入Audience Manager的技术和非技术客户的概述。

## 优势

<!-- c_offline_to_online.xml -->

您可以从Audience Manager中提供其他系统的数据。我们的系统可以帮助您释放价值并利用之前收集的用户数据。This includes information about purchases, customer surveys, registration data, [!DNL CRM] databases, etc. 虽然每个集成都有自己的挑战，但它们都共享了这些常见步骤。查看此材料可帮助减少在线离线数据所需的工作。

## 步骤1：同步用户ID

在同步过程中，Audience Manager会向客户端及其用户分配唯一ID。These IDs are known as the [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) and [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectively. Audience Manager uses the [!UICONTROL DPID] and [!UICONTROL UUID] to identify users and qualify them for traits, segments, audience groups, and for reporting. Additionally, our data collection code ([!UICONTROL DIL]) looks for these IDs to capture visitor data from your website. 完成此步骤后，Audience Manager和您的脱机存储库应包含每个用户记录对应的ID。

关于此步骤的重要注意事项：

* **客户端ID位置：** Audience Manager需要了解您的客户端ID在您的网站上显示的位置(例如，它存储在cookie中、Analytics变量、页面代码中等)。
* **排除[!DNL PII]：** 用户ID不得包含个人识别信息([!DNL PII])。
* **案例和内容敏感性：** 在实时数据同步过程中，Audience Manager从您的站点捕获的用户ID必须与从脱机存储库中传入的ID相对应。For example, if offline records hold information about [!DNL User123], but your site renders that ID as [!DNL USER123], Audience Manager sees these as different visitors. 因此，此访客的在线信息无法与脱机数据库中的相应记录关联。ID必须完全匹配。

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

## 步骤2：数据文件格式

文件名和内容遵循严格指导方针。You *must* name and organize data files according to these specifications in this guide. 请参阅：

* [入站数据文件的 Amazon S3 名称要求](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [入站数据文件内容：语法、变量和示例](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## 线上数据可用于离线营销工作

在线离线数据时，您仍可将此信息用于离线营销活动。To do this, Audience Manager exports trait and segment information to an [!DNL FTP] or [!DNL Amazon S3] location of your choice. 有关更多信息或协助，请与您的合作伙伴解决方案经理联系。

## 环境

Audience Manager为文件放弃提供以下环境：

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
   <td colname="col2"> <p> <code> demdex-s2 s-clients-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 更多技术阅读

Systems engineers, developers, or technical/implementation teams should review [Batch Data Transfer Process Described](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process) and the other articles in this section. 这些文章提供了有关传输协议、文件内容和文件名要求的详细信息。