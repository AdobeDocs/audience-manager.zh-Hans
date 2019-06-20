---
description: 目标登陆页面列出您的所有URL、cookie和服务器到服务器目标。它提供允许您创建、编辑、搜索和报告目标的功能。登陆页面位于“受众数据”>“目标”中。
seo-description: 目标登陆页面列出您的所有URL、cookie和服务器到服务器目标。它提供允许您创建、编辑、搜索和报告目标的功能。登陆页面位于“受众数据”>“目标”中。
seo-title: 管理目标
solution: Audience Manager
title: 管理目标
uuid: 6b66ff42-0075-49a7-a58 f-7f8 ea2295 fdc
translation-type: tm+mt
source-git-commit: 1d516c49a16c38adcc22827dc254da1ebada0734

---


# Manage Destinations {#manage-destinations}

[!UICONTROL Destination] 登陆页面列出您的所有 [!DNL URL]、cookie和服务器到服务器目标。它提供允许您创建、编辑、搜索和报告目标的功能。The landing page is located in **[!UICONTROL Audience Data > Destinations]**.

## Default Landing Page {#default-landing-page}

<!-- destinations-home.xml -->

默认登陆页面会根据类型列出目标。您可以使用四个可用的选项卡过滤目标：

* **** 全部：显示所有类型的目标。
* **Adobe Experience Cloud**：显示将数据发送到其他Adobe Experience Cloud解决方案的目标。目前，唯一支持的选项是Adobe Analytics。See [Configure an Analytics Destination](/help/using/features/destinations/create-analytics-destination.md).
* **集成平台**：显示基于用户的和基于设备的目标(也称为服务器到服务器目标)。请注意，基于人员的目标目前仅对选定客户提供测试功能。
* **自定义**：显示cookie和URL目标。


![](assets/destinations-landing.png)

## Addressable Audiences Landing Page {#audiences-landing-page}

To see audience data and match rates for your server-to-server destination, select **[!UICONTROL Integrated Platforms > Device-Based]**.

