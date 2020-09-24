---
description: 介绍如何使用区段生成器创建区段。
seo-description: 介绍如何使用区段生成器创建区段。
seo-title: 区段生成器
solution: Audience Manager
title: 区段生成器
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
translation-type: tm+mt
source-git-commit: 4bf32099e964c421d943d9925c74dd0d4d6ee576
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 2%

---


# [!UICONTROL Segment Builder] {#segment-builder}

介绍在中创建区段的必需和可选步骤 [!UICONTROL Segment Builder]。

## 视频演示

开始，观看“在 [Audience Manager中创建区段”视频](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)。 该视频将引导您完成区段创建过程。 请阅读以下各节以了解更多信息。

## 创建一个 [!UICONTROL Segment] {#create-segment}

### 区段生成器部分

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 由3个单独的部分组成： [!UICONTROL Basic Information]、 [!UICONTROL Traits]和 [!UICONTROL Destinations Mapping]。 要创建 [!UICONTROL segment]，请填写和部分中的必 [!UICONTROL Basic Information] 填 [!UICONTROL Traits] 字段。 [!UICONTROL Destinations Mapping] 设置为可选。 请参阅下面的说明以获取更多帮助。

1. 在“基 [本信息](../../features/segments/segment-builder.md#segment-builder-controls-basics) ”部分：

   ![创建细分](assets/create-segment.png)

   * 命名 [!UICONTROL segment]。 名称的最大长 [!UICONTROL segment] 度为255个字符。
   * 设置状 [!UICONTROL segment] 态（默认为“活动”）。
   * 选择 [!UICONTROL data source]。 使用第一个下拉菜单在Audience Manager、Adobe Analytics报 [!UICONTROL data sources]表包或两者之间进行筛选。 然后，使用第二个下拉菜单选择您的 [!UICONTROL data source]。 如果您没有使用Adobe Analytics报表包，则类型选 [!UICONTROL data source] 择器将被禁用，并且仅默认为Audience Manager数据源。
   * 选择要 [!UICONTROL profile merge rule] 用于资格 [!UICONTROL segment] 的。
   * 将其分 [!UICONTROL segment] 配到存储文件夹。

1. 在“特 [征](../../features/segments/segment-builder.md#segment-builder-controls-traits) ”部分：
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * 搜索要添加 [!UICONTROL trait] 到区段的对象，然后单击 **[!UICONTROL Add Trait]**。 添加其 [!UICONTROL trait] 他组以创 [!UICONTROL trait] 建组。
   * 单击以 [!UICONTROL Advanced Search] 调出模 **[!UICONTROL Browse All Traits]**&#x200B;态。 按名 [!UICONTROL traits] 称、ID、说明或搜索 [!UICONTROL data source]。 在搜索时单击某个文件夹可将结果限制在该文件夹及其子文件夹中。 您还可以通过( [!UICONTROL traits] 、、 [!UICONTROL trait type] 和)或[!UICONTROL Folder Trait]填充类型( [!UICONTROL Rule-based]ID设备ID和 [!UICONTROL Onboarded]设 [!UICONTROL Algorithmic][](../../reference/ids-in-aam.md)[](../../reference/ids-in-aam.md)备ID交叉)进行过滤。
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * 在构建 [时获取](trait-recommendations.md) 实时特征推荐 [!UICONTROL segment]。
   * 单击并拖 [!UICONTROL traits] 动以创建单独的组。
   * 在组之间悬停，以设置与布尔 [!UICONTROL AND]值、 [!UICONTROL OR]值的 [!UICONTROL AND NOT] 关系。
   * 将指针悬停在时钟图标上 [可向添加近期](../../features/segments/recency-and-frequency.md) 和频率规则 [!UICONTROL trait]。
   * 视图细分填充数据，添加或删除数据 [!UICONTROL traits]。 单击 **[!UICONTROL Calculate Estimates]** 查看（或刷新）估计的人口数。 在中阅读有 [关细分填充数据](../../features/segments/segment-builder-data.md#segment-populations) 的更多信 [!UICONTROL Segment Builder]息。
   * 完成 **[!UICONTROL Save]** 后单击。

1. *（可选）* 将映 [!UICONTROL segment] 射到“目 [!UICONTROL destination] 标映 [射”部分中](../../features/segments/segment-builder.md#segment-builder-controls-destinations) :
   * 搜索并 [!UICONTROL destination] 单击 **[!UICONTROL Add Destination]**。 请注意， [!UICONTROL destination] 必须先存在，才能将其添加到 [!UICONTROL segment]。
   * 完成 **[!UICONTROL Save]** 后单击。

观看以下视频，详细了解跨设备指标的工作方式。

>[!VIDEO](https://video.tv.adobe.com/v/33445/)

## [!UICONTROL Segment Builder] 控件： [!UICONTROL Basic Information] 章节 {#segment-builder-controls-basics}

在中 [!UICONTROL Segment Builder]，通 [!UICONTROL the Basic Information] 过设置可创建新特征或编辑现有特征。 要创建新文 [!UICONTROL segment]件，请提供名称、 [!UICONTROL data source]名称，然后选择存储文件夹。 所有其他字段都是可选字段。 完成后，移 [!UICONTROL Traits] 到该部分。

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
| **[!UICONTROL Name]** | 为区段提供一个简短的逻辑名称，用于描述其功能或用途。 避免缩写和特殊字符。 段名称的最大长度为255个字符。 |
| **[!UICONTROL Description]** | 有关区段的其他说明性信息的字段。 |
| **[!UICONTROL Integration Code]** | 用户定义ID或其他公司特定信息的字段。 |
| **[!UICONTROL Data Source]** | 将区段与特定数据提供者关联。 <br> 使用第一个下拉菜单在Audience Manager数据源、Adobe Analytics报表包或两者之间进行筛选。 然后，使用第二个下拉菜单选择数据源。 <br> 如果您未使用Adobe Analytics报表包，数据源类型选择器将被禁用，并且仅默认为Audience Manager数据源。 |
| **[!UICONTROL Profile Merge Rule]** | 选择用于区段资格的用户档案合并规则。 |
| **[!UICONTROL Status]** | 激活或取消激活区段（默认情况下处于活动状态）。 |
| **文件夹存储** | 确定区段所属的存储文件夹。 |

## [!UICONTROL Segment Builder] 控件： [!UICONTROL Traits] 章节 {#segment-builder-controls-traits}

在中 [!UICONTROL Segment Builder]，您 [!UICONTROL Traits] 可以通过该部分 [!UICONTROL traits] 管理、 [!UICONTROL segment]创建组 [!UICONTROL trait] 和设置资格标准。 要向中添 [!UICONTROL trait] 加名 [!UICONTROL segment]称，请在搜索 [!UICONTROL trait] 字段中键入名称并单击 [!UICONTROL Add Trait]。 保存( [!UICONTROL trait] 如果完成)或转到 [!UICONTROL Destinations Mapping]。

<!-- r_segment_traits_section.xml-->

**先决条件：** 填写部分中的必填 [!UICONTROL Basic Information] 字段。

| 字段 | 描述 |
|--- |--- |
| **[!UICONTROL Basic View]** | 此部分提供了可视控件，允许您： <ul><li>新建并管理现有 [!UICONTROL segments]。</li><li>从 [!UICONTROL traits] 中删除 [!UICONTROL segment]。</li><li>最多加上50(最 [!UICONTROL traits] 多) [!UICONTROL segment]。</li><li>拖放以 [!UICONTROL traits] 创建新组。</li><li>视图 [!UICONTROL traits] 和 [!UICONTROL trait] 组中的组 [!UICONTROL segment]。</li><li>使用布尔表达式、比较运算符和最近／频率设置设置资格标准。</li></ul> |
| **[!UICONTROL Code View]** | 打开一个开发环境，它允许您使用代 [!UICONTROL traits]码而不是可视界面创建和管理、组和资格要求。 代码视图在以下情况下很有用 [!UICONTROL segments]: <ul><li>包含50个以 [!UICONTROL traits] 上的个人 [!UICONTROL segment]。 注意： [!UICONTROL Segments] 限制为5000( [!UICONTROL traits] 最大)。</li><li>包含多 [!UICONTROL trait] 个组。</li><li>具有复杂的资格要求。</li></ul> |
| 搜索 | 帮助您 [!UICONTROL traits] 查找添加到 [!UICONTROL segment]。 |
| 推荐 | 从您订阅的第 [!UICONTROL traits]一方和数据 [!UICONTROL traits] 源 [!UICONTROL Audience Marketplace] 中获取类似的实时建议。 将这些建议添加到 [!UICONTROL segment] 规则以扩展您的受众。 阅读特质Recommendations [的更多信息](trait-recommendations.md)。 |
| **[!UICONTROL Marketplace Recommendations]** | 从您未订阅的 [!UICONTROL traits]数据 [!UICONTROL Audience Marketplace] 源中获取类似的实时推荐。 阅读特质Recommendations [的更多信息](trait-recommendations.md)。 |
| 实数和估计 [!UICONTROL Segment] 大小数据 | 请参阅[区段生成器中的特征和区段人口数据](segment-builder-data.md)。 |

## 从 [!UICONTROL Traits] [!UICONTROL Segment] {#remove-traits}

管理您 [!UICONTROL traits] 的内 [!UICONTROL segments] 容是保持可行性的重要 [!UICONTROL segments] 部分。 如果需要从中删除，请 [!UICONTROL traits] 按照以下步骤 [!UICONTROL segment]操作。

从中删除 [!UICONTROL traits] 的步骤 [!UICONTROL segment]:

1. 转到 **[!UICONTROL Audience Data > Segments]**。 滚动浏览列表或使用搜索功能 [!UICONTROL segment] 找到要处理的内容。
2. 单击该 [!UICONTROL segment] 名称以打开详细 [!UICONTROL segment] 信息屏幕。
3. 单击 **编辑** 以打开 [!UICONTROL Segment Builder] ，然后单 **击特** 征 [!UICONTROL traits] 以打开面板。
4. 将鼠标悬 [!UICONTROL trait] 停在要删除的位置，然后单击X。此操作会立即从您的 [!UICONTROL trait] 位置删除 [!UICONTROL segment]。

## [!UICONTROL Segment Builder] 控件： [!UICONTROL Destinations Mappings] 章节 {#segment-builder-controls-destinations}

在 [!UICONTROL Segment Builder]中，可 [!UICONTROL Destinations Mapping] 选部分允许您 [!UICONTROL segment] 向第三方、或发送 [!DNL cookie]数 [!DNL URL]据 [!UICONTROL server-to-server destination]。 要添加、 [!UICONTROL destination]搜索（或浏览）某个对象， [!UICONTROL destination]请提供 [!UICONTROL destination] 特定信息，然后单击 **[!UICONTROL Add Destination]**。

<!-- r_segment_destinations_map.xml -->

### 先决条件

填写和部分中的 [!UICONTROL Basic Information] 必填 [!UICONTROL Traits] 字段。 此外，目标必须已存在。

### [!UICONTROL Destination Mappings] 搜索工具

该 **[!UICONTROL Destination Mappings]** 面板包含如下表中所述的搜索工具。

| 搜索类型 | 描述 |
|---|---|
| **[!UICONTROL Search by Destination Name]** | 允许您按名称搜 [!UICONTROL destination] 索特定。 要搜索，请开始键入。 该字段将根据您的搜索词自动完成。 完成 **[!UICONTROL Add Destination]** 后单击。 |
| **[!UICONTROL Browse All Destinations]** | 浏览所有可 *用*[!UICONTROL destinations] 的列表。 从弹出式 [!UICONTROL destinations] 列表 [!UICONTROL segment] 中选择并添加到。 |

## 弹出窗 [!UICONTROL Destination Mappings] 口中的字段 {#fields-in-dest-mappings}

在 [!UICONTROL Segment Builder]中， [!UICONTROL Add Destination] 选择后将显示对话框 [!UICONTROL destination]。 此窗口显示有关字段和字 [!UICONTROL destination] 段的静态信息，这些信息根据类型 [!UICONTROL destination] 不同而异。 在空字段中提供设置所需信息 [!UICONTROL destination mapping]。

>[!NOTE]
>
>发布日期是可选的。 如果为空，则目标将变为活动状态且永不过期。

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] 字段

在字 [!UICONTROL Destination Mapping] 段中，指定用于向发送数据的键值对 [!UICONTROL destination]。 在第一个字段中输入键，在第二个字段中输入值。 您的 [!UICONTROL cookie destination] 流行乐可能与以下内容类似：

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] 字段

在和字 [!UICONTROL URL] 段 [!UICONTROL Secure URL] 中，指定用于向发送数据的完整标准或安全地址 [!UICONTROL destination]。

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] 字段

在字 [!UICONTROL Destination Value] 段中，指定用于向其发送数据的值（键值对的一部分） [!UICONTROL destination]。

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [创建Cookie目标](../../features/destinations/create-cookie-destination.md)
>* [创建URL目标](../../features/destinations/create-url-destination.md)

