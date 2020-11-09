---
description: 元数据文件将数字ID与可阅读和理解的名称链接起来。 Audience Optimization报告在各种报告选项菜单中显示可读名称。
seo-description: 元数据文件将数字ID与可阅读和理解的名称链接起来。 Audience Optimization报告在各种报告选项菜单中显示可读名称。
seo-title: 元数据文件的概述和映射
solution: Audience Manager
title: 元数据文件的概述和映射
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: log files
translation-type: tm+mt
source-git-commit: 5d6983f5308f1dfd4560ee1b38bcaee3ca6e422f
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 4%

---


# 元数据文件的概述和映射{#overview-and-mappings-for-metadata-files}

元数据文件将数字ID与可阅读和理解的名称链接起来。 Audience Optimization报告在各种报告选项菜单中显示可读名称。

## 概述 {#overview}

对元数据及其使用方式的审查。 元数据文件必须附带数据文件。 元数据文件内容将数据文件信息与报表菜单中相关的、可读标签相匹配。 有关详细信息，请参 [阅Audience Optimization报告和可操作日志文件的数据文件](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)。

### 元数据文件包含有关其他数据的数据

元数据文件包含有关其他类型数据的信息。 为了帮助您了解其工作方式，让我们来查看接收数 [!DNL Audience Manager] 据的方式。

在印象或单击事件期 [!DNL Audience Manager] 间，将接收URL字符串(称为事件调用) *中的数据*。

事件调用将信息组织成一组定义的键值对。 键值对中的值包含数字数据。 元数据文件包含每个键值对中与ID对应的名称和其他可读信息。

### 元数据链接ID到可读名称

元数据文件需要将数字ID绑定到可读名称。 例如，假设事件调用在键值对中包含创意ID，如下所示： `d_creative:1234`. 如果没有元数据文件，此创意会在选项菜单中显示为1234。

但是，格式正确的元数据文件可以将此创意绑定到实际名称（如“广告商创意A”），该名称可在报告中读取和识别。

### 何时需要元数据文件

首先，当您要使用事件报告时，Audience Optimization调用中需要一个元数据文件以及下面列出的所有 [参数](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)。

其次，如果您要将自己的数据发送到，或希望 [!DNL Audience Manager] 在报告中看到未与我们集成的其他提供商的数据，则需要一个元数据文件。 例如， [!DNL Audience Manager] 与Google的多次单击 [活动管理器(DCM](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) )集成。 由于这种关系， [!DNL Audience Manager] 可以将ID与报表选项使用的名称和说明相关联。 如果没有集成，我们仍可以摄取数据，但报表选项将显示数字ID，而不是描述性名称。

![元数据菜单图像](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## 文件映射 {#file-mappings}

下表列表了保存报表所使用数据的键值 [!UICONTROL Audience Optimization] 对。 如果您需要使用元数据文件，它将包含与这些键值对中的值对应的人可读信息。 这些键的值只接受整数（数据类型INT）。 Note, *italics* indicates a variable placeholder. 其他元素是常量或键，不会更改。

>[!IMPORTANT]
>
>如果您使用报 [!UICONTROL Audience Optimization] 表， *在事件* 调用中需要所有这些值。

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 报告选项 </th> 
   <th colname="col2" class="entry"> 元数据键值对 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>广告商 </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>这是广告商创建数据源时提供的数据源ID或集成代码。 See <a href="../../../features/manage-datasources.md#create-data-source"> Create a Data Source</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>业务部(BU) </p> </td> 
   <td colname="col2"> <p> <code>d_bu = <i>business unit ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>促销活动 </p> </td> 
   <td colname="col2"> <p> <code>d_campaign = <i>campaign ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>创意 </p> </td> 
   <td colname="col2"> <p> <code>d_creative = <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>接受2个不同的键值对： </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_exchange = <i>ID for the exchange that served the ad</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_site = <i>ID for the site an ad served on</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>插入顺序(IO) </p> </td> 
   <td colname="col2"> <p> <code>d_io = <i>insertion order ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>平台 </p> </td> 
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>这是提 <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 供元数据信息</a> （例如，DFA、Atlas、GBM、MediaMath等）的平台的数据源ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>策略 </p> </td> 
   <td colname="col2"> <p> <code>d_tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>垂直 </p> </td> 
   <td colname="col2"> <p> <code>d_vert = <i>vertical ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 事件调用ID的形状文件名、内容和投放路径 {#how-ids-shape-file-names}

这些键值对传入的ID有助于创建元数据文件名及其内容。 以下部分和插图演示了其工作原理。 这些示例构建一个文件，其中包含活动中创意者的名称，但可以使用其他组合。

### 事件呼叫

在此示例中，我们将创建一个元数据文件，将创意名称引入报 [!UICONTROL Audience Optimization] 表。 为此，我们需要从事件调用中提取创意、活动和数据源ID。

![事件呼叫图像](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### 文件名

文件名基于创意、活动和数据源ID。 在这种情况下，请在此处比较事件调用中键值数据与文件名中键值数据的使用方式的差异。

在文件名中：

* 数据源密钥从更 `dpid` 改为 `d_src`。

* 创意ID和活动ID代表类别，而不是实际标识符。

![如何生成文件名](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

See [Naming Conventions for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### 文件内容

在此示例中，文件内容反映在事件调用中传入的创意ID和活动ID。 此处的新元素是可读名称。 处理后，该文件中的名称将作为选项显示在报告的“创意”菜 [!UICONTROL Audience Optimization] 单中。

![元数据文件的内容](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

See [Content Format for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### 文件投放

在命名文件并将数据添加到文件后，将其发送到由提供的AmazonS3存储目录 [!DNL Audience Manager]。 See [Delivery Methods for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORELIKETHIS]
>
>* [Audience Optimization报告的数据文件](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [通过像素调用捕获营销活动点击数据](../../../integration/media-data-integration/click-data-pixels.md)
>* [通过像素调用捕获营销活动展示数据](../../../integration/media-data-integration/impression-data-pixels.md)

