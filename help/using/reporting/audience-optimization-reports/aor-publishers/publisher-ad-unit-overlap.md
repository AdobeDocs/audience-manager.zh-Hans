---
description: 广告单位重叠报表以热度图显示，突出显示广告单位之间的高重叠和低重叠。
seo-description: The Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.
seo-title: Ad Unit Overlap
solution: Audience Manager
title: 广告单元重叠
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Audience Optimization Reports
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# 广告单元重叠{#ad-unit-overlap}

**[!UICONTROL Ad Unit Overlap]**&#x200B;报告显示为热度图，突出显示广告单位之间的高重叠和低重叠。

## 用例 {#use-cases}

通过&#x200B;**[!UICONTROL Ad Unit Overlap]**&#x200B;报表，您可以深入了解受众在Web资产中的重叠位置。 该报表会考虑您的100个热门相关属性，并显示它们之间的重叠。

## 使用广告单位重叠报表 {#using-the-report}

使用&#x200B;**[!UICONTROL Top N Base Ad Units]**&#x200B;和&#x200B;**[!UICONTROL Top N Overlapping Ad Units]**&#x200B;控件为重叠选择所需的广告单位数。 每项最多可选择100个项目。

使用&#x200B;**日期范围**&#x200B;和&#x200B;**日期到**&#x200B;控件调整您的回顾范围。 请注意，7天和30天回顾期间仅适用于星期日日期。

使用&#x200B;**[!UICONTROL Base Ad Unit]**&#x200B;和&#x200B;**[!UICONTROL Overlap Ad Unit]**&#x200B;控件选择要显示在重叠报表中的广告单位。

>[!IMPORTANT]
>
>启用[!UICONTROL Audience Optimization for Publishers]时，必须包括[!UICONTROL Ad Unit IDs]的描述性元数据，如[将Google广告管理器（以前为DFP）数据文件导入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步骤3中所述。 通过这样做，您可以确保报告将Web属性详细视为[!UICONTROL Ad Unit]，而不是[!UICONTROL Ad Unit ID]。

## 解释结果 {#interpreting-results}

您的[!UICONTROL Ad Unit Overlap]报表可能类似于下面的报表。 将鼠标悬停在任何单元格上可获得有关特定重叠的详细信息。 请参阅示例报表下表中其他信息的说明。

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
   <td colname="col1"> <p><span class="wintitle">重叠广告单元</span> </p> </td> 
   <td colname="col2"> <p>库存项目的名称。 例如，这可以是您的某个网站或您网站上的文章。 在上图中，基本广告单位为第9-18条。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">基本广告单元</span> </p> </td> 
   <td colname="col2"> <p>库存项目的名称。 例如，这可以是您的某个网站或您网站上的文章。 在上图中，基本广告单位为第1-8条。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">重叠广告单元独特计数</span> </p> </td> 
   <td colname="col2"> <p>访问广告单元项目9 - 18的用户数。 此信息提取自Google广告管理器日志。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">个基本广告单元唯一计数</span> </p> </td> 
   <td colname="col2"> <p>访问广告单元项目1 - 8的用户数。 此信息提取自Google广告管理器日志。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">个重叠唯一计数</span> </p> </td> 
   <td colname="col2"> <p>访问了<span class="wintitle">基本广告单元</span>和<span class="wintitle">重叠广告单元</span>的用户之间的重叠。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">重叠百分比</span> </p> </td> 
   <td colname="col2"> <p>访问了<span class="wintitle">基本广告单元</span>和<span class="wintitle">重叠广告单元</span>的用户之间的重叠。 这是<span class="wintitle">重叠唯一计数</span>，以占<span class="wintitle">基本广告单元</span>的百分比表示。 </p> </td> 
  </tr> 
 </tbody> 
</table>
