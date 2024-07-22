---
description: 区段到广告单位重叠报表以热度图显示，突出显示广告单位和Audience Manager区段之间的高重叠和低重叠。
seo-description: The Segment to Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units and Audience Manager segments.
seo-title: Segment to Ad Unit Overlap
solution: Audience Manager
title: 区段到广告单元重叠
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 1%

---

# 区段到广告单元重叠{#segment-to-ad-unit-overlap}

区段到广告单位重叠报表以热度图显示，突出显示广告单位和Audience Manager区段之间的高重叠和低重叠。

## 用例 {#use-cases}

通过[!UICONTROL Segment to Ad Unit Overlap]报表，您可以了解哪些受众访问您的Web资产。 此报表显示[!DNL Audience Manager]区段的成员与Web资产的访客数之间的重叠。 重叠程度越高，意味着区段的许多成员都会访问您的Web资产。

## 使用区段添加单位重叠报表 {#using-the-report}

使用&#x200B;**[!UICONTROL Top N Ad Units]**&#x200B;和&#x200B;**[!UICONTROL Top N Segments]**&#x200B;控件为重叠选择所需的广告单位和区段数。 每项最多可选择100个项目。

使用&#x200B;**日期范围**&#x200B;和&#x200B;**日期到**&#x200B;控件调整您的回顾范围。 请注意，7天和30天回顾期间仅适用于星期日日期。

使用&#x200B;**[!UICONTROL Segment Name]**&#x200B;和&#x200B;**[!UICONTROL Ad Unit]**&#x200B;框筛选任意区段和广告单位。

>[!IMPORTANT]
>
>启用[!UICONTROL Audience Optimization for Publishers]时，必须包括[!UICONTROL Ad Unit IDs]的描述性元数据，如[将Google广告管理器（以前为DFP）数据文件导入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步骤3中所述。 通过这样做，您可以确保报告将Web属性详细视为[!UICONTROL Ad Unit]，而不是[!UICONTROL Ad Unit ID]。

## 解释结果 {#interpreting-results}

您的[!UICONTROL Segment to Ad Unit Overlap]报表可能类似于下面的报表。 将鼠标悬停在任何单元格上可获得有关特定重叠的详细信息。 请参阅示例报表下表中其他信息的说明。

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
   <td colname="col1"> <p><span class="wintitle">广告单元</span> </p> </td> 
   <td colname="col2"> <p>库存项目的名称。 例如，这可以是您的某个网站或您网站上的文章。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">区段实时独特计数</span> </p> </td> 
   <td colname="col2"> <p>在指定时间范围内实时查看的独特访客数，以及在<span class="keyword">Audience Manager</span>看到这些访客时符合区段资格条件的访客数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">广告单元唯一计数</span> </p> </td> 
   <td colname="col2"> <p>此特定广告单位的访客数。 此信息提取自Google广告管理器日志。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">个重叠唯一计数</span> </p> </td> 
   <td colname="col2"> <p>向广告单位项目展示的区段成员。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">重叠百分比</span> </p> </td> 
   <td colname="col2"> <p>广告单位和区段人口之间的重叠。 这是<span class="wintitle">个重叠唯一计数</span>，以占<span class="wintitle">个区段实时唯一计数</span>的百分比表示。 </p> </td> 
  </tr> 
 </tbody> 
</table>
