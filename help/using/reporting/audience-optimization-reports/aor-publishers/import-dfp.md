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
source-wordcount: '508'
ht-degree: 13%

---

# 将Google Ad Manager（以前称为DFP）数据文件导入Audience Manager{#import-dfp-data-files-into-audience-manager}

在 Audience Manager 启用 Audience Optimization for Publishers 之前，您必须确保满足本文中列出的所有先决条件。检查所有先决条件后，请与客户关怀团队联系。

## Google Ad Manager日志摄取的先决条件 {#prereqs-dfp-ingestion}

请注意，必须完成本节中描述的流程 *早于* 接下来，您将转到启用日志摄取的先决条件。

要使用 [!DNL Google Ad Manager] (以前称为Google DFP)日志文件 [!DNL Audience Manager]，您必须首先设置 [Audience Manager独特用户ID (UUID)](../../../reference/ids-in-aam.md) 在广告标记调用中。 这样，我们的ID就包含在 [!DNL Google Ad Manager] 日志，我们可以匹配ID [!DNL Google Ad Manager] 和 [!DNL Audience Manager]. 使用 [!DNL Audience Manager] [!UICONTROL DIL] 代码或 [!UICONTROL Audience Management Module] 以设置 [!DNL Audience Manager] 第一方Cookie中的UUID。

以下是如何设置 [!DNL Audience Manager] 广告标记调用中的ID，如我们的文档中所述：

* [通过Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [通过Cookie目标](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

您需要设置 [!DNL Audience Manager] 标识您自己，并且可以与 [!DNL Audience Manager] 咨询以检查是否一切正常。 您已设置 [!DNL Audience Manager] ID正确，如果：

* `'aamid'` 是用作标识符的键。
* 用户ID值的格式正确： [!DNL Audience Manager] UUID，如我们的 [Audience Manager中的ID索引](../../../reference/ids-in-aam.md).
* 您已包含 [!DNL Audience Manager] UUID位于 [!DNL Google Ad Manager] 日志（例如CustomTargeting）。

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
   <td colname="col2"> <p>确认设置所需的步骤 <span class="keyword"> Audience Manager</span> 在转到步骤2之前，已完成UUID（如上所述） </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> 客户关怀或咨询 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 2 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理员将创建： </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">用于将Google Ad Manager摄取到的服务帐户登录 <span class="keyword"> Audience Manager</span>. </li> 
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
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">将分配给服务帐户的唯一电子邮件地址与存储段关联。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 5 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理员会提供Google Ad Manager网络ID。 这允许我们在调用API时传入网络ID。 </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 6 </p> </td> 
   <td colname="col2"> <p>按照详细说明编译先决条件并打开支持工单 <a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html">此处</a> 以启动日志摄取过程。 </p> </td> 
   <td colname="col3"> <p>您，或 <span class="keyword"> Audience Manager</span> 代表您咨询 </p> </td> 
  </tr> 
 </tbody> 
</table>
