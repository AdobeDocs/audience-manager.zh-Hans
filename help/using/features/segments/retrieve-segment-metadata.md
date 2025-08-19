---
description: Audience Manager将区段信息发送给数据合作伙伴时，会使用数字ID标识这些对象。 作为数据合作伙伴，当您与客户共享此信息（或自己使用它）时，实际的名称和描述可在报表、功能板或其他用户界面(UI)中为客户提供更好的体验。 数据合作伙伴可以通过本节中所述的手动或自动方法将这些友好名称提供给其客户。
seo-description: When Audience Manager sends segment information to a data partner, it identifies these objects with numeric IDs. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces (UI). Data partners can make these friendly names available to their customers with either the manual or automated methods described in this section.
seo-title: Retrieving Segment Metadata
solution: Audience Manager
title: 正在检索区段元数据
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
exl-id: 64922cf8-f7bf-4e33-871f-d33626b06360
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# 正在检索区段元数据 {#retrieving-segment-metadata}

Audience Manager将区段信息发送给数据合作伙伴时，会使用数字ID标识这些对象。 作为数据合作伙伴，当您与客户共享此信息（或自己使用它）时，实际的名称和描述可在报表、功能板或其他用户界面([!DNL UI])中为客户提供更好的体验。 数据合作伙伴可以通过本节中所述的手动或自动方法将这些友好名称提供给其客户。

## 手动方法 {#manual-method}

作为数据合作伙伴，您可能习惯通过手动流程从客户那里获取受众元数据。 这可能包括附加到电子邮件的文件，或者来自通过您为此目的构建和维护的[!DNL UI]添加该数据的客户的文件。 这些流程可正常使用，但通常非常繁琐、耗时，并且可能需要手动数据输入工作。 这些方法通常用于帮助快速启动并运行集成，但从长远来看，它们不能提供最佳客户体验。 作为替代方法，您可以使用[!DNL Audience Manager] [!DNL API]自动获取区段元数据。

## 自动化方法 {#automated-method}

[!DNL Audience Manager]提供了一组[REST API](../../api/rest-api-main/rest-api-main.md)，可让您自动检索区段元数据。 使用[!DNL API]，您可以创建按计划间隔检索区段元数据的作业，或在您处理[!DNL Audience Manager]数据并查找新区段ID时自动检索区段元数据的作业。 有关更多信息，请参阅下面的步骤。

### 步骤1：查看Audience Manager API

[REST API快速入门](../../api/rest-api-main/aam-api-getting-started.md)部分包含有关常规要求、身份验证、可用方法等的信息。 如果您之前未使用[!DNL Audience Manager] [!DNL API]，则这是一个很好的起点。

### 步骤2：请求OAuth2访问凭据

您需要客户端ID和密码才能进行[!DNL API]调用。 在集成设置过程中，您可以从集成专家处获取客户端ID和密码。 您还可以在[!UICONTROL Audience Manager Customer Care]向[!DNL amsupport@adobe.com]发送电子邮件请求。

### 步骤3：从每个集成客户那里收集特定于客户的信息

向每个集成客户请求以下内容：

* 用户名：适用于对与特定集成关联的目标具有只读权限的受限用户。
* 密码：用户密码。
* 目标ID：这是与为特定服务器到服务器集成创建的目标相关联的ID（整数）。

### 步骤4：使用API调用检索区段元数据

完成上述步骤后，您可以使用`GET`方法检索区段元数据。 有关示例请求和响应，请参阅[返回目标映射](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings)。 此调用返回[!DNL JSON]对象中格式化为键值对的区段数据。 下表列出了响应中返回的一些重要区段属性。

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
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span>区段ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>区段名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>简要描述区段的一些文本。 </p> </td> 
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
