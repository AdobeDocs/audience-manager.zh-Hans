---
description: 数据导出控制可防止您在此操作违反数据隐私或数据使用协议时向目标发送数据。
seo-description: 数据导出控制可防止您在此操作违反数据隐私或数据使用协议时向目标发送数据。
seo-title: 数据导出控制
solution: Audience Manager
title: 数据导出控制
uuid: de7f3608-c0 cb-4049-973a-8be55425 c600
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# 数据导出控制 {#data-export-controls}

[!UICONTROL Data Export Controls] 防止您在此行为违反数据隐私或数据使用协议时向目标发送数据。

## 概述 {#overview}

[!UICONTROL Data Export Controls] 可让您对 [数据源](../features/datasources-list-and-settings.md#data-sources-list-and-settings) 和 [目标进行分类](../features/destinations/destinations.md)。您应用的分类将确定数据何时可以导出到目标位置。此功能包括：

* **[!UICONTROL Data Export Controls]**：您可以在 *数据源上设置数据导出控制*。在数据源上设置时，这些控件限制了如何使用数据源及其特征。
* **[!UICONTROL Data Export Labels]**：您可以在目标上 *设置数据导出标签*。在目标上设置时，这些标签会识别目标如何使用数据。请参阅 [将数据导出标签添加到目标](/help/using/features/destinations/add-data-export-labels.md) 以了解如何将导出标签添加到目标。

根据应用于数据源和目标的分类，导出控件将停止您：

* 在特征属于数据源时向区段添加特征，该数据源具有数据导出控制，该控件与将区段映射到的一个或多个目标上的数据导出标签不兼容。
例如，假设区段使用导出标签 **[UICONTROL映射到目标位置！此目标可与个人识别信息(PII)结合]**&#x200B;使用。导出控件可阻止您向该区段添加特征，如果特征所属的数据源具有UICCONTRL表示 **[数据导出控件！不能绑定到个人识别信息(PII)]**。
* 将任何数据发送到目标目标都有一个数据导出标签，该标签被数据导出控制所阻止：
   * 包含的特征的数据源；
   * 在包含区段中使用的特征的数据源；
   * 由包含区段利用的配置文件合并规则；
   * 包含区段配置文件合并规则使用的任何数据源。

[!UICONTROL Data Export Controls] 可自动为所有Audience Manager客户提供。但是，您需要管理员权限才能将导出控件添加到数据源。向目标中添加导出标签需要管理员权限 *或* 足够的权限来创建或编辑目标。

## 定义的控件和标签 {#controls-labels}

[!UICONTROL Data Export Controls] 提供以下控件，帮助您对数据源和目标进行分类。

要阻止数据交付，您必须使用导出控制对数据源进行分类，并向目标添加一个导出标签。如果仅将导出控件应用于数据源或目标，则此功能不会限制数据交付。当在数据源 *和* 目标上设置时，导出控件将限制可添加到区段的特征，并阻止向目标发送区段成员。

此外，在数据交付限制生效之前，至少一个导出标签必须与导出控制相匹配。例如，例如，将 [!UICONTROL PII] 导出控件添加到数据源。接下来，将站点定位标签添加到目标位置。在这种情况下，导出控件不会限制数据交付，因为设置不匹配。但是，如果您将 [!UICONTROL PII] 导出标签添加到目标，导出控件将阻止导出。

>[!IMPORTANT]
>
>[您无法通过在区段的数据源上放置数据导出控制来阻止区段的导出，您必须在以下任一位置设置控件：
> * 区段中使用的特征的数据来源；
> * 区段利用的配置文件合并规则；
> * 区段的配置文件合并规则使用的任何数据源。


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 数据源的数据导出控制 </th> 
   <th colname="col2" class="entry"> 目标的数据导出标签 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 无限制</span></b> </td> 
   <td colname="col2"> 不适用 </td> 
   <td colname="col3"> 默认情况下，不会对新数据源和目标设置导出限制。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 无法绑定到个人识别信息</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目标可与个人识别信息(PII)结合使用</span></b> </td> 
   <td colname="col3">选择后，您不能： 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">将特征添加到映射到使用PII的目标的区段。 </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">将使用特征构建的区段映射到使用PII的目标目标。 </li> 
    </ul> <p>第三方数据提供商通常需要这种情况，并且使用包含广告/媒体跟踪信息的数据源。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 无法用于现场广告定位</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目标可用于现场广告定位</span></b> </td> 
   <td colname="col3">选择后，您不能： 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">为映射到目标的区段添加特征，以便根据访客的Web浏览历史记录自定义广告投放。 </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">将使用特征构建的区段映射到目标，从数据源到目标，根据访客的Web浏览历史记录自定义广告投放。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 无法用于非现场广告定位</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目标可用于非现场广告定位</span></b> </td> 
   <td colname="col3">通常使用这些限制，在选择时，您不能： 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">向映射到目标的区段添加特征，以便在其他网站上重定向用户。 </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">将使用特征构建的区段映射到数据源，以便在其他网站上重定向用户。 </li> 
    </ul> <p>处理来自社交媒体平台的数据时经常需要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 无法用于现场个性化</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目标可用于现场广告个性化</span></b> </td> 
   <td colname="col3">选择后，您不能： 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">为映射到目标的区段添加特征，以便根据用户兴趣或Web浏览历史记录自定义内容。 </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">将使用特征构建的区段映射到目标，从数据源到目标，根据用户兴趣或网络浏览历史定制内容。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 工作流 {#workflow}

要开始，请查看数据源和目标文档。这些文章提供有关如何向数据源和目标添加导出控件和标签的说明。

* [创建数据源](../features/manage-datasources.md#create-data-source)
* [将数据导出标签添加到目标位置](../features/destinations/add-data-export-labels.md)