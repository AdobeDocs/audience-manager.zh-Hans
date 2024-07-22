---
description: 返回有关特定特征和整个区段之间共享的独特用户数的数据。
seo-description: Returns data on the number of unique users shared between a particular trait and an entire segment.
seo-title: Segment-to-Trait Overlap Report
solution: Audience Manager
title: 区段到特征重叠报表
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Overlap Reports
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%

---

# 区段到特征重叠报表{#segment-to-trait-overlap-report}

返回有关特定特征和整个区段之间共享的独特用户数的数据。

>[!NOTE]
>
>Audience Manager中的重叠报表遵循RBAC原则。 您只能根据您所属的[RBAC用户组](/help/using/features/administration/administration-overview.md)，从您有权访问的数据源中查看区段和特征。

<!-- 

c_segment_trait_overlap.xml

 -->

## 概述

作为优化工具，[!UICONTROL Segment to Trait Overlap]报表可帮助您构建重点突出的区段或扩大区段范围。 例如，您可以创建具有高重叠度的重点区段和特征以覆盖特定受众。 但是，大量重叠可能意味着独特用户更少（覆盖范围更小）。 运行此报告有助于通过删除具有大量区段重叠的特征，并将它们替换为重叠较少的特征，来扩展范围。

### 示例报告

下图提供了[!UICONTROL Segment-to-Trait Overlap]报表的高级概述。

![](assets/segment-to-trait-overlap.png)

### 向下展开单个数据点

选择单个点以在弹出窗口中查看数据详细信息。 您的单击操作会自动更新报告中显示的数据。

## 将区段与特征进行比较 {#comparing-segments-to-traits}

描述如何比较区段和特征以从结果中获取有意义的信息。

<!-- 

c_compare_s2t.xml

 -->

### 比较特征和区段唯一性：示例

乍一看，将区段与特征进行比较并尝试从结果中得出结论似乎不合逻辑。 毕竟，区段和特征是不同的，那么从完全不同的项目获得的数据又有什么意义呢？ 但是，在本例中，我们不是比较特征和区段，而是比较特征与区段之间共享的独特访客数量。 共享的唯一访客计数提供了一个通用值，可用于将区段与特征进行比较。

下图说明了特征与其所属的区段之间的关系。 在本例中，我们有一个包含10位访客的特征和一个包含1,000位访客的区段。 他们共用3个独特访客。

![](assets/s2t.png)

独特访客计数是在这些不同的对象类之间共享的通用常量值。 因此，您可以确定它们之间的独特访客关系，如下所示：

* 该特征与区段共享其30%的独特访客(3/10 = 0.30)。
* 该区段与特征共享其0.3%的独特访客(3/1,000 = 0.003)

### 在区段与特征比较中查找值

查看特征和区段之间的重叠可以帮助您估计可用访客池（预测）总数或查找重叠过多的低效区段。

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
   <td colname="col2"> <p>要确定可用的访客池，请对特征总计（较少重叠）和区段总计（较少重叠）之间的差异求和。 </p> <p>此区段 — 特征组合最多可以包含1004个新用户。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>查找效率低下的区段</b> </td> 
   <td colname="col2"> <p>如果某个特征属于区段定义中的<span class="wintitle"> AND</span>组，则具有该特征的独特访客已存在于区段中，并且无法添加到区段中。 您可以使用此报表查找重叠程度较低的相关特征，并将其添加到区段定义，从而扩大该区段受众池的覆盖范围。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 了解区段到特征重叠报表中的数据过滤器 {#data-filters-s2t-report}

描述特征和区段唯一重叠%滑块的工作方式。

<!-- 

r_s2t_sliders.xml

 -->

[!UICONTROL Segment-to-Trait overlap]报表允许您使用两个滑块按特征或区段重叠百分比过滤数据。

* **[!UICONTROL Filter Trait Uniques %:]**&#x200B;按特征和区段之间共享的独特访客的%过滤数据。
* **[!UICONTROL Filter Segment Uniques Overlap %:]**&#x200B;按区段和特征之间共享的独特访客的%过滤数据。

### 示例

下图说明了特征唯一值%与区段唯一值%之间的差异。 在这种情况下，特征和区段共享3个独特访客。 按比例：

* 该特征与区段共享其30%的独特访客(3/10 = 0.30)。
* 该区段与特征共享其0.3%的独特访客(3/1,000 = 0.003)

![](assets/s2t.png)

## 定义的区段到特征数据Pop字段 {#fields-defined}

描述单击单个数据点时弹出式窗口中显示的量度。

<!-- 

r_s2t_data_pop.xml

 -->

[!UICONTROL Segment-to-Trait Overlap]报表的弹出窗口包含下列量度。 请注意，表中的唯一量度表示您的&#x200B;*实时用户*。

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">区段ID</span></b> </td> 
   <td colname="col2"> 区段的唯一数值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">特征数据Source </span></b> </td> 
   <td colname="col2"> 特征所有者的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">数据Source类型</span></b> </td> 
   <td colname="col2">定义特征所属的提供程序的类型。 可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一方（您自己的特征）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方（来自外部数据合作伙伴/供应商）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">特征ID</span></b> </td> 
   <td colname="col2"> 特征的唯一数值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">特征名称</span></b> </td> 
   <td colname="col2"> 特征的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">特征唯一项重叠%</span></b> </td> 
   <td colname="col2"> 特征与区段共享的独特访客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">区段唯一值重叠%</span></b> </td> 
   <td colname="col2"> 区段与某个特征共享的独特访客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">个重叠唯一值</span></b> </td> 
   <td colname="col2"> 在区段和特征之间共享的独特访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">区段唯一值</span></b> </td> 
   <td colname="col2"> 区段中的独特访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">特征独特</span></b> </td> 
   <td colname="col2"> 特征中的独特访客数。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用数据滑块筛选报表结果](../../reporting/dynamic-reports/data-sliders.md)
>* [交互式报表中使用的形状、颜色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [报告图标和工具说明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报表：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [选定Audience Manager报表中的数据取样率和错误率……](../../reporting/report-sampling.md)
>* [重叠报表的 CSV 文件](../../reporting/dynamic-reports/overlap-csv-files.md)
