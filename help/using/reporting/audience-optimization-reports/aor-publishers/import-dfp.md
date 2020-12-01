---
description: 在 Audience Manager 启用 Audience Optimization for Publishers 之前，您必须确保满足本文中列出的所有先决条件。检查所有先决条件后，请与客户关怀团队联系。
seo-description: 在 Audience Manager 启用 Audience Optimization for Publishers 之前，您必须确保满足本文中列出的所有先决条件。检查所有先决条件后，请与客户关怀团队联系。
seo-title: 将Google Ad Manager数据文件导入Audience Manager
solution: Audience Manager
title: 将Google Ad Manager数据文件导入Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 16%

---


# 将Google Ad Manager（以前称为DFP）数据文件导入Audience Manager{#import-dfp-data-files-into-audience-manager}

在 Audience Manager 启用 Audience Optimization for Publishers 之前，您必须确保满足本文中列出的所有先决条件。检查所有先决条件后，请与客户关怀团队联系。

## Google Ad Manager日志摄取{#prereqs-dfp-ingestion}的先决条件

请注意，在&#x200B;*转到启用日志摄取的先决条件之前，此部分中描述的过程必须完成*。

要在[!DNL Audience Manager]中使用[!DNL Google Ad Manager]（以前称为Google DFP）日志文件，必须首先在ad标记调用中设置我们的[Audience Manager唯一用户ID(UUID)](../../../reference/ids-in-aam.md)。 这样，我们的ID将包含在[!DNL Google Ad Manager]日志中，并且我们可以匹配[!DNL Google Ad Manager]和[!DNL Audience Manager]之间的ID。 使用[!DNL Audience Manager] [!UICONTROL DIL]代码或[!UICONTROL Audience Management Module]在第一方cookie中设置[!DNL Audience Manager] UUID。

下面介绍如何在广告标记调用中设置[!DNL Audience Manager] ID，如我们的文档中所述：

* [通过Google Publisher标签(GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [通过Cookie目标](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

您需要自己设置[!DNL Audience Manager] ID，并可与[!DNL Audience Manager]咨询部门合作检查一切是否正常。 在以下情况下，您已正确设置[!DNL Audience Manager] ID:

* `'aamid'` 是用作标识符的键。
* 用户ID值的格式正确，为[!DNL Audience Manager] UUID，如Audience Manager](../../../reference/ids-in-aam.md)中[ ID索引中所述。
* 您已在[!DNL Google Ad Manager]日志中的定义字段中包含[!DNL Audience Manager] UUID（例如CustomTargeting）。

## 启用日志摄取{#prereqs-ingestion-enablement}的先决条件

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
   <td colname="col2"> <p>在转到步骤2之前，确认已完成设置<span class="keyword">Audience Manager</span> UUID（上述）的所需步骤 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> 受众经</span> 理客户关怀或咨询 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 2 </p> </td> 
   <td colname="col2"> <p>您的Google广告管理器管理员创建： </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">用于接收Google Ad Manager的服务帐户登录到<span class="keyword">Audience Manager</span>。 </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">新凭据。 <p>注意： 这可能需要特定于此项目的唯一电子邮件地址，并且在设置对Google存储存储段的访问时将使用。 </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">私钥（基于JSON的凭据） </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 3 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理员授予对服务帐户的API访问权限。 此步骤允许访问元数据以划分维（行项目、订单、创意）。 <p>注意： 使用您在步骤2中设置的服务帐户电子邮件访问权限授予访问API的权限。 </p> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 4 </p> </td> 
   <td colname="col2"> <p>您的Google广告管理器管理员将建立对Google存储存储段的访问权。 记住： </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">这可以通过Google组完成。 </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">将分配给服务帐户的唯一电子邮件地址与存储时段关联。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 5 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理员提供Google Ad Manager网络ID。 这允许我们在调用API时传入网络ID。 </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理员 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 6 </p> </td> 
   <td colname="col2"> <p>将电子邮件中的先决条件编译为AAM客户服务(aamsupport@adobe.com)以启动日志获取过程。 在下一节中使用模板起草电子邮件。 </p> </td> 
   <td colname="col3"> <p>您或<span class="keyword">Audience Manager</span>代表您咨询 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 电子邮件模板{#email-template}

要完成日志摄取启用，请向我们发送电子邮件至aamsupport@adobe.com。 请使用附加的[电子邮件模板](assets/enable_dfp_ingestion.txt)。
