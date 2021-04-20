---
description: 返回关于在您的所有第一方和第三方特征之间共享的唯一用户数的数据。
seo-description: 返回关于在您的所有第一方和第三方特征之间共享的唯一用户数的数据。
seo-title: 特征到特征重叠报表
solution: Audience Manager
title: 特征到特征重叠报表
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 8%

---

# 特征到特征重叠报表{#trait-to-trait-overlap-report}

返回关于在您的所有第一方和第三方特征之间共享的唯一用户数的数据。

>[!NOTE]
>
>Audience Manager中的Overlap报表遵循RBAC原则。 您只能根据您所属的[RBAC用户组](/help/using/features/administration/administration-overview.md)查看您有权访问的数据源中的特征。

<!-- 

c_overlap_reports.xml

 -->

## 概述

[!UICONTROL Trait-to-Trait Overlap]报表返回所有您自己的特征和第三方特征之间共享的唯一用户百分比数据。 作为优化工具，此报表可帮助您：

* 根据您的需求创建重叠度高或低的区段。 重叠度高的特征可为您提供目标受众，但独特访客较少。 重叠度低的特征有助于达到更大、唯一的访客集。
* 验证第三方特征数据：相似的第一方和第三方特征之间的强烈重叠表明，您数据合作伙伴提供的特征准确可靠。 相反，低重叠可能表示第三方特征实际上可能与您自己的类似第一方特征包含的信息不同。
* 发现特征之间意外的重叠，并使用该信息构建创新细分。

## 示例报告

下图提供了[!UICONTROL Trait-to-Trait Overlap]报表中元素的高级概述。

>[!NOTE]
>
>当[!UICONTROL Trait-to-Trait Overlap]报表将同一特征与自身进行比较时，它返回一个空字段。

![](assets/trait-to-trait-overlap.png)

## 深入查看各个数据点

在弹出窗口中选择视图数据详细信息的单个点。 您的点击操作会自动更新报表中显示的数据。

## 已定义特征到特征重叠数据弹出字段{#field-definitions}

描述在单击单个数据点时在弹出窗口中显示的量度。

<!-- 

r_t2t_data_pop.xml

 -->

[!UICONTROL Trait-to-Trait Overlap]报表的弹出窗口包含以下量度。 请注意，表中的唯一值量度表示您的&#x200B;*实时用户*。

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重叠%</span></b> </td> 
   <td colname="col2"> 显示比较特征（重叠唯一值/特征唯一值）之间唯一重叠的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 数据源类型</span></b> </td> 
   <td colname="col2">定义特征所属的数据源类型。 可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一方（您自己的特质）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方（来自外部数据合作伙伴/供应商）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重叠特征ID</span></b> </td> 
   <td colname="col2"> 重叠特征的唯一数字ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重叠的特征名称</span></b> </td> 
   <td colname="col2"> 重叠特征的名称。 </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 特征ID 2</span></b> </td> 
   <td colname="col2"> 基本数据源中特征的唯一数字ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特征名称2</span></b> </td> 
   <td colname="col2"> 基本数据源中特征的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重叠单值</span></b> </td> 
   <td colname="col2"> <p>要获取重叠%,Audience Manager使用以下公式：</p> <p>重叠单值/（基本特征单值+重叠特征单值 — 重叠单值）</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重叠特征唯一值</span></b> </td> 
   <td colname="col2"> 重叠特征中的唯一访客数。 </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 基本特征单值</span></b> </td> 
   <td colname="col2"> 基特征中的唯一访客数。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用数据滑块筛选报表结果](../../reporting/dynamic-reports/data-sliders.md)
>* [动态报表中使用的形状、颜色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [说明报表图标和工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报表：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [选定 Audience Manager 报表中的数据取样率和错误率...](../../reporting/report-sampling.md)
>* [重叠报表的 CSV 文件](../../reporting/dynamic-reports/overlap-csv-files.md)

