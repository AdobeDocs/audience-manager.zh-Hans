---
description: 当此操作违反数据隐私或数据使用协议时，“数据导出控制”会阻止您向目标发送数据。
seo-description: 当此操作违反数据隐私或数据使用协议时，“数据导出控制”会阻止您向目标发送数据。
seo-title: 数据导出控制
solution: Audience Manager
title: 数据导出控制
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: 数据导出控制
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 2%

---

# 数据导出控制 {#data-export-controls}

[!UICONTROL Data Export Controls] 当此操作违反数据隐私或数据使用协议时，阻止您向目标发送数据。

## 概述 {#overview}

[!UICONTROL Data Export Controls] 允许您对数据 [源](../features/datasources-list-and-settings.md#data-sources-list-and-settings) 和目标 [进行分类](../features/destinations/destinations.md)。您应用的分类可确定何时可以将数据导出到目标。 此功能包括：

* **[!UICONTROL Data Export Controls]**:您可以对数据源设置数据 *导出控件*。在数据源上设置时，这些控件会限制数据源及其特征的使用方式。
* **[!UICONTROL Data Export Labels]**:您可以对目标设置数据导 *出标签*。在目标上设置后，这些标签会标识目标如何使用数据。 请参阅[向目标添加数据导出标签](/help/using/features/destinations/add-data-export-labels.md)以了解如何向目标添加导出标签。

根据应用于数据源和目标的分类，导出控件可阻止您：

* 当特征属于某个数据源（该数据源具有与区段映射到的一个或多个目标上的数据导出标签不兼容的数据导出控件）时，向区段添加特征。
例如，假设某个区段被映射到具有导出标签**[!DNL This destination may enable a combination with personally identifiable information (PII)]**&#x200B;的目标。 如果特征所属的数据源具有显示&#x200B;**[!DNL Cannot be tied to personally identifiable information (PII)]**&#x200B;的数据导出控件，则导出控件会阻止您向该区段添加特征。
* 将任何数据发送到目标目标具有数据导出标签，该标签被任何目标上的数据导出控件阻止：
   * 包含特征的数据源；
   * 在包含的区段中使用的特征的数据源；
   * 包含的区段利用的用户档案合并规则；
   * 包含区段的配置文件合并规则使用的任何数据源。

[!UICONTROL Data Export Controls] 可自动供所有Audience Manager客户使用。但是，您需要管理员权限才能将导出控件添加到数据源。 向目标添加导出标签需要管理员权限&#x200B;*或*&#x200B;足够的权限来创建或编辑目标。

## 定义{#controls-labels}的控件和标签

[!UICONTROL Data Export Controls] 提供以下控件以帮助您对数据源和目标进行分类。

要阻止数据交付，您必须使用导出控件对数据源进行分类，并向目标添加导出标签。 如果仅将导出控件应用于数据源或目标，则此功能不会限制数据交付。 在数据源&#x200B;*和*&#x200B;目标上进行设置后，导出控件将限制您可以添加到区段的特征，并阻止将区段成员发送到目标。

此外，在数据传送限制生效之前，必须至少有一个导出标签与导出控件匹配。 例如，假设您将[!UICONTROL PII]导出控件添加到数据源。 接下来，将现场定位标签添加到目标。 在这种情况下，导出控件将不会限制数据提交，因为设置不匹配。 但是，如果将[!UICONTROL PII]导出标签添加到目标，则导出控件将阻止导出。

>[!IMPORTANT]
>
>不能通过将数据导出控件放置在区段的数据源上来阻止导出区段，您必须在以下任一位置设置控件：
> * 区段中使用的特征的数据源；
> * 区段利用的配置文件合并规则；
> * 区段的用户档案合并规则使用的任何数据源。


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
   <td colname="col3"> 默认情况下，不会对新数据源和目标设置导出限制。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 不能绑定到个人身份信息</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目标可能会启用包含个人身份信息(PII)的组合</span></b> </td> 
   <td colname="col3">选择后，您将无法： 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">将特征添加到映射到使用PII的目标的区段。 </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">将通过特征从数据源构建的区段映射到使用PII的目标。 </li> 
    </ul> <p>当使用包含广告/媒体跟踪信息的数据源时，第三方数据提供商通常需要这样做。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 不能用于现场广告定位</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目标可用于现场广告定位</span></b> </td> 
   <td colname="col3">选择后，您将无法： 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">将特征添加到映射到目标的区段，这些区段可根据访客的Web浏览历史记录自定义广告投放。 </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">将通过数据源中的特征构建的区段映射到根据访客的Web浏览历史记录自定义广告投放的目标。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 不能用于站外广告定位</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目标可用于站外广告定位</span></b> </td> 
   <td colname="col3">这些限制通常用于选择后，您无法： 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">将特征添加到映射到目标的区段，以便在其他网站上重新定位用户。 </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">将通过特征从数据源构建的区段映射到可重新定位其他网站上用户的目标。 </li> 
    </ul> <p>使用来自社交媒体平台的数据时通常需要使用此参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 不能用于网站上的个性化</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 此目标可用于网站广告个性化</span></b> </td> 
   <td colname="col3">选择后，您将无法： 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">将特征添加到映射到根据用户兴趣或Web浏览历史记录自定义内容的目标的区段。 </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">将通过数据源中的特征构建的区段映射到根据用户兴趣或Web浏览历史记录自定义内容的目标。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 工作流 {#workflow}

要开始配置，请查看数据源和目标文档。 这些文章提供了有关如何向数据源和目标添加导出控件和标签的说明。

* [创建数据源](../features/manage-datasources.md#create-data-source)
* [将数据导出标签添加到目标](../features/destinations/add-data-export-labels.md)
