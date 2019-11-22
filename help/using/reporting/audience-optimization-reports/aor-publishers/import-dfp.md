---
description: 在 Audience Manager 启用 Audience Optimization for Publishers 之前，您必须确保满足本文中列出的所有先决条件。检查所有先决条件后，请与客户关怀团队联系。
seo-description: 在 Audience Manager 启用 Audience Optimization for Publishers 之前，您必须确保满足本文中列出的所有先决条件。检查所有先决条件后，请与客户关怀团队联系。
seo-title: 将 DFP 数据文件导入 Audience Manager
solution: Audience Manager
title: 将 DFP 数据文件导入 Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
translation-type: tm+mt
source-git-commit: 9f091fa765e937fb47b3328d8f5f2dab24a85040

---


# 将 DFP 数据文件导入 Audience Manager{#import-dfp-data-files-into-audience-manager}

在 Audience Manager 启用 Audience Optimization for Publishers 之前，您必须确保满足本文中列出的所有先决条件。检查所有先决条件后，请与客户关怀团队联系。

## DFP日志摄取的先决条件 {#prereqs-dfp-ingestion}

请注意，在转到启用日志获取的先决条件之 *前* ，必须先完成本节中介绍的过程。

要在中使用DFP( [!DNL DoubleClick For Publishers])日志文件，您必须先在 [!DNL Audience Manager]ad标记调用中设置 [Audience Manager唯一用户ID(UUID)](../../../reference/ids-in-aam.md) 。 这样，我们的ID将包含在DFP日志中，并且我们可以在DFP和之间匹配ID [!DNL Audience Manager]。 使 [!DNL Audience Manager] 用 [!UICONTROL DIL] 代码或在第 [!UICONTROL Audience Management Module] 一方Cookie中设置 [!DNL Audience Manager] UUID。

下面是如何在广告标 [!DNL Audience Manager] 签调用中设置ID，如我们的文档中所述：

* [通过Google Publisher标记(GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [通过Cookie目标](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

您需要自己设置 [!DNL Audience Manager] ID，并可以与咨询部门合作检查 [!DNL Audience Manager] 一切是否正常。 在以下情况下，您已 [!DNL Audience Manager] 正确设置ID:

* `'aamid'` 是用作标识符的键。
* 用户ID值的格式正确，为 [!DNL Audience Manager] UUID，如Audience manager中 [的ID索引中所述](../../../reference/ids-in-aam.md)。
* 您已将 [!DNL Audience Manager] UUID包含在DFP日志的定义字段中（例如CustomTargeting）。

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
   <td colname="col2"> <p>在转到步骤2之前，确认已完成设置 <span class="keyword"> Audience Manager</span> UUID（上述）所需的步骤 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager客户关怀</span> 或咨询 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 2 </p> </td> 
   <td colname="col2"> <p>您的DFP管理员将创建： </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">用于将DFP日志引入 <span class="keyword"> Audience manager的服务帐户</span>。 </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">新凭据。 <p>注意： 这可能需要特定于此项目的唯一电子邮件地址，并且在设置对Google存储桶的访问时将使用该地址。 </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">私钥（基于JSON的凭证） </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>您的DFP管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 3 </p> </td> 
   <td colname="col2"> <p>您的DFP管理员授予对服务帐户的API访问权限。 通过此步骤，可以访问元数据来划分维（行项目、订单、创意）。 <p>注意： 使用您在步骤2中设置的服务帐户电子邮件访问权限授予访问API的权限。 </p> </p> </td> 
   <td colname="col3"> <p>您的DFP管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 4 </p> </td> 
   <td colname="col2"> <p>您的DFP管理员将建立对Google存储桶的访问权限。 记住： </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">这可以通过Google组完成。 </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">将分配给服务帐户的唯一电子邮件地址关联到存储存储桶。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>您的DFP管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 5 </p> </td> 
   <td colname="col2"> <p>您的DFP管理员提供DFP网络ID。 这允许我们在调用API时传入网络ID。 </p> </td> 
   <td colname="col3"> <p>您的DFP管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 6 </p> </td> 
   <td colname="col2"> <p>将电子邮件中的先决条件编译为AAM客户服务(aamsupport@adobe.com)，以启动日志摄取过程。 在下一节中使用模板起草电子邮件。 </p> </td> 
   <td colname="col3"> <p>您或 <span class="keyword"> Audience Manager</span> Consulting代表您 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 电子邮件模板 {#email-template}

要最终确定日志摄取启用，请向我们发送电子邮件至aamsupport@adobe.com。 请使用附 [加的电子邮件模板](assets/enable_dfp_ingestion.txt)。
