---
description: Audience Manager将区段信息发送给数据合作伙伴时，它会用数字ID识别这些对象。作为数据合作伙伴，当您与客户共享此信息(或自己处理)时，实际的名称和描述为报告、仪表板或其他用户界面(UI)中的客户提供了更好的体验。数据合作伙伴可以使用本节所述的手动或自动化方法为客户提供这些友好的名称。
seo-description: Audience Manager将区段信息发送给数据合作伙伴时，它会用数字ID识别这些对象。作为数据合作伙伴，当您与客户共享此信息(或自己处理)时，实际的名称和描述为报告、仪表板或其他用户界面(UI)中的客户提供了更好的体验。数据合作伙伴可以使用本节所述的手动或自动化方法为客户提供这些友好的名称。
seo-title: 检索区段元数据
solution: Audience Manager
title: 检索区段元数据
uuid: 719e2c 41-8788-e8 a-967a-e367421 f9 f84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Retrieving Segment Metadata {#retrieving-segment-metadata}

Audience Manager将区段信息发送给数据合作伙伴时，它会用数字ID识别这些对象。As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces ([!DNL UI]). 数据合作伙伴可以使用本节所述的手动或自动化方法为客户提供这些友好的名称。

## Manual method {#manual-method}

作为数据合作伙伴，您很可能习惯于通过手动流程从客户获取受众元数据。This could include files attached to emails or from customers adding that data through a [!DNL UI] you've built and maintained for this purpose. 这些流程工作得很繁琐，但往往很麻烦，而且可能需要手动输入数据。这些方法通常用于帮助快速上手和运行，但并非长期提供最佳客户体验。As an alternative, you can use the [!DNL Audience Manager] [!DNL API] to get segment metadata automatically.

## Automated method {#automated-method}

[!DNL Audience Manager] 提供一组 [REST API](../../api/rest-api-main/rest-api-main.md) ，可让您自动检索区段元数据。[!DNL API]利用此功能，您可以在处理 [!DNL Audience Manager] 数据和查找新的区段ID时创建可按预定间隔检索区段元数据的作业。有关更多信息，请参阅以下步骤。

### 步骤1：查看Audience Manager API

The [Getting Started with REST APIs](../../api/rest-api-main/aam-api-getting-started.md) section contains information about general requirements, authentication, available methods, etc. This is a good place to begin if you haven't worked with the [!DNL Audience Manager] [!DNL API] before.

### 步骤2：请求OAuth访问凭据

You need a client ID and secret to make [!DNL API] calls. 在集成设置过程中，您可以从集成专家处获得客户端ID和机密。You can also send an email request to [!UICONTROL Audience Manager Customer Care] at [!DNL amsupport@adobe.com].

### 步骤3：收集每位集成客户的特定客户信息

从每个集成客户请求以下内容：

* 用户名：这适用于具有与特定集成关联的目标的只读权限的受限用户。
* 密码：用户密码。
* 目标ID：这是与为特定服务器到服务器集成创建的目标相关联的ID(整数)。

### 第步：使用API调用检索区段元数据

After completing the previous steps, you can use a `GET` method to retrieve segment metadata. For a sample request and response, see [Return Destination Mappings](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). This call returns segment data formatted as key-value pairs in a [!DNL JSON] object. 下表列出了响应中返回的一些重要区段属性。

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DestinationMappingID</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 区段ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ElementName</code> </p> </td> 
   <td colname="col2"> <p>区段名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ElementDescription</code> </p> </td> 
   <td colname="col2"> <p>简短描述区段的文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ElementStatus</code> </p> </td> 
   <td colname="col2"> <p>区段映射的当前状态。返回的状态选项包括： </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active活动</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> 非活动</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> 已删除</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>