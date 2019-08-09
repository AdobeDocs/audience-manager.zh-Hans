---
description: 介绍如何使用区段生成器创建区段。
seo-description: 介绍如何使用区段生成器创建区段。
seo-title: 区段生成器
solution: Audience Manager
title: 区段生成器
uuid: 5ca924a5-2b29-4802-ab02-e292 d77 a ae
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# 区段生成器 {#segment-builder}

介绍在其中创建区段所需的和可选的步骤 [!UICONTROL Segment Builder]。

## 创建区段 {#create-segment}

### 区段生成器部分

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 包含个单独的部分： [!UICONTROL Basic Information][!UICONTROL Traits][!UICONTROL Destinations Mapping]和.要创建区段，请填写和 [!UICONTROL Basic Information][!UICONTROL Traits] 部分中的必填字段。[!UICONTROL Destinations Mapping] 设置为可选设置。请参阅下面的说明以获取更多帮助。

1. 在 [“基本信息”](../../features/segments/segment-builder.md#segment-builder-controls-basics) 部分中：
   * 命名区段。区段名称的最大长度为255个字符。
   * 设置区段状态(默认为处于活动状态)。
   * 选择数据源。
   * 选择配置文件合并规则以用于区段资格。
   * 将区段分配给存储文件夹。
1. 在 [“特征](../../features/segments/segment-builder.md#segment-builder-controls-traits) ”部分中：
   * 搜索要添加到区段中的特征，然后单击 **[!UICONTROL Add Trait]**。添加其他特征以创建特征组。
   * 单击 **[!UICONTROL Browse All Traits]**“高级搜索”模式。按名称、ID、描述或数据源搜索特征。搜索时单击文件夹可将结果限制在该文件夹及其子文件夹中。您还可以按特征类型筛选特征。
   * 在构建细分时获得实时 [特征推荐](trait-recommendations.md) 。
   * 单击并拖动特征可创建单独的组。
   * 将鼠标悬停在组之间可设置与Boolean [!UICONTROL AND]、 [!UICONTROL OR][!UICONTROL AND NOT] 值的关系。
   * 将鼠标悬停在时钟图标上，可向特征添加 [最近的缩进和频率](../../features/segments/recency-and-frequency.md) 规则。
   * 在添加或删除特征时查看细分群体数据。单击 **[!UICONTROL Calculate Estimates]** 以查看(或刷新)估计的人口编号。阅读有关细分生成器 [中细分人口数据](../../features/segments/segment-builder-data.md#segment-populations) 的更多信息。
   * Click **[!UICONTROL Save]** when done.
1. *(可选)* 在 [目标映射](../../features/segments/segment-builder.md#segment-builder-controls-destinations) 部分将区段映射到目标：
   * 搜索目标并单击 **[!UICONTROL Add Destination]**。注意，目标必须已经存在，然后才能将其添加到区段。
   * Click **[!UICONTROL Save]** when done.

## 区段生成器控制：基本信息部分 {#segment-builder-controls-basics}

在中 [!UICONTROL Segment Builder]， [!UICONTROL the Basic Information] 设置允许您创建新属性或编辑现有特征。要创建新区段，请提供名称、数据源并选择存储文件夹。所有其他字段都是可选字段。完成后，移到 [!UICONTROL Traits] 章节。

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

## 区段生成器控制：特征部分 {#segment-builder-controls-traits}

在该部分 [!UICONTROL Segment Builder]中， [!UICONTROL Traits] 您可以管理区段中的特征、创建特征组以及设置资格标准。要将特征添加到区段，请在搜索字段中键入特征名称，然后单击 [!UICONTROL Add Trait]。保存特征(如果已完成)或继续使用 [!UICONTROL Destinations Mapping]。

<!-- r_segment_traits_section.xml -->

**先决条件：** 完成 [!UICONTROL Basic Information] 部分中的必填字段。

| 字段 | 描述 |
|--- |--- |
| 基本视图 | 本节提供了可供您使用的可视控件： <ul><li>构建新的和管理现有的细分。</li><li>从区段中删除特征。</li><li>为区段添加最多50(最大)特征。</li><li>拖放特征以创建新组。</li><li>查看区段中的特征和特征组。</li><li>使用Boolean表达式、比较运算符以及最近/频率设置设置资格标准。</li></ul> |
| 代码视图 | 打开一个开发环境，它允许您使用代码而不是可视界面创建和管理特征、组和资格要求。在区段中，代码视图很有用： <ul><li>在单个区段中包含50多个特征。注意：区段仅限于5000个特征(最大)。</li><li>包含许多特征组。</li><li>具有复杂的资格要求。</li></ul> |
| 搜索 | 帮助您找到添加到区段的特征。 |
| 推荐 | 获取类似特征的实时建议，以添加到区段规则。请阅读 [特征推荐](trait-recommendations.md)中的更多信息。 |
| 真实和估计细分大小数据 | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## 从区段中删除特征 {#remove-traits}

管理细分中的特征是保持细分可行性的重要部分。如果需要从区段删除特征，请按照以下步骤操作。

要从区段中删除特征，请执行以下操作：

1. 转到 **受众数据&gt;区段**。滚动列表或使用搜索功能查找要处理的区段。
2. 单击区段名称以打开区段详细信息屏幕。
3. 单击 **编辑** 以打开区段生成器，然后单击 **属性** 以打开特性面板。
4. 将鼠标悬停在要删除的特征上方，然后单击X。此操作会立即删除区段中的特征。

## 区段生成器控制：目标映射部分 {#segment-builder-controls-destinations}

在中 [!UICONTROL Segment Builder]，可选 [!UICONTROL Destinations Mapping] 部分允许您将区段数据发送到第三方 [!DNL cookie]、 [!DNL URL]服务器或服务器到服务器目标。要为目标添加目标，请搜索(或浏览)目标，提供目标信息，然后单击 **[!UICONTROL Add Destination]**。

<!-- r_segment_destinations_map.xml -->

### 先决条件

完成 [!UICONTROL Basic Information] 和 [!UICONTROL Traits] 部分中的必填字段。此外，目标必须已经存在。

### 目标映射搜索工具

**[!UICONTROL Destination Mappings]** 面板中包含如下表所述的搜索工具。

| 搜索类型 | 描述 |
|---|---|
| **按目标名称搜索** | 允许您按名称搜索特定目标。要进行搜索，请开始键入。字段将根据您的搜索词自动完成。Click **[!UICONTROL Add Destination]** when done. |
| **浏览所有目标** | 浏览可供您使用的 *所有* 目标的列表。从弹出列表中选择目标并将其添加到区段。 |

## “目标映射”弹出窗口中的字段 {#fields-in-dest-mappings}

在 [!UICONTROL Segment Builder]中，在您选择目标后， [!UICONTROL Add Destination] 将显示该对话框。此窗口显示目标和字段的静态信息，这些信息因目标类型而异。在空字段中提供所需的信息以设置目标映射。

>[!NOTE]
>
>发布日期为可选日期。如果为空，目标将变为活动状态，永不过期。

<!-- r_add_mappings_pop.xml -->

### Cookie目标字段

在 [!UICONTROL Destination Mapping] 字段中，指定用于向目标发送数据的键值对。在第一个字段中输入键，在第二个字段中输入值。您的cookie目标流行信息可能类似于：

![](assets/cookie_modal.PNG)

### URL目标字段

在 [!UICONTROL URL] 和 [!UICONTROL Secure URL] 字段中，指定用于向目标发送数据的完整标准或安全地址。

![](assets/url_modal.PNG)

### 服务器到服务器目标字段

[!UICONTROL Destination Value] 在字段中指定用于向目标发送数据的值(密钥值对的一部分)。

![](assets/s2s_modal.PNG)

>[!MORE_ LIKE_ This]
>
>* [创建Cookie目标](../../features/destinations/create-cookie-destination.md)
>* [创建URL目标](../../features/destinations/create-url-destination.md)

