---
description: 介绍如何使用区段生成器创建区段。
seo-description: 介绍如何使用区段生成器创建区段。
seo-title: 区段生成器
solution: Audience Manager
title: 区段生成器
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0ae
translation-type: tm+mt
source-git-commit: 0d0806ef2c84b4770adc29d668351ac3f2d8cc5f

---


# 区段生成器 {#segment-builder}

介绍在中创建区段的必需和可选步骤 [!UICONTROL Segment Builder]。

## 视频演示

首先，观看Audience Manager [中的“创建细分”视频](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)。 该视频将引导您完成区段创建过程。 请阅读以下各节以了解更多信息。

## 创建区段 {#create-segment}

### “区段生成器”部分

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 由3个单独的部分组成： [!UICONTROL Basic Information]、 [!UICONTROL Traits]和 [!UICONTROL Destinations Mapping]。 要创建区段，请填写和部分中的必 [!UICONTROL Basic Information] 填字 [!UICONTROL Traits] 段。 [!UICONTROL Destinations Mapping] 设置是可选的。 请参阅下面的说明以获取更多帮助。

1. 在“基 [本信息](../../features/segments/segment-builder.md#segment-builder-controls-basics) ”部分：
   * 命名区段。 区段名称的最大长度为255个字符。
   * 设置区段状态（默认为活动）。
   * 选择数据源。
   * 选择用于区段资格的配置文件合并规则。
   * 将区段分配到存储文件夹。
1. 在“特 [征](../../features/segments/segment-builder.md#segment-builder-controls-traits) ”部分：
   * 搜索要添加到区段的特征，然后单击 **[!UICONTROL Add Trait]**。 添加另一个特征以创建特征组。
   * 单击以调出“高级搜索”模式 **[!UICONTROL Browse All Traits]**。 按名称、ID、说明或数据源搜索特征。 在搜索时单击文件夹，将结果限制在该文件夹及其子文件夹中。 您还可以按特征类型筛选特征。
   * 在构建 [细分时获取实时](trait-recommendations.md) 特征推荐。
   * 单击并拖动特征以创建单独的组。
   * 在组之间悬停可设置与布尔值、 [!UICONTROL AND]值、 [!UICONTROL OR]值的 [!UICONTROL AND NOT] 关系。
   * 将指针悬停在时钟图标上，可向 [特征添加近期和频率](../../features/segments/recency-and-frequency.md) 规则。
   * 在添加或删除特征时查看区段人口数据。 单击 **[!UICONTROL Calculate Estimates]** 查看（或刷新）估计的人口数。 在“区段生成 [器”中阅读有关区段](../../features/segments/segment-builder-data.md#segment-populations) 填充数据的更多信息。
   * Click **[!UICONTROL Save]** when done.
1. *（可选）* “目标映射”部分中的区段映射 [到目标](../../features/segments/segment-builder.md#segment-builder-controls-destinations) :
   * 搜索目标并单击 **[!UICONTROL Add Destination]**。 请注意，目标必须已存在，然后才能将其添加到区段。
   * Click **[!UICONTROL Save]** when done.

## 区段生成器控件：基本信息部分 {#segment-builder-controls-basics}

在中， [!UICONTROL Segment Builder]设 [!UICONTROL the Basic Information] 置允许您创建新特征或编辑现有特征。 要创建新区段，请提供名称、数据源，然后选择存储文件夹。 所有其他字段都是可选的。 完成后，移 [!UICONTROL Traits] 到部分。

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
   <td colname="col2"> <p>为区段提供一个简短的逻辑名称，用于描述其功能或用途。 避免缩写和特殊字符。 区段名称的最大长度为255个字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>描述</b> </td> 
   <td colname="col2"> <p>有关区段的其他描述性信息的字段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>集成代码</b> </td> 
   <td colname="col2"> <p>用户定义ID或其他公司特定信息的字段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>数据源</b> </td> 
   <td colname="col2"> <p>将区段与特定数据提供者关联。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>个人资料合并规则</b> </td> 
   <td colname="col2"> <p>选择用于区段资格的配置文件合并规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>状态</b> </td> 
   <td colname="col2"> <p>激活或取消激活区段（默认情况下为活动状态）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>文件夹存储</b> </td> 
   <td colname="col2"> <p>确定区段所属的存储文件夹。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 区段生成器控件：特征部分 {#segment-builder-controls-traits}

在中 [!UICONTROL Segment Builder]，该部 [!UICONTROL Traits] 分允许您管理区段中的特征、创建特征组和设置资格条件。 要向区段添加特征，请在搜索字段中键入特征名称，然后单击 [!UICONTROL Add Trait]。 保存特征（如果完成）或移到 [!UICONTROL Destinations Mapping]。

<!-- r_segment_traits_section.xml -->

**** 先决条件：填写部分中的必填 [!UICONTROL Basic Information] 字段。

| 字段 | 描述 |
|--- |--- |
| 基本视图 | 此部分提供了可视控件，允许您： <ul><li>建立新的客户群并管理现有客户群。</li><li>从区段中删除特征。</li><li>将最多50个（最大）特征加入区段。</li><li>拖放特征以创建新组。</li><li>查看区段中的特征和特征组。</li><li>使用布尔表达式、比较运算符和最近使用的频率设置设置资格标准。</li></ul> |
| 代码视图 | 打开一个开发环境，通过该环境，您可以使用代码而不是可视界面来创建和管理特征、组和资格要求。 如果您的区段为： <ul><li>在单个区段中包含50多个特征。 注意：区段限制为5000个特征（最大）。</li><li>包含许多特征组。</li><li>具有复杂的资格要求。</li></ul> |
| 搜索 | 帮助您查找要添加到区段的特征。 |
| 推荐 | 获取要添加到区段规则的类似特征的实时推荐。 阅读特征推荐 [中的更多信息](trait-recommendations.md)。 |
| 真实和估计的细分大小数据 | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## 从区段中删除特征 {#remove-traits}

管理区段中的特征是保持区段可行性的重要部分。 如果需要从区段中删除特征，请按照以下步骤操作。

要从区段中删除特征：

1. 转到“受 **众数据”&gt;“区段”**。 滚动浏览列表或使用搜索功能查找要处理的区段。
2. 单击区段名称以打开区段详细信息屏幕。
3. 单击 **编辑** ，打开区段生成器，然后单击 **特征** ，打开特征面板。
4. 将指针悬停在要删除的特征上，然后单击X。此操作会立即从您的区段中删除特征。

## 区段生成器控件：“目标映射”部分 {#segment-builder-controls-destinations}

在 [!UICONTROL Segment Builder]中，可 [!UICONTROL Destinations Mapping] 选部分允许您将区段数据发送到第三方、 [!DNL cookie]或服 [!DNL URL]务器到服务器目标。 要添加目标，请搜索（或浏览）目标，提供目标特定信息，然后单击 **[!UICONTROL Add Destination]**。

<!-- r_segment_destinations_map.xml -->

### 先决条件

填写和部分中的必 [!UICONTROL Basic Information] 填字 [!UICONTROL Traits] 段。 此外，目标必须已存在。

### 目标映射搜索工具

该面 **[!UICONTROL Destination Mappings]** 板包含如下表中所述的搜索工具。

| 搜索类型 | 描述 |
|---|---|
| **按目标名称搜索** | 允许您按名称搜索特定目标。 要搜索，请开始键入。 该字段将根据您的搜索词自动完成。 Click **[!UICONTROL Add Destination]** when done. |
| **浏览所有目标** | 浏览所有可 *用目标* 的列表。 从弹出列表中选择目标并将其添加到您的区段。 |

## “目标映射”弹出窗口中的字段 {#fields-in-dest-mappings}

在中， [!UICONTROL Segment Builder]选择目 [!UICONTROL Add Destination] 标后将显示该对话框。 此窗口显示有关目标和字段的静态信息，这些信息根据目标类型而有所不同。 在空字段中提供所需信息以设置目标映射。

>[!NOTE]
>
>发布日期是可选的。 如果为空，则目标将变为活动状态且永不过期。

<!-- r_add_mappings_pop.xml -->

### Cookie目标字段

在字 [!UICONTROL Destination Mapping] 段中，指定用于将数据发送到目标的键值对。 在第一个字段中输入键，在第二个字段中输入值。 您的Cookie目标弹出窗口可能类似于：

![](assets/cookie_modal.PNG)

### URL目标字段

在和字 [!UICONTROL URL] 段中 [!UICONTROL Secure URL] ，指定用于将数据发送到目标的完整标准或安全地址。

![](assets/url_modal.PNG)

### 服务器到服务器目标字段

在字 [!UICONTROL Destination Value] 段中，指定用于将数据发送到目标的值（键值对的一部分）。

![](assets/s2s_modal.PNG)

>[!MORE_LIKE_THIS]
>
>* [创建Cookie目标](../../features/destinations/create-cookie-destination.md)
>* [创建URL目标](../../features/destinations/create-url-destination.md)

