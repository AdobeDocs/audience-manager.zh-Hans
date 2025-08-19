---
description: 元数据文件将数字ID链接到您可以阅读和理解的名称。 Audience Optimization报表在各种报表选项菜单中显示了可读名称。
seo-description: A metadata file links numeric IDs with names you can read and understand. The Audience Optimization reports display readable names in the various report options menus.
seo-title: Overview and Mappings for Metadata Files
solution: Audience Manager
title: 元数据文件的概述和映射
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: Log Files
exl-id: 8c59ab80-f04a-42df-891e-a187ecd0219f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 2%

---

# 元数据文件的概述和映射{#overview-and-mappings-for-metadata-files}

元数据文件将数字ID链接到您可以阅读和理解的名称。 Audience Optimization报表在各种报表选项菜单中显示了可读名称。

## 概述 {#overview}

元数据及其使用方式的审查。 元数据文件必须附有数据文件。 元数据文件内容将数据文件信息与报表菜单中人工可读的相关标签相匹配。 有关详细信息，请参阅[Audience Optimization报表的数据文件以及可操作的日志文件](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)。

### 元数据文件包含有关其他数据的数据

元数据文件包含有关其他类型数据的信息。 为了帮助您了解其工作方式，让我们看看[!DNL Audience Manager]如何接收数据。

在展示或点击事件期间，[!DNL Audience Manager]在称为&#x200B;*事件调用*&#x200B;的URL字符串中接收数据。

事件调用将信息整理到一组定义的键值对中。 键值对中的值包含数字数据。 元数据文件包含与每个键值对中的ID对应的名称和其他可读信息。

### 元数据链接ID到可读名称

将数字ID绑定到可读名称需要元数据文件。 例如，假设事件调用在键值对中包含创意ID，如下所示： `d_creative:1234`。 如果没有元数据文件，此创意内容在选项菜单中将显示为1234。

但是，格式正确的元数据文件可将此创意绑定回“广告商Creative A”等真实名称，您可以读取并在报表中识别该名称。

### 何时需要元数据文件

首先，当您要使用[Audience Optimization报表](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)时，在事件调用中需要元数据文件以及下面列出的所有参数。

其次，如果您向[!DNL Audience Manager]发送自己的数据，或者您希望在报表中查看来自与我们未集成的其他提供商的数据，则需要元数据文件。 例如，[!DNL Audience Manager]与Google的[双击Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM)集成。 由于这种关系，[!DNL Audience Manager]可以将ID与报告选项使用的名称和描述相关联。 如果没有集成，我们仍可以摄取数据，但报表选项将显示数字ID，而不是描述性名称。

![元数据菜单图像](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## 文件映射 {#file-mappings}

下表列出了包含[!UICONTROL Audience Optimization]报表所使用数据的键值对。 如果需要使用元数据文件，它将包含与键值对中的值对应的人类可读信息。 这些键的值仅接受整数（数据类型INT）。 请注意，*斜体*&#x200B;表示变量占位符。 其他元素为常量或键，不会更改。

>[!IMPORTANT]
>
>如果您使用的是[!UICONTROL Audience Optimization]报告，则事件调用中需要这些值的&#x200B;*所有*。

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 报表选项 </th> 
   <th colname="col2" class="entry"> 元数据键值对 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>广告商 </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>这是在创建数据源时提供的广告商的数据源ID或集成代码。 请参阅<a href="../../../features/manage-datasources.md#create-data-source">创建数据Source</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>业务单元(BU) </p> </td> 
   <td colname="col2"> <p> <code>d_bu = <i>business unit ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>促销活动 </p> </td> 
   <td colname="col2"> <p> <code>d_campaign = <i>campaign ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative </p> </td> 
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
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>这是提供元数据信息的平台的<a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings">数据源</a> ID（例如，DFA、Atlas、GBM、MediaMath等）。 </p> </td> 
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

## 事件调用ID如何影响文件名、内容和投放路径 {#how-ids-shape-file-names}

这些键值对传入的ID可帮助创建元数据文件名及其内容。 以下部分和插图演示了此功能的使用方法。 这些示例会生成一个包含营销策划中创意内容名称的文件，但也可以使用其他组合。

### 事件调用

在此示例中，我们将创建一个元数据文件，将创意名称引入[!UICONTROL Audience Optimization]报表中。 为此，我们需要从事件调用中提取创意、营销活动和数据源ID。

![事件调用图像](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### 文件名

文件名基于创意ID、营销活动ID和数据源ID。 在本例中，比较一下在事件调用中键值数据与在文件名中的使用方式之间的区别。

在文件名中：

* 数据源密钥从`dpid`更改为`d_src`。

* 创意和营销活动ID表示类别而不是实际标识符。

![如何生成文件名](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

请参阅[元数据文件的命名约定](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)。

### 文件内容

在此示例中，文件内容反映了在事件调用中传入的创意和促销活动ID。 此处的新元素是一个可读的名称。 处理之后，此文件中的名称将在[!UICONTROL Audience Optimization]报表的Creative菜单中作为一个选项显示。

![元数据文件的内容](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

请参阅元数据文件的[内容格式](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md)。

### 文件交付

在命名数据并将其添加到文件后，将其发送到[!DNL Audience Manager]提供的Amazon S3存储目录。 请参阅元数据文件的[提交方法](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md)。

>[!MORELIKETHIS]
>
>* Audience Optimization报表的[数据文件](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [通过像素调用捕获营销活动点击数据](../../../integration/media-data-integration/click-data-pixels.md)
>* [通过像素调用捕获营销活动展示数据](../../../integration/media-data-integration/impression-data-pixels.md)
