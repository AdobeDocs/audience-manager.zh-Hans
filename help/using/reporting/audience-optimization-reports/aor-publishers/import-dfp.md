---
description: 在 Audience Manager 启用 Audience Optimization for Publishers 之前，您必须确保满足本文中列出的所有先决条件。检查所有先决条件后，请与客户关怀团队联系。
seo-description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-title: Import Google Ad Manager Data Files Into Audience Manager
solution: Audience Manager
title: 将Google Ad Manager数据文件导入Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization Reports
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
source-git-commit: 7147091e6c253e8124f5f21a2251c1a76ac9d808
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 14%

---

# 将Google Ad Manager（以前称为DFP）数据文件导入Audience Manager{#import-dfp-data-files-into-audience-manager}

在 Audience Manager 启用 Audience Optimization for Publishers 之前，您必须确保满足本文中列出的所有先决条件。检查所有先决条件后，请与客户关怀团队联系。

## Google Ad Manager日志摄取的先决条件 {#prereqs-dfp-ingestion}

请注意，在&#x200B;*之前必须*&#x200B;完成此部分中描述的进程，然后才能转到启用日志摄取的先决条件。

要在[!DNL Google Ad Manager]中使用[!DNL Audience Manager]&#x200B;(以前为Google DFP)日志文件，您必须在广告标记调用中首先设置我们的[Audience Manager独特用户ID (UUID)](../../../reference/ids-in-aam.md)。 这样，我们的ID将包含在[!DNL Google Ad Manager]日志中，我们可以匹配[!DNL Google Ad Manager]和[!DNL Audience Manager]之间的ID。 使用[!DNL Audience Manager] [!UICONTROL DIL]代码或[!UICONTROL Audience Management Module]在第一方Cookie中设置[!DNL Audience Manager] UUID。

以下是如何在广告标记调用中设置[!DNL Audience Manager] ID，如我们的文档中所述：

* [通过Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [通过Cookie目标](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

您需要自行设置[!DNL Audience Manager] ID，并且可以与[!DNL Audience Manager]咨询人员合作来检查是否一切正常。 在以下情况下，您已正确设置[!DNL Audience Manager] ID：

* `'aamid'`是用作标识符的键。
* 用户ID值的格式正确为[!DNL Audience Manager] UUID，如Audience Manager[中的ID索引](../../../reference/ids-in-aam.md)中所述。
* 您在[!DNL Audience Manager]日志的已定义字段中包含了[!DNL Google Ad Manager] UUID（例如CustomTargeting）。

## 启用日志摄取的先决条件 {#prereqs-ingestion-enablement}

<table id="table_C980A9F9B0FB4157B4908A64768B1571"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 步骤 </th> 
   <th colname="col2" class="entry"> 详细信息 </th> 
   <th colname="col3" class="entry"> 所有者 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>步骤 1 </p> </td> 
   <td colname="col2"> <p>在转到第2步之前，请确认已完成设置<span class="keyword"> Audience Manager</span> UUID（如上所述）所需的步骤 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span>客户关怀或咨询 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 2 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理员将创建： </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">用于将Google广告管理器摄取的服务帐户登录到<span class="keyword"> Audience Manager</span>。 </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">新凭据。 <p>注意：这可能需要一个特定于此项目的唯一电子邮件地址，在配置对Google存储段的访问权限时将使用此地址。 </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">私钥（基于JSON的凭据） </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 3 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理员向服务帐户授予API访问权限。 此步骤允许访问元数据以描述维度（行项目、订单、创意）。 <p>注意：使用您在步骤2中设置的服务帐户电子邮件访问权限授予访问API的权限。 </p> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 4 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理员已建立对Google存储段的访问权限。 请记住： </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">可以通过Google组完成此操作。 </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">将分配给服务帐户的唯一电子邮件地址关联到存储段。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 5 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理员将提供Google Ad Manager网络ID。 这允许我们在调用API时传入网络ID。 </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 6 </p> </td> 
   <td colname="col2"> <p>编译先决条件并按照详细的<a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html">此处</a>说明打开支持票证以启动日志摄取过程。 </p> </td> 
   <td colname="col3"> <p>您或代表您<span class="keyword">咨询Audience Manager</span> </p> </td> 
  </tr> 
 </tbody> 
</table>
