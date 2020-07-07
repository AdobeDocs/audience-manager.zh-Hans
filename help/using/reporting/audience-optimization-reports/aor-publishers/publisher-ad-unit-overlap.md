---
description: “广告单元重叠”报告以热图形式显示，突出显示广告单元之间的高重叠和低重叠。
seo-description: “广告单元重叠”报告以热图形式显示，突出显示广告单元之间的高重叠和低重叠。
seo-title: 广告单元重叠
solution: Audience Manager
title: 广告单元重叠
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 3%

---


# 广告单元重叠{#ad-unit-overlap}

报 **[!UICONTROL Ad Unit Overlap]** 告将以热度图形显示，突出显示广告单元之间的高重叠和低重叠。

## 用例 {#use-cases}

通过报 **[!UICONTROL Ad Unit Overlap]** 告，您可以深入了解受众在Web属性中的重叠位置。 该报告考虑您的100个顶级相关属性，并显示它们之间的重叠。

## 使用广告单位重叠报表 {#using-the-report}

使用和 **[!UICONTROL Top N Base Ad Units]** 控 **[!UICONTROL Top N Overlapping Ad Units]** 件为重叠选择所需数量的广告单位。 每个项目最多可选择100个项目。

使用“ **日期范围** ” **和“通** 过日期”控件调整回顾范围。 请注意，7天和30天回顾期仅适用于星期日日期。

使用 **[!UICONTROL Base Ad Unit]** 和控 **[!UICONTROL Overlap Ad Unit]** 件选择要在重叠报告中显示的广告单元。

>[!IMPORTANT]
>
>启用时， [!UICONTROL Audience Optimization for Publishers]必须包含描述性元数据， [!UICONTROL Ad Unit IDs]如将Google Ad Manager( [以前称为DFP)数据文件导入Audience Manager的步骤3中所述](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 通过执行此操作，您可以确保报告将Web属性详细 [!UICONTROL Ad Unit] 化为而非 [!UICONTROL Ad Unit ID]。

## 解释结果 {#interpreting-results}

您 [!UICONTROL Ad Unit Overlap] 的报告可能与下面的报告类似。 将鼠标悬停在任何单元格上可获得有关该特定重叠的详细信息。 有关其他信息，请参阅示例报告下表中的说明。

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
   <td colname="col1"> <p><span class="wintitle"> 重叠广告单元</span> </p> </td> 
   <td colname="col2"> <p>库存物料的名称。 例如，这可以是您的网站之一或您网站上的文章。 在上图中，基本广告单位为第9条至第18条。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 基本广告单元</span> </p> </td> 
   <td colname="col2"> <p>库存物料的名称。 例如，这可以是您的网站之一或您网站上的文章。 在上图中，基本广告单位为第1-8条。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠广告单位唯一值计数</span> </p> </td> 
   <td colname="col2"> <p>已访问广告单元项目9 - 18的用户数。 此信息从Google Ad Manager日志中提取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 基本广告单位唯一值计数</span> </p> </td> 
   <td colname="col2"> <p>已访问广告单元项目1 - 8的用户数。 此信息从Google Ad Manager日志中提取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠唯一值计数</span> </p> </td> 
   <td colname="col2"> <p>访问过基本广告单元和重叠广 <span class="wintitle"> 告单元的用户</span><span class="wintitle"> 之间的重叠</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠百分比</span> </p> </td> 
   <td colname="col2"> <p>访问过基本广告单元和重叠广 <span class="wintitle"> 告单元的用户</span><span class="wintitle"> 之间的重叠</span>。 这是重叠 <span class="wintitle"> 唯一值计数</span>，以基本广告单位的百 <span class="wintitle"> 分比表示</span>。 </p> </td> 
  </tr> 
 </tbody> 
</table>
