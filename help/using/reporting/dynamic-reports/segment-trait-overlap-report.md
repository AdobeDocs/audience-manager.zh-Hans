---
description: 返回特定特征和整个区段之间共享的唯一用户数量数据。
seo-description: 返回特定特征和整个区段之间共享的唯一用户数量数据。
seo-title: 区段到特质重叠报表
solution: Audience Manager
title: 区段到特质重叠报表
uuid: a6b3dd21-332e-449f-aa01-2bb47 f1794 e
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# 区段到特质重叠报表{#segment-to-trait-overlap-report}

返回特定特征和整个区段之间共享的唯一用户数量数据。

>[!NOTE]
>
>Audience Manager中的重叠报告遵循CLUAC原则。You can only see segments and traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_segment_trait_overlap.xml

 -->

## 概述

As an optimization tool, the [!UICONTROL Segment to Trait Overlap] reports helps you build highly focused segments or expand segment reach. 例如，您可以创建具有高重叠值的聚焦细分和特征，以覆盖特定受众。但是，许多重叠可能意味着不同的用户(触及范围更少)。运行此报告可通过删除具有大量区段重叠的特征并用减少重叠的特征替换，从而帮助扩大范围。

### 示例报告

The following illustration provides a high-level overview of the [!UICONTROL Segment-to-Trait Overlap] report.

![](assets/segment-to-trait-overlap.png)

### 深入了解各个数据点

选择单个点可在弹出窗口中查看数据详细信息。单击操作会自动更新报告中显示的数据。

## Comparing Segments to Traits {#comparing-segments-to-traits}

介绍如何比较区段和特征，从结果中得出有意义的信息。

<!-- 

c_compare_s2t.xml

 -->

### 比较特征和区段统一：示例

乍一看，比较细分与特征并尝试得出结果可能看起来不合逻辑。毕竟，细分和特征不同，因此来自不同项目的数据如何产生含义？但是，在这种情况下，我们并不会比较特征和区段，而是在访客之间共享的唯一访客数量。共享的独特访客计数提供了共同值，使区段能够进行特征比较。

下图说明了特征与其所属区段之间的关系。在这种情况下，我们有一个特征为10个访客，一个区段具有1,000个访客。他们共享共有个独特的访客。

![](assets/s2t.png)

独特的访客计数是在这些不同对象类之间共享的通用常数值。因此，您可以按如下方式确定不同的访客关系：

* 特征共享其唯一访客的30%(3/10=0.30)。
* 该区段与特征共享的唯一访客有0.3%(3/1,000=0.03)

### 在区段中查找值与特征比较

查看特征和区段之间的重叠可帮助您评估可用的访客池(预测)，或查找效率过高的低效细分。

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>预测功能</b> </td> 
   <td colname="col2"> <p>要确定可用的访客池，请将特征总数与区段总数(减少重叠)相加(减少重叠)。 </p> <p>此区段特征组合可覆盖最多100名新用户。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>查找低效细分</b> </td> 
   <td colname="col2"> <p>If a trait is part of an <span class="wintitle"> AND</span> group in a segment definition, the unique visitors who have that trait are already in the segment and not available for adding to the segment. 您可以使用此报告找到较低重叠的相关特征，并将其添加到区段定义中，从而提高区段受众池的范围。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Understanding the Data Filters in the Segment-to-Trait Overlap Report {#data-filters-s2t-report}

描述特征和区段独特重叠百分比滑块的工作原理。

<!-- 

r_s2t_sliders.xml

 -->

[!UICONTROL Segment-to-Trait overlap] 该报告允许您使用两个滑块按特征或区段筛选重叠的数据。

* **[!UICONTROL Filter Trait Uniques %:]** 按特征与区段之间共享的唯一访客百分比过滤数据。
* **[!UICONTROL Filter Segment Uniques Overlap %:]** 按唯一访客在区段与特征之间共享的百分比过滤数据。

### 示例

下图说明了特征唯一值%和区段唯一值%之间的差异。在这种情况下，特征和区段共享个独特访客。比例：

* 特征共享其唯一访客的30%(3/10=0.30)。
* 该区段与特征共享的唯一访客有0.3%(3/1,000=0.03)

![](assets/s2t.png)

## Segment-to-Trait Data Pop Fields Defined {#fields-defined}

在单击单个数据点时，描述弹出窗口中显示的量度。

<!-- 

r_s2t_data_pop.xml

 -->

[!UICONTROL Segment-to-Trait Overlap] 报告的弹出窗口包含以下指标。Note that the uniques metric in the table represents your *real-time users*.

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 区段ID</span></b> </td> 
   <td colname="col2"> 区段的唯一数字ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 数据提供程序名称</span></b> </td> 
   <td colname="col2"> 区段所有者的姓名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 数据提供者类型</span></b> </td> 
   <td colname="col2">定义属于的提供者类型。可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一方(您自己的特征)。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方(来自数据合作伙伴/供应商)。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> SID</span></b> </td> 
   <td colname="col2"> 区段的唯一数字ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> SID名称</span></b> </td> 
   <td colname="col2"> 区段的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特征统一重叠%</span></b> </td> 
   <td colname="col2"> 属于特征共享的唯一访客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 区段唯一重叠百分比</span></b> </td> 
   <td colname="col2"> 一个区段与特征共享的唯一访客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重叠统一</span></b> </td> 
   <td colname="col2"> 区段与特征之间共享的唯一访客数量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 区段统一</span></b> </td> 
   <td colname="col2"> 区段中唯一访客数量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特征统一</span></b> </td> 
   <td colname="col2"> 特征中唯一访客数量。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [使用数据滑块过滤报告结果](../../reporting/dynamic-reports/data-sliders.md)
>* [交互式报告中使用的形状、颜色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [报告图标和工具说明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报告：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [选定Audience Manager报告中的数据采样和错误率…](../../reporting/report-sampling.md)
>* [重叠报告的CSV文件](../../reporting/dynamic-reports/overlap-csv-files.md)