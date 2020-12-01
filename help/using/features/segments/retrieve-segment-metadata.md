---
description: 当Audience Manager向数据合作伙伴发送细分信息时，它会用数字ID标识这些对象。 作为数据合作伙伴，当您与客户共享此信息（或亲自处理）时，实际的名称和描述将为报告、仪表板或其他用户界面(UI)中的客户提供更好的体验。 数据合作伙伴可以通过本节中介绍的手动或自动化方法，为客户提供这些友好名称。
seo-description: 当Audience Manager向数据合作伙伴发送细分信息时，它会用数字ID标识这些对象。 作为数据合作伙伴，当您与客户共享此信息（或亲自处理）时，实际的名称和描述将为报告、仪表板或其他用户界面(UI)中的客户提供更好的体验。 数据合作伙伴可以通过本节中介绍的手动或自动化方法，为客户提供这些友好名称。
seo-title: 检索区段元数据
solution: Audience Manager
title: 检索区段元数据
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 1%

---


# 检索区段元数据 {#retrieving-segment-metadata}

当Audience Manager向数据合作伙伴发送细分信息时，它会用数字ID标识这些对象。 作为数据合作伙伴，当您与客户共享此信息（或亲自处理）时，实际的名称和描述将为报告、仪表板或其他用户界面([!DNL UI])中的客户提供更好的体验。 数据合作伙伴可以通过本节中介绍的手动或自动化方法，为客户提供这些友好名称。

## 手动方法{#manual-method}

作为受众合作伙伴，您可能习惯于通过手动流程从客户处获取数据。 这可能包括附加到电子邮件或来自通过[!DNL UI]为此目的构建和维护的数据的客户的文件。 这些过程是有效的，但往往繁琐、耗时，并且可能需要手动输入数据。 这些方法通常用于帮助快速建立和运行集成，但从长远看，它们不能提供最佳客户体验。 作为替代方法，您可以使用[!DNL Audience Manager] [!DNL API]自动获取段元数据。

## 自动化方法{#automated-method}

[!DNL Audience Manager] 提供一组REST  [API,](../../api/rest-api-main/rest-api-main.md) 使您可以自动检索段元数据。使用[!DNL API]，您可以创建以预定时间间隔检索段元数据的作业，或者在处理[!DNL Audience Manager]数据并查找新段ID时自动检索段元数据。 有关更多信息，请参阅以下步骤。

### 第1步：查看Audience ManagerAPI

[REST API入门](../../api/rest-api-main/aam-api-getting-started.md)部分包含有关一般要求、身份验证和可用方法等的信息。 如果您以前没有使用[!DNL Audience Manager] [!DNL API]，则这是一个不错的开始。

### 第2步：请求OAuth2访问凭据

您需要一个客户端ID和机密才能进行[!DNL API]调用。 在集成设置过程中，您可以从集成专家处获取客户端ID和机密。 您还可以向[!UICONTROL Audience Manager Customer Care]发送电子邮件请求，地址为[!DNL amsupport@adobe.com]。

### 第3步：从每个集成的客户处收集客户特定信息

请求每个集成客户提供以下信息：

* 用户名：这适用于对与特定集成关联的目标具有只读权限的受限用户。
* 密码：用户密码。
* 目标ID:这是与为特定服务器到服务器集成创建的目标关联的ID（整数）。

### 第4步：通过API调用检索段元数据

完成上述步骤后，可使用`GET`方法检索段元数据。 有关示例请求和响应，请参阅[返回目标映射](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings)。 此调用返回在[!DNL JSON]对象中格式化为键值对的段数据。 下表列出了响应中返回的一些重要段属性。

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> destinationMappingId</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span>段ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>区段名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>简要描述该段的一些文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>区段映射的当前状态。 返回的状态选项包括： </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>