---
description: 元数据文件链接数字ID，并且您可以阅读和理解名称。受众优化报告可在各种报告选项菜单中显示可读名称。
seo-description: 元数据文件链接数字ID，并且您可以阅读和理解名称。受众优化报告可在各种报告选项菜单中显示可读名称。
seo-title: 元数据文件概述和映射
solution: Audience Manager
title: 元数据文件概述和映射
uuid: 70df7f11-69c5-4873-a69 d-8f93 f94 e9837
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Overview and Mappings for Metadata Files{#overview-and-mappings-for-metadata-files}

元数据文件链接数字ID，并且您可以阅读和理解名称。受众优化报告可在各种报告选项菜单中显示可读名称。

## 概述 {#overview}

对元数据及其使用方式的检查。元数据文件必须附带一个数据文件。元数据文件内容将数据文件信息与报告菜单中相关、人工可读标签相匹配。For more information, see [Data Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### 元数据文件包含有关其他数据的数据

元数据文件包含有关其他类型数据的信息。To help you understand how this works, let’s review how [!DNL Audience Manager] receives data.

During an impression or click event, [!DNL Audience Manager] receives data in an URL string known as an *event call*.

事件调用将信息组织到定义的键值对组中。键值对中的值包含数字数据。元数据文件包含与每个键值对中的ID对应的名称和其他可读信息。

### 元数据链接ID到可读名称

需要该元数据文件才能将数字ID绑定到可读名称。As an example, say an event call contains a creative ID in a key-value pair like this: `d_creative:1234`. 如果没有元数据文件，此创意功能将在选项菜单中显示为1234。

但是，格式正确的元数据文件可以将此创意绑定到真实名称，如“广告商创意A”，这是您可以在报告中阅读和识别的名称。

### 何时需要元数据文件

First, a metadata file, and all of the parameters listed below, are required in an event call when you want to use the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

Second, you need a metadata file if you’re sending your own data to [!DNL Audience Manager] or if you want to see data in the reports from other providers we’re not integrated with. For example, [!DNL Audience Manager] has an integration with Google’s [Double-click Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM). Because of this relationship, [!DNL Audience Manager] can associate IDs with names and descriptions used by the report options. 如果没有集成，我们仍可以摄取数据，但报告选项将显示数字ID而不是描述性名称。

![](assets/metadata_menu.png)

## File Mappings {#file-mappings}

The following table lists the key-value pairs that hold data used by the [!UICONTROL Audience Optimization] reports. 如果需要使用元数据文件，它将包含与这些键值对中的值对应的可读信息。这些键的值仅接受整数(数据类型INT)。Note, *italics* indicates a variable placeholder. 其他元素是常量或密钥，不会更改。

>[!IMPORTANT]
>
>If you&#39;re using the [!UICONTROL Audience Optimization] reports, *all* of these values are required in the event call.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 报告选项 </th> 
   <th colname="col2" class="entry"> 元数据密钥值对 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>广告商 </p> </td> 
   <td colname="col2"> <p> <code>d_ adsrc= <i>data源ID或集成代码</i></code> </p> <p>这是广告商在创建数据源时提供的数据源ID或集成代码。See <a href="../../../features/manage-datasources.md#create-data-source"> Create a Data Source</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>事业部(BU) </p> </td> 
   <td colname="col2"> <p> <code>d_ bu= <i>业务单位ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>促销活动 </p> </td> 
   <td colname="col2"> <p> <code>d_ campaign= <i>系列活动ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative </p> </td> 
   <td colname="col2"> <p> <code>d_ creative= <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>接受个不同的键值对： </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_ change= <i>提供广告的交换的ID</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_ site= <i>用于在站点上投放广告的ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>插入顺序(IO) </p> </td> 
   <td colname="col2"> <p> <code>d_ io= <i>插入顺序ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>平台 </p> </td> 
   <td colname="col2"> <p> <code>d_ src= <i>数据源ID</i></code> </p> <p>This is the <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> data source</a> ID for the platform providing metadata information (e.g., DFA, Atlas, GBM, MediaMath, etc.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic </p> </td> 
   <td colname="col2"> <p> <code>d_ actacic= <i>tatic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>垂直 </p> </td> 
   <td colname="col2"> <p> <code>d_ vert= <i>垂直ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## How Event Call IDs Shape File Names, Contents, and Delivery Paths {#how-ids-shape-file-names}

这些键值对传入的ID有助于创建元数据文件名及其内容。以下部分和插图说明了这一点的用法。这些示例构建了一个包含营销活动中的创意名称的文件，但其他组合是可能的。

### 活动电话

In this example we&#39;ll create a metadata file that brings creative names in to an [!UICONTROL Audience Optimization] report. 为此，我们需要从活动调用中提取创意、营销活动和数据源ID。

![](assets/metadata_file_event.png)

### 文件名

文件名基于创意、营销活动和数据源ID。在这种情况下，请比较事件调用中的键值数据之间的差异以及文件名称中的使用方式。

在文件名中：

* The data source key changes to `dpid` from `d_src`.

* 创意和系列活动ID代表一个类别，而不是实际标识符。

![](assets/metadata_file_name.png)

See [Naming Conventions for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### 文件内容

在此示例中，文件内容反映了活动调用中传入的创意和系列活动ID。此处的新元素为可读名称。Once processed, the name in this file will appear as an option in the Creative menu of an [!UICONTROL Audience Optimization] report.

![](assets/metadata_file_contents.png)

See [Content Format for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### 文件交付

After you name and add data to a file, you send it to an Amazon S3 storage directory provided by [!DNL Audience Manager]. See [Delivery Methods for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md) and [Status Updates for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md).

>[!MORE_ LIKE_ This]
>
>* [用于受众优化报告的数据文件](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [通过像素调用捕获Campaign单击数据](../../../integration/media-data-integration/click-data-pixels.md)
>* [通过像素调用捕获营销活动展示数据](../../../integration/media-data-integration/impression-data-pixels.md)