For more information about the displayed information, see [Addressable Audiences Interface](/help/using/features/addressable-audiences.md#addressable-audience-interface).

![](/help/using/features/assets/addressable-audiences-landing.png)

## Destination Builder {#destination-builder}

[!UICONTROL Destination Builder] 允许您创建基于cookie的或 [!DNL URL] 目标。You cannot create server-to-server ([!DNL S2S]) destinations with [!UICONTROL Destination Builder], but you can manage their segment mappings. Contact your consultant to set up a [!DNL S2S] destination. [!UICONTROL Destination Builder]**[!UICONTROL Audience Data > Destinations]** 所处位置。

### Destination Builder Settings {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 包括以下部分和设置：

| [!UICONTROL Destination Builder] 区域 | 用途 |
|--- |--- |
| 基本信息 | Used to name the destination, describe it, and select destination type ([!DNL URL] or [!DNL cookie]), and platform (all, [!DNL Android], browser, or [!DNL iOS]). |
| 配置 | Includes controls for: <br/><ul><li>Passing in key-value data to [!DNL URL] destinations. 您可以将数据作为单独的或序列化的键值对发送。For details see, [Destination Serialization](../../features/destinations/key-value-pairs.md#destination-serialized) and [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md). </li><li>Cookie目标的元素，如cookie名称、域、大小、到期时间间隔、数据格式等。</li></ul> |
| 细分映射 | 允许您: <br/><ul><li>搜索、添加和管理与所有目标类型关联的区段。 </li><li>Set delivery priorities on individual segments (for [!DNL cookie]-based segments only).</li></ul> |

### Data Delivery Methods {#data-delivery-methods}

Send information to a destination by passing it in through a [!DNL URL] string, by writing to a browser [!DNL cookie], or through offline server-to-server data transfers.

* [!DNL URL] 和基于cookie的目标以同步方式传输数据，当用户在页面上采取行动时。
* 服务器到服务器数据传输是异步的，在用户离开页面后可能很长一段时间。您选择的交付类型取决于您的业务需求以及特定数据合作伙伴想要或可以接收数据的方式。

See [How to Choose a Destination Type](../../features/destinations/destinations.md) for more information.

>[!MORE_ LIKE_ This]
>
>* [创建Cookie目标](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [创建URL目标](../../features/destinations/manage-destinations.md#configure-url-destination)


## Configure a Cookie Destination {#create-cookie-destination}

Cookie目标返回数据并将数据写入用户浏览器中的cookie。cookie包含可由有权访问页面的其他平台读取的数据。Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

To create a new cookie destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

### 基本信息 {#basic-information}

此部分包含启动cookie目标创建过程的字段和选项。要完成本节，请执行以下操作：

1. Click **[!UICONTROL Basic Information]** to expose the controls.
2. 命名目标。避免缩写和特殊字符。
3. *(可选)* 描述目标。简明描述是定义或提供目标的更多信息的有效方法。
4. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
5. In the **[!UICONTROL Environment]** list, select **[!UICONTROL Browser]**. 无法为原生移动环境(如Android或iOS应用程序)配置cookie目标。
6. In the **[!UICONTROL Type]** list, click **[!UICONTROL Cookie]**.
7. *(可选)* 选择一个 **[!UICONTROL Auto-fill Destination Mapping]**。选项包括：
   * **[!UICONTROL Segment ID]**：自动添加区段ID并将其发送到目标。
   * **[!UICONTROL Integration Code Value]**：自动添加区段集成代码并将其发送到目标映射。集成代码是客户创建和使用的唯一标识符。长度限制为255个字符，最大。
8. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

### Data Export Labels {#data-export-labels-cookies}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a cookie destination. 如果您不使用数据导出控件，请跳过此步骤。要完成本节，请执行以下操作：

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. 单击 **[!UICONTROL Save]**.

### 配置 {#configuration}

此部分包含允许您为目标设置Cookie的字段和选项。

>[!NOTE]
>
>[!DNL Audience Manager] 对写入目标cookie的数据进行编码。For example, spaces are encoded as `%20` and semicolons are encoded as `%3B`.

要完成本节，请执行以下操作：

1. Click **[!UICONTROL Configuration]** to expose the controls
1. 命名cookie。避免缩写和特殊字符。
1. 选择数据格式选项。这些选项允许您为将区段数据发送到目标的键值对选择分隔符和分隔符。格式选项包括：
   * **单键：** 允许您在键值对中设置键。You&#39;ll set the value after you select a segment in the [!UICONTROL Segment Mappings] section below.
   * **多键：** 允许您设置键值对的键和值。在下面的“区段映射”部分选择区段之后，您将创建键值对。
See [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md) for more information about these data elements.
1. 单击 **[!UICONTROL Save]**.

所有其他设置均为可选设置。For more information about the **[!UICONTROL Cookie Domain]** and **[!UICONTROL Publish data to]** settings, see [Optional Settings for Cookie Destinations](../../features/destinations/manage-destinations.md#optional-settings-cookies).

### Segment Mappings {#segments-mapping}

此部分允许您搜索区段并将其添加到目标位置。要完成本节，请执行以下操作：

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. **[!UICONTROL Search and Add Segments]** 在框中，开始键入区段名称或单击 **[!UICONTROL Browse All Segments]** 以浏览可用区段列表。
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. In the [!UICONTROL Edit Mapping] dialog:
   * **[!UICONTROL Mapping]** 允许您为以上“配置”部分中指定的键设置值。
   * **[!UICONTROL Publish from]** 允许您设置目标的开始日期和结束日期。如果结束日期为空，则目标永不过期。
1. 单击 **[!UICONTROL Save]**.
1. 单击 **[!UICONTROL Done]**.

## Configure a URL Destination {#configure-url-destination}

[!DNL URL] 目标会向目标页面发出像素调用。Follow these instructions to create a [!DNL URL] destination with [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

To create a new [!DNL URL] destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

### 基本信息 {#basic-info}

此部分包含启动URL目标创建过程的字段和选项。要完成本节，请执行以下操作：

1. Click **[!UICONTROL Basic Information]** to expose the controls.
1. 命名目标。避免缩写和特殊字符。
1. *(可选)* 描述目标。简明描述是定义或提供目标的更多信息的有效方法。
1. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
1. In the **[!UICONTROL Environment]** list, select the environment in which to trigger the URL destination.
1. In the **[!UICONTROL Type]** list, click **[!UICONTROL URL]**.
1. *(可选)* 选择一个 **[!UICONTROL Auto-fill Destination Mapping]**。选项包括：
   * **[!UICONTROL Segment ID]**：自动添加区段ID并将其发送到目标。
   * **[!UICONTROL Integration Code Value]**：自动添加区段集成代码并将其发送到目标映射。集成代码是客户创建和使用的唯一标识符。长度限制为255个字符，最大。
1. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

### Data Export Labels {#data-export-labels-dest}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a [!DNL URL] destination. 如果您不使用数据导出控件，请跳过此步骤。要完成本节，请执行以下操作：

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. 单击 **[!UICONTROL Save]**.

### 配置 {#configure-base-data}

This section contains options that let you set a base [!DNL URL] and data delimiters passed in by the [!DNL URL] string. 此部分为可选部分。要完成本节，请执行以下操作：

1. Click **[!UICONTROL Configuration]** to expose the controls.
1. *(可选)* 选中复选 **[!UICONTROL Serialize]** 框。
这允许您按顺序将区段发送到目标，而不是为每个区段单独发送调用。序列化有助于提高数据传输效率。选中此复选框可显示URL和分隔符字段。For more information, see [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md).
1. If you select **[!UICONTROL Serialize]**, then you must also configure the URL and delimiter fields described below.

| 字段 | 描述 |
|--- |--- |
| 基本 URL | The base part of a standard `HTTP` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`  [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. 示例: `https://www.myCompany.com/%alias%...` |
| 安全URL | The base part of a secure `HTTPS` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`   [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. 示例: `https://www.myCompany.com/%alias%...` |
| Delimiter（分隔符） | The symbol that separates the segment variables in the [!DNL URL] string. 这通常是逗号或分号。从目标合作伙伴处获取此信息。 |

### Segment Mappings {#segment-mappings}

此部分允许您搜索区段并将其添加到目标位置。要完成本节，请执行以下操作：

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. **[!UICONTROL Search and Add Segments]** 在框中，开始键入区段名称或单击 **[!UICONTROL Browse All Segments]** 浏览可用区段列表。
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. 在 [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**：提供区段使用的键值对。
   * **[!UICONTROL Start Date]** 以及 **[!UICONTROL End Date]**：选择目标的开始日期和结束日期。如果结束日期为空，则目标永不过期。
1. 单击 **[!UICONTROL Done]**.

### Optional Settings for Cookie Destinations {#optional-settings-cookies}

In [!UICONTROL Destination Builder], the [!UICONTROL Configuration section] contains the [!UICONTROL Cookie Domain] and [!UICONTROL Publish Data To] fields. 这些规则允许您创建规则以确定目标设置cookie还是返回cookie。[!UICONTROL Cookie Domain] 独立 [!UICONTROL Publish Data To] 工作，并且是可选的。您可以创建cookie目标，而无需使用其中任何一个。

## Cookie Domain: Syntax and Examples {#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cookie 域 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>语法</b> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Cookie域</span> 字段接受一个简单的文本字符串，它允许您在指定的域或所有域上设置cookie。使用此功能时： </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">仅为每个cookie目标设置一个域。Do not type multiple domains in the <span class="wintitle"> Cookie Domain</span> field. Create another <span class="wintitle"> Destination</span> instead. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">请勿使用通配符字符。 </li> 
     </ul> </p> <p> Leave the <span class="wintitle"> Cookie Domain</span> field blank to set a cookie on all domains. 这是默认设置。 </p> <p>要在特定域和子域上设置cookie，请执行以下操作： </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Type the name of the domain in the <span class="wintitle"> Cookie Domain</span> field. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">用句点启动域名。For example, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>示例</b> </p> </td> 
   <td colname="col2"> <p>例如，假设我们有一个名为sports. com的虚构网站。Sports.com有用于高尔夫、棒球和足球的域。To set a cookie in all the sports domains, you would type that in the <span class="wintitle"> Cookie Domain</span> box as shown below: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>This tells <span class="keyword"> Audience Manager</span> to set a cookie in any domain that contains the pattern <code><i>something</i></code>.sports.com. 请参阅下面的更复杂的示例。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 复杂Cookie域示例

These examples show you if [!DNL Audience Manager] will set a cookie based on how the [!UICONTROL Cookie Domain] option is configured.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 网站 </th> 
   <th colname="col2" class="entry">Cookie域：.sports.com <p>Cookie集 </p> </th> 
   <th colname="col3" class="entry">Cookie域：.golf.sports.com <p>Cookie集 </p> </th> 
   <th colname="col4" class="entry">Cookie域：Blank <p>Cookie集 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sports.com</b> </p> </td> 
   <td colname="col2"> 是 </td> 
   <td colname="col3"> 否 </td> 
   <td colname="col4"> 是 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sports.com</b> </p> </td> 
   <td colname="col2"> 是 </td> 
   <td colname="col3"> 是 </td> 
   <td colname="col4"> 是 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sports.com</b> </p> </td> 
   <td colname="col2"> 是 </td> 
   <td colname="col3"> 否 </td> 
   <td colname="col4"> 是 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sports.golf.com</b> </p> </td> 
   <td colname="col2"> 否 </td> 
   <td colname="col3"> 否 </td> 
   <td colname="col4"> 是 </td> 
  </tr> 
 </tbody> 
</table>

## Publish Data To {#publish-data-to}

[!UICONTROL Publish Data To] 如果域符合您选择的选项设置的条件，则设置会返回cookie。选项包括：

* **[!UICONTROL All of our domains]**：(默认)返回任何域的一个 [!DNL cookie] 。
* **[!UICONTROL Only the selected domains]**：仅返回在域列表中选择的域的cookie。
* **[!UICONTROL All of our domains except the selected domains]**：阻止选定域接收 [!DNL cookie]。All other domains can receive a [!DNL cookie].

>[!MORE_ LIKE_ This]
>
>* [创建Cookie目标](../../features/destinations/manage-destinations.md#create-cookie-destination)


## Add or Edit Segments for Server-to-Server Destinations {#add-edit-segments}

You can only add or edit segments for a server-to-server ([!DNL S2S]) destination. You cannot create [!DNL S2S] destinations with [!UICONTROL Destination Builder]. Contact your consultant to set up [!DNL S2S] destinations. Follow these instructions to add or edit segments for an [!DNL S2S] destination.

<!-- destination-s2s-edit.xml -->

To add or edit segment mappings for an [!DNL S2S] destination:

1. **[!UICONTROL Audience Data > Destinations]** 转至。Select **Integrated Platforms &gt; Device-Based** and find the [!DNL S2S] destination you want to work with.
1. In the [!UICONTROL Action] column, click the pencil icon to edit the destination.
   * **[!UICONTROL Search and Add Segments]** 在框中，开始键入区段名称或单击 **[!UICONTROL Browse All Segments]** 浏览可用区段列表。
   * Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
   * 在 [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**：为此目标使用的 [键值对](../../features/destinations/key-value-pairs.md) 设置值。
      * **[!UICONTROL Start Date]** 以及 **[!UICONTROL End Date]**：选择目标的开始日期和结束日期。如果结束日期为空，则目标永不过期。
1. Click **[!UICONTROL Save]** and then click **[!UICONTROL Done]**.

## Add Data Export Labels to a Destination {#add-data-export-labels}

[!DNL Data Export Labels] 使用在数据 [!DNL Export Controls] 源上设置的内容。[!DNL Data Export Labels] 防止您向区段添加受限特征，并将区段数据发送到目标。You can set multiple export labels to a new or existing [!DNL cookie] or [!DNL URL] destination.

>[!NOTE]
>
>To add an export label, you need administrator permissions *or* sufficient privileges to create or edit a destination.

<!-- t_export_labels.xml -->

要向目标中添加导出标签，请执行以下操作：

1. 单击 **[!UICONTROL Audience Data]**:
   * For new destinations: Click **[!UICONTROL Create New Destination]**. Complete the [!UICONTROL Basic Information] section before you select a data export label. See [Create a Cookie Destination](../../features/destinations/manage-destinations.md#create-cookie-destination) or [Create a URL Destination](../../features/destinations/manage-destinations.md#configure-url-destination) for information.
   * For existing destinations: Use the [!DNL Search] box to find your destination or scroll through the list and click on the destination name to open it.
1. 选择 [!DNL Data Export Label]. 如果不希望设置任何导出限制，请将复选框保留为空。导出标签包括以下选项：
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Export restrictions will not work unless you set a [matching export control](../../features/data-export-controls.md) on a data source.
1. 单击 **[!UICONTROL Save]**.

>[!MORE_ LIKE_ This]
>
>* [创建数据源](../../features/manage-datasources.md#create-data-source)

