---
description: 数据导出控制功能可防止您在此操作违反数据隐私或数据使用协议时向目标发送数据。
seo-description: 数据导出控制功能可防止您在此操作违反数据隐私或数据使用协议时向目标发送数据。
seo-title: 数据导出控制
solution: Audience Manager
title: 数据导出控制
uuid: de7f3608-c0cb-4049-973a-8be54525c600
translation-type: tm+mt
source-git-commit: 22657113512e136296be5c4bcb8e092e65f45c06

---


# 数据导出控制 {#data-export-controls}

[!UICONTROL Data Export Controls] 防止您在此操作违反数据隐私或数据使用协议时向目标发送数据。

## 概述 {#overview}

[!UICONTROL Data Export Controls] 允许您对数据 [源和目标](../features/datasources-list-and-settings.md#data-sources-list-and-settings)[进行分类](../features/destinations/destinations.md)。 您应用的分类确定何时可以或不能将数据导出到目标。 此功能包括：

* **[!UICONTROL Data Export Controls]**:可以对数据源设置“数据导 *出控件”*。 在数据源上设置时，这些控件会限制数据源及其特征的使用方式。
* **[!UICONTROL Data Export Labels]**:您可以在目标上设置数据导出 *标签*。 当在目标上设置时，这些标签会标识目标使用数据的方式。 请参 [阅将数据导出标签添加到目标](/help/using/features/destinations/add-data-export-labels.md) ，了解如何将导出标签添加到目标。

根据应用于数据源和目标的分类，导出控件可阻止您：

* 当特征属于数据源时向区段添加特征，该数据源具有与区段映射到的一个或多个目标上的数据导出标签不兼容的数据导出控件。
例如，假设区段映射到具有导出标签的目标 **[!DNL This destination may enable a combination with personally identifiable information (PII)]**。 如果特征所属的数据源具有表示的数据导出控件，则导出控件会阻止您向该段添加特征 **[!DNL Cannot be tied to personally identifiable information (PII)]**。
* 将任何数据发送到目标目标具有数据导出标签，该标签被以下任一位置的数据导出控件阻止：
   * 包含的特征的数据源；
   * 在包含的段中使用的特征的数据源；
   * 包含的细分利用的档案合并规则；
   * 包含的区段的配置文件合并规则使用的任何数据源。

[!UICONTROL Data Export Controls] 可自动向所有Audience manager客户提供。 但是，您需要管理员权限才能向数据源添加导出控件。 向目标添加导出标签需要管理员权 *限* ，或者需要足够的权限才能创建或编辑目标。

## 定义的控件和标签 {#controls-labels}

[!UICONTROL Data Export Controls] 提供以下控件帮助您对数据源和目标进行分类。

要阻止数据传送，您必须使用导出控件对数据源进行分类，并向目标添加导出标签。 如果仅将导出控件应用于数据源或目标，则此功能不会限制数据交付。 在数据源和目标上设 *置* ，导出控件将限制可添加到区段的特征，并阻止将区段成员发送到目标。

此外，在数据传送限制生效之前，至少一个导出标签必须与导出控件匹配。 例如，假设您向数据源 [!UICONTROL PII] 添加导出控件。 然后，将站点定位标签添加到目标。 在这种情况下，导出控件不会限制数据传送，因为设置不匹配。 但是，如果向目标添 [!UICONTROL PII] 加导出标签，则导出控件将阻止导出。

>[!IMPORTANT]
>
>您不能通过将数据导出控件放在区段的数据源上来阻止区段的导出，必须对以下任一项设置控件：
> * 区段中使用的特征的数据源；
> * 细分利用的档案合并规则；
> * 区段的配置文件合并规则使用的任何数据源。


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 数据源的数据导出控件 </th> 
   <th colname="col2" class="entry"> 目标的数据导出标签 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 无限制</span></b> </td> 
   <td colname="col2"> 不适用 </td> 
   <td colname="col3"> 默认情况下，新数据源和目标上不设置导出限制。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 不能绑定到个人识别信息</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目标可能允许将个人识别信息(PII)</span></b> </td> 
   <td colname="col3">选择后，您无法： 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">向映射到使用PII的目标的区段添加特征。 </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">将使用特征从数据源构建的区段映射到使用PII的目标。 </li> 
    </ul> <p>这通常是第三方数据提供商在使用包含广告／媒体跟踪信息的数据源时所必需的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 不能用于现场广告定位</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目标可用于现场广告定位</span></b> </td> 
   <td colname="col3">选择后，您无法： 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">向映射到目标的区段添加特征，这些目标根据访客的Web浏览历史记录自定义广告投放。 </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">将使用数据源中的特征构建的区段映射到根据访客的Web浏览历史记录自定义广告投放的目标。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 不能用于非现场广告定位</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目标可用于非现场广告定位</span></b> </td> 
   <td colname="col3">这些限制通常与“选择后，您不能： 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">将特征添加到映射到目标的区段，这些目标在其他站点上重新定位用户。 </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">将使用数据源中的特征构建的区段映射到重新定位其他站点用户的目标。 </li> 
    </ul> <p>处理来自社交媒体平台的数据时通常需要此功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 不能用于在线个性化</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目标可用于在线广告个性化</span></b> </td> 
   <td colname="col3">选择后，您无法： 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">向映射到目标的区段添加特征，这些目标根据用户兴趣或Web浏览历史记录自定义内容。 </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">将使用数据源中的特征构建的区段映射到根据用户兴趣或Web浏览历史自定义内容的目标。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 工作流 {#workflow}

要开始使用，请查看数据源和目标文档。 这些文章提供了有关如何向数据源和目标添加导出控件和标签的说明。

* [创建数据源](../features/manage-datasources.md#create-data-source)
* [将数据导出标签添加到目标](../features/destinations/add-data-export-labels.md)