---
description: “区段到广告单位重叠”报表显示为热图，突出显示广告单位和Audience Manager区段之间的高和低重叠。
seo-description: “区段到广告单位重叠”报表显示为热图，突出显示广告单位和Audience Manager区段之间的高和低重叠。
seo-title: 区段到广告单元重叠
solution: Audience Manager
title: 区段到广告单元重叠
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 5%

---

# 区段到广告单元重叠{#segment-to-ad-unit-overlap}

“区段到广告单位重叠”报表显示为热图，突出显示广告单位和Audience Manager区段之间的高和低重叠。

## 用例 {#use-cases}

通过[!UICONTROL Segment to Ad Unit Overlap]报表，您可以了解哪些受众访问您的Web属性。 该报表显示[!DNL Audience Manager]区段成员之间的重叠以及Web属性的访客数。 重叠程度越高，表示某个区段的许多成员都会访问您的Web资产。

## 使用区段以添加设备重叠报表{#using-the-report}

使用&#x200B;**[!UICONTROL Top N Ad Units]**&#x200B;和&#x200B;**[!UICONTROL Top N Segments]**&#x200B;控件为重叠选择所需数量的广告单位和区段。 每个项目最多可选择100个项目。

使用&#x200B;**日范围**&#x200B;和&#x200B;**日期至**&#x200B;控件调整回顾范围。 请注意，7天和30天回顾期仅适用于星期日日期。

使用&#x200B;**[!UICONTROL Segment Name]**&#x200B;和&#x200B;**[!UICONTROL Ad Unit]**&#x200B;框过滤任意区段和广告单位。

>[!IMPORTANT]
>
>启用[!UICONTROL Audience Optimization for Publishers]时，必须包含[!UICONTROL Ad Unit IDs]的描述性元数据，如[将Google Ad Manager（以前称为DFP）数据文件导入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步骤3中所述。 通过执行此操作，您可以确保报告将web属性详细描述为[!UICONTROL Ad Unit]而不是[!UICONTROL Ad Unit ID]。

## 解释结果{#interpreting-results}

您的[!UICONTROL Segment to Ad Unit Overlap]报表可能与下面报表类似。 将鼠标悬停在任何单元格上可获得有关该特定重叠的详细信息。 有关其他信息，请参阅示例报告下表中的说明。

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
   <td colname="col1"> <p><span class="wintitle"> 广告单位  </span> </p> </td> 
   <td colname="col2"> <p>库存物料的名称。 例如，这可以是您的网站之一或您网站上的文章。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 区段实时唯一值计数</span> </p> </td> 
   <td colname="col2"> <p>在指定时间范围内实时查看的唯一访客数，以及在<span class="keyword">Audience Manager</span>查看时符合区段条件的唯一数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 广告单位计数</span> </p> </td> 
   <td colname="col2"> <p>此特定广告单元的访客数。 此信息会从Google广告管理器日志中提取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠唯一值计数</span> </p> </td> 
   <td colname="col2"> <p>向广告单元项目公开的区段成员。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠百分比</span> </p> </td> 
   <td colname="col2"> <p>广告单位和细分群体之间的重叠。 这是<span class="wintitle">重叠唯一值计数</span>，表示为<span class="wintitle">区段实时唯一值</span>的百分比。 </p> </td> 
  </tr> 
 </tbody> 
</table>
