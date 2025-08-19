---
description: 介绍如何使用区段生成器创建区段。
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: 区段生成器
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 2%

---

# [!UICONTROL Segment Builder] {#segment-builder}

描述在[!UICONTROL Segment Builder]中创建区段的必需步骤和可选步骤。

## 视频演示

首先观看[在Audience Manager中创建区段视频](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)。 该视频将指导您完成区段创建过程。 有关详细信息，请阅读以下部分。

## 创建[!UICONTROL Segment] {#create-segment}

### 区段生成器部分

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder]包含3个不同的部分：[!UICONTROL Basic Information]、[!UICONTROL Traits]和[!UICONTROL Destinations Mapping]。 要创建[!UICONTROL segment]，请完成[!UICONTROL Basic Information]和[!UICONTROL Traits]部分中的必填字段。 [!UICONTROL Destinations Mapping]设置是可选的。 有关其他帮助，请参阅下面的说明。

1. 在[基本信息](../../features/segments/segment-builder.md#segment-builder-controls-basics)部分中：

   ![create-segment](assets/create-segment.png)

   * 为[!UICONTROL segment]命名。 [!UICONTROL segment]名称的最大长度为255个字符。
   * 设置[!UICONTROL segment]状态（默认为“活动”）。
   * 选择[!UICONTROL data source]。 使用第一个下拉菜单在Audience Manager [!UICONTROL data sources]、Adobe Analytics报表包或两者之间筛选。 然后，使用第二个下拉菜单选择您的[!UICONTROL data source]。 如果您未使用Adobe Analytics报表包，则[!UICONTROL data source]类型选择器已禁用，并且仅默认为Audience Manager数据源。
   * 选择要用于[!UICONTROL profile merge rule]资格的[!UICONTROL segment]。
   * 将[!UICONTROL segment]分配到存储文件夹。

1. 在[特征](../../features/segments/segment-builder.md#segment-builder-controls-traits)部分中：
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * 搜索要添加到区段的[!UICONTROL trait]，然后单击&#x200B;**[!UICONTROL Add Trait]**。 添加其他[!UICONTROL trait]以创建[!UICONTROL trait]组。
   * 通过单击[!UICONTROL Advanced Search]打开&#x200B;**[!UICONTROL Browse All Traits]**&#x200B;模式窗口。 按名称、ID、说明或[!UICONTROL traits]搜索[!UICONTROL data source]。 搜索时单击某个文件夹，将结果限制为该文件夹及其子文件夹。 您还可以按[!UICONTROL traits] （[!UICONTROL trait type]、[!UICONTROL Folder Trait]、[!UICONTROL Rule-based]和[!UICONTROL Onboarded]）或填充类型（[!UICONTROL Algorithmic]设备ID[和](../../reference/ids-in-aam.md)跨设备ID[）筛选](../../reference/ids-in-aam.md)。
     ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * 在构建[时实时获取](trait-recommendations.md)特征推荐[!UICONTROL segment]。
   * 单击并拖动[!UICONTROL traits]以创建单独的组。
   * 在组之间悬停以设置与布尔值[!UICONTROL AND]、[!UICONTROL OR]、[!UICONTROL AND NOT]的关系。
   * 将鼠标悬停在时钟图标上以将[回访间隔和频率](../../features/segments/recency-and-frequency.md)规则添加到[!UICONTROL trait]。
   * 在添加或删除[!UICONTROL traits]时查看区段填充数据。 单击&#x200B;**[!UICONTROL Calculate Estimates]**&#x200B;查看（或刷新）预计的群体数量。 详细了解[中的](../../features/segments/segment-builder-data.md#segment-populations)区段人口数据[!UICONTROL Segment Builder]。
   * 完成后单击&#x200B;**[!UICONTROL Save]**。

1. *（可选）*&#x200B;将[!UICONTROL segment]映射到[!UICONTROL destination]目标映射[部分中的](../../features/segments/segment-builder.md#segment-builder-controls-destinations)：
   * 搜索[!UICONTROL destination]并单击&#x200B;**[!UICONTROL Add Destination]**。 请注意，必须先存在[!UICONTROL destination]，然后才能将其添加到[!UICONTROL segment]。
   * 完成后单击&#x200B;**[!UICONTROL Save]**。

请观看以下视频，详细了解跨设备量度的工作方式。

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder]控件：[!UICONTROL Basic Information]节 {#segment-builder-controls-basics}

在[!UICONTROL Segment Builder]中，[!UICONTROL the Basic Information]设置允许您创建新特征或编辑现有特征。 要创建新[!UICONTROL segment]，请提供名称、[!UICONTROL data source]并选择存储文件夹。 所有其他字段都是可选的。 完成后转到[!UICONTROL Traits]部分。

<!-- r_segment_basic_info_section.xml -->

<!--

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Name</b> </td> 
   <td colname="col2"> <p>Give the segment a short, logical name that describes its function or purpose. Avoid abbreviations and special characters. The maximum length of a segment name is 255 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>A field for additional descriptive information about the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integration Code</b> </td> 
   <td colname="col2"> <p>A field for a user-defined ID or other company-specific information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <p>Associates the segment with a specific data provider. <p>Use the first drop-down menu to filter between Audience Manager data sources, Adobe Analytics report suites, or both. Then, use the second drop-down menu to choose your data source.</p><p> If you are not using Adobe Analytics report suites, the data source type selector is disabled and defaulted to Audience Manager data sources only.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Profile Merge Rule</b> </td> 
   <td colname="col2"> <p>Selects the Profile Merge Rule to use for segment qualification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Activates or deactivates the segment (active by default). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Folder Storage</b> </td> 
   <td colname="col2"> <p>Determines which storage folder the segment belongs to. </p> </td> 
  </tr> 
 </tbody> 
</table>

-->

| 字段 | 描述 |
---------|----------
| **[!UICONTROL Name]** | 为区段提供一个简短逻辑名称，用于描述其功能或用途。 避免使用缩写和特殊字符。 区段名称的最大长度为255个字符。 |
| **[!UICONTROL Description]** | 有关区段的其他说明性信息的字段。 |
| **[!UICONTROL Integration Code]** | 用户定义的ID或其他特定于公司的信息的字段。 |
| **[!UICONTROL Data Source]** | 将区段与特定数据提供商关联。 <br>使用第一个下拉菜单在Audience Manager数据源、Adobe Analytics报表包或两者之间筛选。 然后，使用第二个下拉菜单选择数据源。 <br>如果您未使用Adobe Analytics报表包，则数据源类型选择器处于禁用状态，并且仅默认为Audience Manager数据源。 |
| **[!UICONTROL Profile Merge Rule]** | 选择用于区段鉴别的配置文件合并规则。 |
| **[!UICONTROL Status]** | 激活或停用区段（默认处于活动状态）。 |
| **文件夹存储** | 确定区段属于哪个存储文件夹。 |

## [!UICONTROL Segment Builder]控件：[!UICONTROL Traits]节 {#segment-builder-controls-traits}

在[!UICONTROL Segment Builder]中，[!UICONTROL Traits]部分允许您在[!UICONTROL traits]中管理[!UICONTROL segment]、创建[!UICONTROL trait]组并设置资格条件。 要将[!UICONTROL trait]添加到[!UICONTROL segment]，请在搜索字段中键入[!UICONTROL trait]名称，然后单击[!UICONTROL Add Trait]。 保存[!UICONTROL trait]（如果完成）或移至[!UICONTROL Destinations Mapping]。

<!-- r_segment_traits_section.xml-->

**先决条件：**&#x200B;完成[!UICONTROL Basic Information]部分中的必填字段。

| 字段 | 描述 |
|--- |--- |
| **[!UICONTROL Basic View]** | 此部分提供了可视控件，这些控件允许您： <ul><li>生成新的和管理现有的[!UICONTROL segments]。</li><li>从[!UICONTROL traits]中删除[!UICONTROL segment]。</li><li>将最多50个（最大） [!UICONTROL traits]添加到[!UICONTROL segment]。</li><li>拖放[!UICONTROL traits]以创建新组。</li><li>在[!UICONTROL traits]中查看[!UICONTROL trait]和[!UICONTROL segment]组。</li><li>使用布尔表达式、比较运算符和回访间隔/频率设置设置资格标准。</li></ul> |
| **[!UICONTROL Code View]** | 打开一个开发环境，允许您使用代码而不是可视化界面创建和管理[!UICONTROL traits]、组和资格要求。 如果您的[!UICONTROL segments]： <ul><li>单个[!UICONTROL traits]中的[!UICONTROL segment]超过50个。 注意： [!UICONTROL Segments]限制为5000 [!UICONTROL traits]（最大值）。</li><li>包含多个[!UICONTROL trait]组。</li><li>具有复杂的资格要求。</li></ul> |
| 搜索 | 帮助您找到要添加到[!UICONTROL traits]的[!UICONTROL segment]。 |
| 推荐 | 从您订阅的第一方[!UICONTROL traits]和[!UICONTROL traits]数据馈送中获取类似[!UICONTROL Audience Marketplace]的实时推荐。 将这些推荐添加到[!UICONTROL segment]规则以扩展您的受众。 请参阅[特征推荐](trait-recommendations.md)以了解详情。 |
| **[!UICONTROL Marketplace Recommendations]** | 从您未订阅的[!UICONTROL traits]数据馈送获取类似[!UICONTROL Audience Marketplace]的实时推荐。 请参阅[特征推荐](trait-recommendations.md)以了解详情。 |
| 实际和预计[!UICONTROL Segment]大小数据 | 请参阅[区段生成器中的特征和区段人口数据](segment-builder-data.md)。 |

## 从[!UICONTROL Traits]中删除[!UICONTROL Segment] {#remove-traits}

管理[!UICONTROL traits]中的[!UICONTROL segments]是保持[!UICONTROL segments]可行性的重要部分。 如果需要从[!UICONTROL traits]中移除[!UICONTROL segment]，请按照以下步骤操作。

要从[!UICONTROL traits]中删除[!UICONTROL segment]，请执行以下操作：

1. 转到&#x200B;**[!UICONTROL Audience Data > Segments]**。 滚动列表或使用搜索功能查找要处理的[!UICONTROL segment]。
2. 单击[!UICONTROL segment]名称以打开[!UICONTROL segment]详细信息屏幕。
3. 单击&#x200B;**编辑**&#x200B;以打开[!UICONTROL Segment Builder]，然后单击&#x200B;**特征**&#x200B;以打开[!UICONTROL traits]面板。
4. 将鼠标悬停在要删除的[!UICONTROL trait]上，然后单击X。此操作会立即从您的[!UICONTROL trait]中删除[!UICONTROL segment]。

## [!UICONTROL Segment Builder]控件：[!UICONTROL Destinations Mappings]节 {#segment-builder-controls-destinations}

在[!UICONTROL Segment Builder]中，可选的[!UICONTROL Destinations Mapping]部分允许您将[!UICONTROL segment]数据发送给第三方[!DNL cookie]、[!DNL URL]或[!UICONTROL server-to-server destination]。 要添加[!UICONTROL destination]，请搜索（或浏览）[!UICONTROL destination]，提供[!UICONTROL destination]特定信息，然后单击&#x200B;**[!UICONTROL Add Destination]**。

<!-- r_segment_destinations_map.xml -->

### 先决条件

完成[!UICONTROL Basic Information]和[!UICONTROL Traits]部分中的必填字段。 此外，目标必须已存在。

### [!UICONTROL Destination Mappings]搜索工具

**[!UICONTROL Destination Mappings]**&#x200B;面板包含下表所述的搜索工具。

| 搜索类型 | 描述 |
|---|---|
| **[!UICONTROL Search by Destination Name]** | 允许您按名称搜索特定[!UICONTROL destination]。 要搜索，请开始键入。 该字段将根据您的搜索词自动完成。 完成后单击&#x200B;**[!UICONTROL Add Destination]**。 |
| **[!UICONTROL Browse All Destinations]** | 浏览可供您使用的&#x200B;*所有* [!UICONTROL destinations]的列表。 从弹出列表中选择[!UICONTROL destinations]并将其添加到您的[!UICONTROL segment]。 |

## [!UICONTROL Destination Mappings]弹出窗口中的字段 {#fields-in-dest-mappings}

在[!UICONTROL Segment Builder]中，选择[!UICONTROL Add Destination]后将显示[!UICONTROL destination]对话框。 此窗口显示有关[!UICONTROL destination]的静态信息以及根据[!UICONTROL destination]类型而变化的字段。 在空字段中提供设置[!UICONTROL destination mapping]所需的信息。

>[!NOTE]
>
>发布日期是可选的。 当为空时，目标将变为活动状态且永不过期。

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination]字段

在[!UICONTROL Destination Mapping]字段中，指定用于将数据发送到[!UICONTROL destination]的键值对。 在第一个字段中输入键，在第二个字段中输入值。 您的[!UICONTROL cookie destination] pop可能类似于以下内容：

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination]字段

在[!UICONTROL URL]和[!UICONTROL Secure URL]字段中，指定用于向[!UICONTROL destination]发送数据的完整标准或安全地址。

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination]字段

在[!UICONTROL Destination Value]字段中，指定用于向[!UICONTROL destination]发送数据的值（键值对的一部分）。

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [创建Cookie目标](../../features/destinations/create-cookie-destination.md)
>* [创建URL目标](../../features/destinations/create-url-destination.md)
