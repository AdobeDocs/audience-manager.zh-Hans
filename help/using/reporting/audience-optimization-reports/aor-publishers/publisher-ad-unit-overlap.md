---
description: “广告单元重叠”报告显示为广告单位之间高和低重叠的热点图。
seo-description: “广告单元重叠”报告显示为广告单位之间高和低重叠的热点图。
seo-title: 广告单元重叠
solution: Audience Manager
title: 广告单元重叠
uuid: e4467e81-acbf-474e-b501-89d57395651 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ad Unit Overlap{#ad-unit-overlap}

**[!UICONTROL Ad Unit Overlap]** 报告显示为广告单位之间高和低重叠的热点图。

## 用例 {#use-cases}

**[!UICONTROL Ad Unit Overlap]** 通过报告，您可以了解受众在您的网络资产中的位置。报告将考虑100个顶级相关属性，并显示它们之间的重叠。

## Using the Ad Unit Overlap Report {#using-the-report}

Use the **[!UICONTROL Top N Base Ad Units]** and **[!UICONTROL Top N Overlapping Ad Units]** controls to select your desired number of ad units for the overlap. 您可以为每个项目选择最多100个项目。

Use the **Day Range** and **Date Through** controls to adjust your look-back range. 请注意，天和30天回顾期仅可用于星期日日期。

Use the **[!UICONTROL Base Ad Unit]** and the **[!UICONTROL Overlap Ad Unit]** controls to select which of your ad units you want to display in the overlap report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

[!UICONTROL Ad Unit Overlap] 您的报表类似于下面的报告。将鼠标悬停在任意单元格上可获得有关该特定重叠内容的更多信息。有关详细信息，请参阅示例报告下表格中的其他信息。

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠广告单元</span> </p> </td> 
   <td colname="col2"> <p>库存项目的名称。例如，这可以是您的网站或网站上的文章。在上面的图像中，基本广告单元为文章-18。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 基本广告单元</span> </p> </td> 
   <td colname="col2"> <p>库存项目的名称。例如，这可以是您的网站或网站上的文章。在上面的图像中，基本广告单元为文章-8。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠广告单元累计计数</span> </p> </td> 
   <td colname="col2"> <p>已访问广告单元项目-18的用户数。此信息将从DFP日志中提取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 基本广告单元累计计数</span> </p> </td> 
   <td colname="col2"> <p>已访问广告单元项目的用户数-8。此信息将从DFP日志中提取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠唯一计数数</span> </p> </td> 
   <td colname="col2"> <p>The overlap between your users who have visited a <span class="wintitle"> Base Ad Unit</span> and <span class="wintitle"> Overlap Ad Unit</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠百分比</span> </p> </td> 
   <td colname="col2"> <p>The overlap between your users who have visited a <span class="wintitle"> Base Ad Unit</span> and <span class="wintitle"> Overlap Ad Unit</span>. This is the <span class="wintitle"> Overlap Uniques Count</span>, expressed as a percentage of the <span class="wintitle"> Base Ad Unit</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
