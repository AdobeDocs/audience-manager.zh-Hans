---
description: “区段到广告单元重叠”报告显示为广告单位和受众管理器区段之间高和低重叠的热点图。
seo-description: “区段到广告单元重叠”报告显示为广告单位和受众管理器区段之间高和低重叠的热点图。
seo-title: 区段到广告单元重叠
solution: Audience Manager
title: 区段到广告单元重叠
uuid: aa20163-58aa-42c9-8f72-a1 dfb0 d20 e57
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment to Ad Unit Overlap{#segment-to-ad-unit-overlap}

“区段到广告单元重叠”报告显示为广告单位和受众管理器区段之间高和低重叠的热点图。

## 用例 {#use-cases}

With the [!UICONTROL Segment to Ad Unit Overlap] report, you can understand which audiences visit your web properties. The report displays the overlap between members of your [!DNL Audience Manager] segments and the number of visitors to your web properties. 重叠意味着区段的许多成员访问您的Web资产。

## Using the Segment to Ad Unit Overlap Report {#using-the-report}

Use the **[!UICONTROL Top N Ad Units]** and **[!UICONTROL Top N Segments]** controls to select your desired number of ad units and segments for the overlap. 您可以为每个项目选择最多100个项目。

Use the **Day Range** and **Date Through** controls to adjust your look-back range. 请注意，天和30天回顾期仅可用于星期日日期。

Use the **[!UICONTROL Segment Name]** and the **[!UICONTROL Ad Unit]** boxes to filter any of segments and ad units.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

[!UICONTROL Segment to Ad Unit Overlap] 您的报表类似于下面的报告。将鼠标悬停在任意单元格上可获得有关该特定重叠内容的更多信息。有关详细信息，请参阅示例报告下表格中的其他信息。

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
   <td colname="col1"> <p><span class="wintitle"> 广告单元 </span> </p> </td> 
   <td colname="col2"> <p>库存项目的名称。例如，这可以是您的网站或网站上的文章。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 区段实时统一计数</span> </p> </td> 
   <td colname="col2"> <p>The number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 广告单元统一计数</span> </p> </td> 
   <td colname="col2"> <p>此特定广告单元访客的数量。此信息将从DFP日志中提取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠唯一计数数</span> </p> </td> 
   <td colname="col2"> <p>您区段中暴露给广告单元项目的成员。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠百分比</span> </p> </td> 
   <td colname="col2"> <p>广告单元与细分人群之间的重叠。This is the <span class="wintitle"> Overlap Uniques Count</span>, expressed as a percentage of the <span class="wintitle"> Segment Real Time Uniques</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

