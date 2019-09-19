---
description: “区段到广告单位重叠”报告显示为热图，突出显示广告单位与Audience manager区段之间的高重叠和低重叠。
seo-description: “区段到广告单位重叠”报告显示为热图，突出显示广告单位与Audience manager区段之间的高重叠和低重叠。
seo-title: 区段到广告单元重叠
solution: Audience Manager
title: 区段到广告单元重叠
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 区段到广告单元重叠{#segment-to-ad-unit-overlap}

“区段到广告单位重叠”报告显示为热图，突出显示广告单位与Audience manager区段之间的高重叠和低重叠。

## 用例 {#use-cases}

通过该报 [!UICONTROL Segment to Ad Unit Overlap] 告，您可以了解哪些受众访问您的Web资产。 该报告显示区段成员与Web [!DNL Audience Manager] 属性访问者数量之间的重叠。 重叠程度越高，表示区段的许多成员都会访问您的Web资产。

## 使用区段以广告单元重叠报表 {#using-the-report}

使用和 **[!UICONTROL Top N Ad Units]** 控件 **[!UICONTROL Top N Segments]** 为重叠选择所需数量的广告单位和区段。 每个项目最多可选择100个项目。

使用“ **日期范围** ”和“ **** 日期穿透”控件调整回顾范围。 请注意，7天和30天回顾期仅适用于星期日日期。

使用和 **[!UICONTROL Segment Name]** 框可筛 **[!UICONTROL Ad Unit]** 选任意区段和广告单位。

>[!IMPORTANT]
>
>启用此 [!UICONTROL Audience Optimization for Publishers]项后，您必须包含描述性元数据， [!UICONTROL Ad Unit IDs]如将DFP数据文件导入Audience manager的 [步骤3中所述](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 通过执行此操作，您可以确保报告将Web属性详细 [!UICONTROL Ad Unit] 化为 [!UICONTROL Ad Unit ID]。

## 解释结果 {#interpreting-results}

您 [!UICONTROL Segment to Ad Unit Overlap] 的报告可能与以下报告类似。 将鼠标悬停在任何单元格上可获得有关该特定重叠的更多信息。 有关示例报告下表中的其他信息，请参阅说明。

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 广告单位 </span> </p> </td> 
   <td colname="col2"> <p>库存物料的名称。 例如，这可以是您的网站之一或您网站上的文章。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 细分实时唯一值计数</span> </p> </td> 
   <td colname="col2"> <p>在指定时间范围内实时查看的唯一访客数，以及在Audience manager查看区段时有资格访问这些访客的 <span class="keyword"> 数量</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 广告单位唯一值计数</span> </p> </td> 
   <td colname="col2"> <p>此特定广告单元的访客数。 此信息从DFP日志中提取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠唯一值计数</span> </p> </td> 
   <td colname="col2"> <p>面向广告单元项目的区段成员。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠百分比</span> </p> </td> 
   <td colname="col2"> <p>广告单位和细分群体之间的重叠。 这是重叠 <span class="wintitle"> 唯一值计数</span>，表示为区段实时唯一值 <span class="wintitle"> 的百分比</span>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

