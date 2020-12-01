---
description: 返回特定特征和整个区段之间共享的唯一用户数的数据。
seo-description: 返回特定特征和整个区段之间共享的唯一用户数的数据。
seo-title: 区段到特征重叠报表
solution: Audience Manager
title: 区段到特征重叠报表
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 5%

---


# 区段到特征重叠报表{#segment-to-trait-overlap-report}

返回特定特征和整个区段之间共享的唯一用户数的数据。

>[!NOTE]
>
>Audience Manager中的重叠报表遵循RBAC原则。 您只能根据您所属的[RBAC用户组](/help/using/features/administration/administration-overview.md)从您有权访问的数据源查看区段和特征。

<!-- 

c_segment_trait_overlap.xml

 -->

## 概述

作为优化工具，[!UICONTROL Segment to Trait Overlap]报告可帮助您建立高度集中的细分或扩大细分范围。 例如，您可以创建重叠度高的重点细分和特征，以到达特定受众。 但是，大量重叠可能意味着唯一用户数量减少（触及范围更小）。 运行此报告以通过删除具有大量细分重叠的特征并用重叠较少的特征替换它们来帮助扩大受众范围。

### 示例报告

下图提供了[!UICONTROL Segment-to-Trait Overlap]报告的高级概述。

![](assets/segment-to-trait-overlap.png)

### 深入查看单个数据点

在弹出窗口中选择单个点以视图数据详细信息。 单击操作会自动更新报告中显示的数据。

## 将区段与特征{#comparing-segments-to-traits}比较

介绍如何比较区段和特征，从结果中获得有意义的信息。

<!-- 

c_compare_s2t.xml

 -->

### 比较特征和段单位：示例

乍一看，比较细分与特征并试图从结果中得出结论似乎不合逻辑。 毕竟，细分和特征是不同的，那么从不同项目中衍生出的数据又有什么意义呢？ 但是，在这种情况下，我们不会比较特征和区段，而是比较它们之间共享的唯一访客数。 共享的唯一访客计数提供了使区段与特征比较成为可能的公用值。

下图说明了特征与其所属的区段之间的关系。 在这个例子中，我们有一个特征，有10个访客，一个有1000个访客的片段。 他们共有3个独特的访客。

![](assets/s2t.png)

唯一访客计数是这些不同类别对象之间共享的常数值。 因此，您可以按如下方式确定它们之间的唯一访客关系：

* 特质与区段共享其唯一访客的30%(3/10 = 0.30)。
* 区段共享其特征的唯一访客的0.3%(3/1,000 = 0.003)

### 在区段与特征比较中查找值

查看特征和区段之间的重叠可以帮助您估计可用访客池总数（预测）或查找重叠过多的低效区段。

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>预测</b> </td> 
   <td colname="col2"> <p>要确定可用访客池，请求特征总和（较少重叠）与段总和（较少重叠）之间的差值总和。 </p> <p>此区段特征组合可能最多容纳1004个新用户。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>查找低效的细分</b> </td> 
   <td colname="col2"> <p>如果特征是段定义中<span class="wintitle"> AND</span>组的一部分，则具有该特征的唯一访客已在段中，无法添加到段。 您可以使用此报表查找重叠度低的相关特征并将它们添加到区段定义中，从而增加该区段受众池的范围。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 了解区段到特征重叠报表{#data-filters-s2t-report}中的过滤器

描述特征和区段唯一重叠%滑块的工作方式。

<!-- 

r_s2t_sliders.xml

 -->

通过[!UICONTROL Segment-to-Trait overlap]报告，您可以使用两个滑块按重叠%（按特征或段）筛选数据。

* **[!UICONTROL Filter Trait Uniques %:]** 过滤器特征和区段之间共享的唯一访客的%。
* **[!UICONTROL Filter Segment Uniques Overlap %:]** 过滤器数据，按区段与特征之间共享的唯一访客的%。

### 示例

下图说明了特征单位%与段单位%之间的差异。 在这种情况下，特征和区段共享3个唯一访客。 比例：

* 特质与区段共享其唯一访客的30%(3/10 = 0.30)。
* 区段共享其特征的唯一访客的0.3%(3/1,000 = 0.003)

![](assets/s2t.png)

## 定义的段到特征数据弹出字段{#fields-defined}

描述在单击单个数据点时在弹出窗口中显示的度量。

<!-- 

r_s2t_data_pop.xml

 -->

[!UICONTROL Segment-to-Trait Overlap]报告的弹出窗口包含以下度量。 请注意，表中的唯一度量表示您的&#x200B;*实时用户*。

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
   <td colname="col1"><b><span class="wintitle"> 特征数据源  </span></b> </td> 
   <td colname="col2"> 特征所有者的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 数据源类型</span></b> </td> 
   <td colname="col2">定义特征所属的提供程序类型。 可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一方（您自己的特质）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方（来自外部数据合作伙伴／供应商）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特征ID</span></b> </td> 
   <td colname="col2"> 特征的唯一数字ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特征名称</span></b> </td> 
   <td colname="col2"> 特征的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特征唯一重叠%</span></b> </td> 
   <td colname="col2"> 特征与区段共享的唯一访客的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 区段唯一值重叠%</span></b> </td> 
   <td colname="col2"> 区段共享具有特征的唯一访客的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重叠单位</span></b> </td> 
   <td colname="col2"> 区段与特征之间共享的唯一访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 段唯一值</span></b> </td> 
   <td colname="col2"> 区段中的唯一访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特征唯一</span></b> </td> 
   <td colname="col2"> 特征中的唯一访客数。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用数据滑块筛选报表结果](../../reporting/dynamic-reports/data-sliders.md)
>* [交互式报告中使用的形状、颜色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [说明报告图标和工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报表：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [选定 Audience Manager 报表中的数据取样率和错误率...](../../reporting/report-sampling.md)
>* [重叠报表的 CSV 文件](../../reporting/dynamic-reports/overlap-csv-files.md)