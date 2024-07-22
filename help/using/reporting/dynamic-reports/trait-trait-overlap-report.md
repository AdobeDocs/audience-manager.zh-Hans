---
description: 返回有关您的所有第一方和第三方特征之间共享的独特用户数的数据。
seo-description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-title: Trait-to-Trait Overlap Report
solution: Audience Manager
title: 特质到特质重叠报表
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
source-git-commit: 6cc1351c3a84d4d2219f33ef6175f182b9641377
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# 特质到特质重叠报表{#trait-to-trait-overlap-report}

返回有关您的所有第一方和第三方特征之间共享的独特用户数的数据。

>[!NOTE]
>
>Audience Manager中的重叠报表遵循RBAC原则。 您只能根据您所属的[RBAC用户组](/help/using/features/administration/administration-overview.md)，查看您有权访问的数据源中的特征。

<!-- 

c_overlap_reports.xml

 -->

## 概述

[!UICONTROL Trait-to-Trait Overlap]报表返回有关所有您自己的特征与第三方特征之间共享的独特用户百分比的数据。 作为优化工具，此报表可帮助您：

* 根据您的需求，创建具有高重叠或低重叠的区段。 具有高重叠的特征可为您提供目标受众，但独特访客较少。 重叠程度较低的特征对于访问较大的独特访客集很有用。
* 验证第三方特征数据：相似的第一方和第三方特征之间高度重叠，这表示数据合作伙伴提供的特征准确且可信。 相反，重叠程度较低可能表示第三方特征实际上可能包含的信息与您自己的类似的第一方特征不相同。
* 找到特征之间意外的重叠，然后使用该信息来构建创新区段。

## 示例报告

下图提供了[!UICONTROL Trait-to-Trait Overlap]报表中元素的高级概述。

>[!NOTE]
>
>[!UICONTROL Trait-to-Trait Overlap]报告将相同特征与其自身进行比较时返回空字段。

>[!NOTE]
>
>在特质到特质重叠报表中，无法对文件夹特质进行比较。 通过使用特定文件夹特征创建区段，您可以通过[区段到特征重叠报表](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md)执行分析。

![](assets/trait-to-trait-overlap.png)

## 向下展开单个数据点

选择单个点以在弹出窗口中查看数据详细信息。 您的单击操作会自动更新报告中显示的数据。

## 定义的特征到特征重叠数据Pop字段 {#field-definitions}

描述单击单个数据点时弹出式窗口中显示的量度。

<!-- 

r_t2t_data_pop.xml

 -->

[!UICONTROL Trait-to-Trait Overlap]报表的弹出窗口包含下列量度。 请注意，表中的唯一量度表示您的&#x200B;*实时用户*。

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">重叠%</span></b> </td> 
   <td colname="col2"> 显示比较的特征之间的唯一重叠百分比（重叠唯一值/特征唯一值）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">数据Source类型</span></b> </td> 
   <td colname="col2">定义特征所属的数据源类型。 可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一方（您自己的特征）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方（来自外部数据合作伙伴/供应商）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">重叠的特征ID</span></b> </td> 
   <td colname="col2"> 重叠特征的唯一数值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">重叠的特征名称</span></b> </td> 
   <td colname="col2"> 重叠特征的名称。 </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle">特征ID 2</span></b> </td> 
   <td colname="col2"> 基础数据源中特征的唯一数值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">特征名称2</span></b> </td> 
   <td colname="col2"> 基础数据源中的特征名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">个重叠唯一值</span></b> </td> 
   <td colname="col2"> <p>要获取重叠%，Audience Manager使用以下公式：</p> <p>重叠唯一性/（基本特征唯一性+重叠特征唯一性 — 重叠唯一性）</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">个重叠特征唯一值</span></b> </td> 
   <td colname="col2"> 来自重叠特征的独特访客数。 </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle">基本特征唯一值</span></b> </td> 
   <td colname="col2"> 基本特征中的独特访客数。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用数据滑块筛选报表结果](../../reporting/dynamic-reports/data-sliders.md)
>* [动态报告中使用的形状、颜色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [报告图标和工具说明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报表：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [选定Audience Manager报表中的数据取样率和错误率……](../../reporting/report-sampling.md)
>* [重叠报表的 CSV 文件](../../reporting/dynamic-reports/overlap-csv-files.md)
