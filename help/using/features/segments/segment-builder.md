---
description: 介绍如何使用区段生成器创建区段。
seo-description: 介绍如何使用区段生成器创建区段。
seo-title: 区段生成器
solution: Audience Manager
title: 区段生成器
uuid: 5ca924a5-2b29-4802-ab02-e292 d77 a ae
translation-type: tm+mt
source-git-commit: b346dbe500f1e662c7b121a18c6cc0704ef3cfac

---


# 区段生成器 {#segment-builder}

Describes the required and optional steps that create a segment in [!UICONTROL Segment Builder].

## 创建区段 {#create-segment}

### 区段生成器部分

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 包含个单独的部分： [!UICONTROL Basic Information][!UICONTROL Traits][!UICONTROL Destinations Mapping]和.To create a segment, complete the required fields in the [!UICONTROL Basic Information] and [!UICONTROL Traits] sections. [!UICONTROL Destinations Mapping] 设置为可选设置。请参阅下面的说明以获取更多帮助。

1. In the [Basic Information](../../features/segments/segment-builder.md#segment-builder-controls-basics) section:
   * 命名区段。区段名称的最大长度为255个字符。
   * 设置区段状态(默认为处于活动状态)。
   * 选择数据源。
   * 选择配置文件合并规则以用于区段资格。
   * 将区段分配给存储文件夹。
1. In the [Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits) section:
   * Search for the trait you want to add to a segment and click **[!UICONTROL Add Trait]**. 添加其他特征以创建特征组。
   * Bring up the Advanced Search modal by clicking **[!UICONTROL Browse All Traits]**. 按名称、ID、描述或数据源搜索特征。搜索时单击文件夹可将结果限制在该文件夹及其子文件夹中。您还可以按特征类型筛选特征。
   * Get live [trait recommendations](trait-recommendations.md) as you build your segment.
   * 单击并拖动特征可创建单独的组。
   * Hover between groups to set relationships with Boolean [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] values.
   * Hover over the clock icon to add [recency and frequency](../../features/segments/recency-and-frequency.md) rules to the trait.
   * 在添加或删除特征时查看细分群体数据。Click **[!UICONTROL Calculate Estimates]** to see (or refresh) the estimated population numbers. Read more about [segment population data](../../features/segments/segment-builder-data.md#segment-populations) in the Segment Builder.
   * Click **[!UICONTROL Save]** when done.
1. *(可选)* 在 [目标映射](../../features/segments/segment-builder.md#segment-builder-controls-destinations) 部分将区段映射到目标：
   * Search for the destination and click **[!UICONTROL Add Destination]**. 注意，目标必须已经存在，然后才能将其添加到区段。
   * Click **[!UICONTROL Save]** when done.

## Segment Builder Controls: Basic Information Section {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] settings let you create new, or edit existing traits. 要创建新区段，请提供名称、数据源并选择存储文件夹。所有其他字段都是可选字段。Move on to the [!UICONTROL Traits] section when done.

<!-- r_segment_basic_info_section.xml -->

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>名称</b> </td> 
   <td colname="col2"> <p>为区段提供一个简短的逻辑名称，用于描述其函数或目的。避免缩写和特殊字符。区段名称的最大长度为255个字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>描述</b> </td> 
   <td colname="col2"> <p>有关区段的其他描述性信息的字段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>集成代码</b> </td> 
   <td colname="col2"> <p>用户定义的ID或其他公司特定信息的字段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>数据源</b> </td> 
   <td colname="col2"> <p>将区段与特定数据提供商关联。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>个人资料合并规则</b> </td> 
   <td colname="col2"> <p>选择配置文件合并规则以用于区段资格。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>状态</b> </td> 
   <td colname="col2"> <p>激活或取消激活区段(默认情况下处于活动状态)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>文件夹存储</b> </td> 
   <td colname="col2"> <p>确定区段属于哪个存储文件夹。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment Builder Controls: Traits Section {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], the [!UICONTROL Traits] section lets you manage traits in a segment, create trait groups, and set qualification criteria. To add a trait to a segment, type the trait name in the search field and click [!UICONTROL Add Trait]. Save the trait (if finished) or move on to [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**先决条件：** 完成 [!UICONTROL Basic Information] 部分中的必填字段。

| 字段 | 描述 |
|--- |--- |
| 基本视图 | 本节提供了可供您使用的可视控件： <ul><li>构建新的和管理现有的细分。</li><li>从区段中删除特征。</li><li>为区段添加最多50(最大)特征。</li><li>拖放特征以创建新组。</li><li>查看区段中的特征和特征组。</li><li>使用Boolean表达式、比较运算符以及最近/频率设置设置资格标准。</li></ul> |
| 代码视图 | 打开一个开发环境，它允许您使用代码而不是可视界面创建和管理特征、组和资格要求。在区段中，代码视图很有用： <ul><li>在单个区段中包含50多个特征。注意：区段仅限于5000个特征(最大)。</li><li>包含许多特征组。</li><li>具有复杂的资格要求。</li></ul> |
| 搜索 | 帮助您找到添加到区段的特征。 |
| 推荐 | 获取类似特征的实时建议，以添加到区段规则。Read more in [Trait Recommendations](trait-recommendations.md). |
| 真实和估计细分大小数据 | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Remove Traits from a Segment {#remove-traits}

管理细分中的特征是保持细分可行性的重要部分。如果需要从区段删除特征，请按照以下步骤操作。

要从区段中删除特征，请执行以下操作：

1. Go to **Audience Data &gt; Segments**. 滚动列表或使用搜索功能查找要处理的区段。
2. 单击区段名称以打开区段详细信息屏幕。
3. Click **Edit** to open Segment Builder and then click **Traits** to open the traits panel.
4. 将鼠标悬停在要删除的特征上方，然后单击X。此操作会立即删除区段中的特征。

## Segment Builder Controls: Destinations Mappings Section {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], the optional [!UICONTROL Destinations Mapping] section lets you send segment data to a third-party [!DNL cookie], [!DNL URL], or server-to-server destination. To add a destination, search (or browse) for a destination, provide destination specific information, and click **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### 先决条件

Complete the required fields in the [!UICONTROL Basic Information] and [!UICONTROL Traits] sections. 此外，目标必须已经存在。

### 目标映射搜索工具

**[!UICONTROL Destination Mappings]** 面板中包含如下表所述的搜索工具。

| 搜索类型 | 描述 |
|---|---|
| **按目标名称搜索** | 允许您按名称搜索特定目标。要进行搜索，请开始键入。字段将根据您的搜索词自动完成。Click **[!UICONTROL Add Destination]** when done. |
| **浏览所有目标** | Browse a list of *all* destinations available to you. 从弹出列表中选择目标并将其添加到区段。 |

## Fields in the Destination Mappings Pop-up Windows {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], the [!UICONTROL Add Destination] dialog appears after you select a destination. 此窗口显示目标和字段的静态信息，这些信息因目标类型而异。在空字段中提供所需的信息以设置目标映射。

>[!NOTE]
>
>发布日期为可选日期。如果为空，目标将变为活动状态，永不过期。

<!-- r_add_mappings_pop.xml -->

### Cookie目标字段

In the [!UICONTROL Destination Mapping] fields, specify the key-value pairs used to send data to the destination. 在第一个字段中输入键，在第二个字段中输入值。您的cookie目标流行信息可能类似于：

![](assets/cookie_modal.PNG)

### URL目标字段

In the [!UICONTROL URL] and [!UICONTROL Secure URL] fields, specify the complete standard or secure address used to send data to the destination.

![](assets/url_modal.PNG)

### 服务器到服务器目标字段

[!UICONTROL Destination Value] 在字段中指定用于向目标发送数据的值(密钥值对的一部分)。

![](assets/s2s_modal.PNG)

>[!MORE_ LIKE_ This]
>
>* [创建Cookie目标](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [创建URL目标](../../features/destinations/manage-destinations.md#configure-url-destination)

