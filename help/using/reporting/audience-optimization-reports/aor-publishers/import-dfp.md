---
description: 在 Audience Manager 启用 Audience Optimization for Publishers 之前，您必须确保满足本文中列出的所有先决条件。检查所有先决条件后，请与客户关怀团队联系。
seo-description: 在 Audience Manager 启用 Audience Optimization for Publishers 之前，您必须确保满足本文中列出的所有先决条件。检查所有先决条件后，请与客户关怀团队联系。
seo-title: 将 DFP 数据文件导入 Audience Manager
solution: Audience Manager
title: 将 DFP 数据文件导入 Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8 bbafe0 b268
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 将 DFP 数据文件导入 Audience Manager{#import-dfp-data-files-into-audience-manager}

在 Audience Manager 启用 Audience Optimization for Publishers 之前，您必须确保满足本文中列出的所有先决条件。检查所有先决条件后，请与客户关怀团队联系。

## Prerequisites for DFP Log Ingestion {#prereqs-dfp-ingestion}

Note that the process described in this section must be completed *before* you move on to the prerequisites for log ingestion enablement.

In order to use DFP ( [!DNL DoubleClick For Publishers]) log files in [!DNL Audience Manager], you must first set our [Audience Manager Unique User ID (UUID)](../../../reference/ids-in-aam.md) in the ad tag call. By doing this, our ID is included in the DFP logs and we can match IDs between DFP and [!DNL Audience Manager]. Use [!DNL Audience Manager] [!UICONTROL DIL] code or the [!UICONTROL Audience Management Module] to set the [!DNL Audience Manager] UUID in a first party cookie.

Here is how to set the [!DNL Audience Manager] ID in the ad tag call, as explained in our documentation:

* [通过Google Publisher标签(GPT)](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
* [通过Cookie目标](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)

You need to set the [!DNL Audience Manager] ID yourself, and can work with [!DNL Audience Manager] consulting to check if everything works. You have set the [!DNL Audience Manager] ID correctly if:

* `'aamid'` 是用作标识符的键。
* The User ID value is correctly formatted as the [!DNL Audience Manager] UUID, as described in our [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md).
* You have included the [!DNL Audience Manager] UUID in a defined field in your DFP logs (e.g. CustomTargeting).

## Prerequisites for Log Ingestion Enablement {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Confirm that the required steps to set the <span class="keyword"> Audience Manager</span> UUID (outlined above) have been completed prior to moving to Step 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> 客户关怀或咨询 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 2 </p> </td> 
   <td colname="col2"> <p>您的DFP管理员创建： </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">A service account for ingesting DFP logs into <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">新凭据。 <p>注意：这可能需要特定于此项目的唯一电子邮件地址，并在供应访问Google Storage Bucket时使用。 </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">私钥(基于JSON的凭证) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>您的DFP管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 3 </p> </td> 
   <td colname="col2"> <p>DFP管理员授予API访问服务帐户的权限。此步骤允许访问元数据来界定维度(行项目、订单、创意人员)。 <p>注意：使用在步骤中设置的服务帐户电子邮件访问权限授予访问API的权限。 </p> </p> </td> 
   <td colname="col3"> <p>您的DFP管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 4 </p> </td> 
   <td colname="col2"> <p>您的DFP管理员可以访问Google Storage Bucket。记住： </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">这可以通过Google组完成。 </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">将分配给服务帐户的唯一电子邮件地址关联到存储桶。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>您的DFP管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 5 </p> </td> 
   <td colname="col2"> <p>您的DFP管理员提供DFP网络ID。这允许我们在调用API时传入网络ID。 </p> </td> 
   <td colname="col3"> <p>您的DFP管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 6 </p> </td> 
   <td colname="col2"> <p>将电子邮件中的先决条件编译为AAM客户服务(aamsupport@adobe.com)，启动日志摄取流程。在下一节中使用模板起草电子邮件。 </p> </td> 
   <td colname="col3"> <p>You, or <span class="keyword"> Audience Manager</span> Consulting on your behalf </p> </td> 
  </tr> 
 </tbody> 
</table>

## E-Mail Template {#email-template}

要完成日志摄取的启用，请向我们发送电子邮件到aamsupport@adobe.com。Please use the [attached e-mail template](assets/enable_dfp_ingestion.txt).
