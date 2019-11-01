---
description: 返回关于在您的所有第一方和第三方特征之间共享的唯一用户数的数据。
seo-description: 返回关于在您的所有第一方和第三方特征之间共享的唯一用户数的数据。
seo-title: 特质到特质重叠报表
solution: Audience Manager
title: 特质到特质重叠报表
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 特质到特质重叠报表{#trait-to-trait-overlap-report}

返回关于在您的所有第一方和第三方特征之间共享的唯一用户数的数据。

>[!NOTE]
>
>Audience manager中的Overlap报告遵循RBAC原则。 您只能根据您所属的 [RBAC用户组来查看您有权访问的数据源中的特征](/help/using/features/administration/administration-overview.md) 。

<!-- 

c_overlap_reports.xml

 -->

## 概述

该报 [!UICONTROL Trait-to-Trait Overlap] 告返回关于在您所有自己的特征和您的第三方特征之间共享的唯一用户百分比的数据。 作为优化工具，此报告可帮助您：

* 根据您的需求创建重叠程度高或低的区段。 重叠程度高的特征可为您提供目标受众，但唯一访客数量较少。 重叠度低的特征有助于访问更大的唯一访客集。
* 验证第三方特征数据：相似的第一方特征和第三方特征之间的强烈重叠表明您的数据合作伙伴的特征准确可靠。 相反，低重叠度表示第三方特征实际上可能并不包含与您自己的类似第一方特征相同的信息。
* 发现特征之间意外的重叠，并使用该信息构建创新细分。

## 示例报告

下图提供了报告中元素的高级概 [!UICONTROL Trait-to-Trait Overlap] 述。

>[!NOTE]
>
>将 [!UICONTROL Trait-to-Trait Overlap] 同一特征与自身进行比较时，报表返回空字段。

![](assets/trait-to-trait-overlap.png)

## 对单个数据点进行向下钻取

选择单个点以在弹出窗口中查看数据详细信息。 单击操作会自动更新报告中显示的数据。

## 特征到特征重叠数据弹出字段已定义 {#field-definitions}

描述单击单个数据点时在弹出窗口中显示的量度。

<!-- 

r_t2t_data_pop.xml

 -->

报告的弹出窗 [!UICONTROL Trait-to-Trait Overlap] 口包含以下指标。 请注意，表中的唯一指标代表您 *的实时用户*。

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 数据提供者名称</span></b> </td> 
   <td colname="col2"> 特征所有者的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 数据提供者类型</span></b> </td> 
   <td colname="col2">定义特征所属的提供程序类型。 可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一方（您自己的特质）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方（来自外部数据合作伙伴／供应商）。 </li> 
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
   <td colname="col2"> 显示比较特征（重叠唯一值／特征唯一值）之间唯一重叠的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重叠单值</span></b> </td> 
   <td colname="col2"> <p>要获得重叠百分比，Audience manager使用以下公式：</p> <p>重叠单值/（基本段单值+重叠段单值——重叠单值）</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特征唯一值</span></b> </td> 
   <td colname="col2"> 特征中的唯一访客数。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用数据滑块过滤报告结果](../../reporting/dynamic-reports/data-sliders.md)
>* [动态报表中使用的形状、颜色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [说明的报表图标和工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报告：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [所选Audience Manager报告中的数据采样和错误率……](../../reporting/report-sampling.md)
>* [重叠报告的CSV文件](../../reporting/dynamic-reports/overlap-csv-files.md)