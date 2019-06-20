---
description: 返回在您的第一方和第三方特征之间共享的唯一用户数量数据。
seo-description: 返回在您的第一方和第三方特征之间共享的唯一用户数量数据。
seo-title: 特质到特质重叠报表
solution: Audience Manager
title: 特质到特质重叠报表
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
translation-type: tm+mt
source-git-commit: 4dc8aad623198cbc24c5c76ac3818d7ee00e9a5e

---


# 特质到特质重叠报表{#trait-to-trait-overlap-report}

返回在您的第一方和第三方特征之间共享的唯一用户数量数据。

>[!NOTE]
>
>Audience Manager中的重叠报告遵循CLUAC原则。You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_overlap_reports.xml

 -->

## 概述

[!UICONTROL Trait-to-Trait Overlap] 报告返回在您自己的所有特征和第三方特征之间共享的唯一用户的数据。作为优化工具，此报告可帮助您：

* 根据需要创建高重叠或低重叠的细分。重叠的特征可为您提供目标受众，但访客数量较少。低重叠的特征对于到达较大、独特的访客集很有用。
* 验证第三方特征数据：相似的第一方和第三方特征之间的强烈重叠表示数据合作伙伴的特征是准确可信的。相反，低重叠可能表示第三方特征实际上并不包含与您自己相似的第一方特征。
* 发现特征之间的意外重叠，并使用这些信息构建创新细分。

## 示例报告

The following illustration provides a high-level overview of elements in the [!UICONTROL Trait-to-Trait Overlap] report.

>[!NOTE]
>
>[!UICONTROL Trait-to-Trait Overlap] 报表将同一特征与其自身比较时返回一个空字段。

![](assets/trait-to-trait-overlap.png)

## 深入了解各个数据点

选择单个点可在弹出窗口中查看数据详细信息。单击操作会自动更新报告中显示的数据。

## Trait-to-Trait Overlap Data Pop Fields Defined {#field-definitions}

在单击单个数据点时，描述弹出窗口中显示的量度。

<!-- 

r_t2t_data_pop.xml

 -->

[!UICONTROL Trait-to-Trait Overlap] 报告的弹出窗口包含以下指标。Note that the uniques metric in the table represents your *real-time users*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 数据提供程序名称</span></b> </td> 
   <td colname="col2"> 特征所有者的名称。 </td> 
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
   <td colname="col1"><b><span class="wintitle"> 特征ID</span></b> </td> 
   <td colname="col2"> 该特征的唯一数字ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特征名称</span></b> </td> 
   <td colname="col2"> 特征的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重叠%</span></b> </td> 
   <td colname="col2"> 显示比较特征之间唯一重叠的百分比(重叠Unicons/特征统一)。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重叠统一</span></b> </td> 
   <td colname="col2"> <p>要获得重叠%，Audience Manager使用以下公式：</p> <p>重叠的唯一节点/(基本区段统一+重叠区段统一-重叠的唯一等式)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特征统一</span></b> </td> 
   <td colname="col2"> 特征中唯一访客的数量。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [使用数据滑块过滤报告结果](../../reporting/dynamic-reports/data-sliders.md)
>* [动态报告中使用的形状、颜色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [报告图标和工具说明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报告：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [选定Audience Manager报告中的数据采样和错误率…](../../reporting/report-sampling.md)
>* [重叠报告的CSV文件](../../reporting/dynamic-reports/overlap-csv-files.md)