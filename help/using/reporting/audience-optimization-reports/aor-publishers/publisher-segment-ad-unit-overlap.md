---
description: “区段到广告单元重叠”报告以热图表形式显示，突出显示广告单元与Audience Manager区段之间的高重叠和低重叠。
seo-description: “区段到广告单元重叠”报告以热图表形式显示，突出显示广告单元与Audience Manager区段之间的高重叠和低重叠。
seo-title: 区段到广告单元重叠
solution: Audience Manager
title: 区段到广告单元重叠
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 4%

---


# 区段到广告单元重叠{#segment-to-ad-unit-overlap}

“区段到广告单元重叠”报告以热图表形式显示，突出显示广告单元与Audience Manager区段之间的高重叠和低重叠。

## 用例 {#use-cases}

通过报 [!UICONTROL Segment to Ad Unit Overlap] 告，您可以了解哪些受众访问您的Web资产。 此报告显示区段成员与 [!DNL Audience Manager] Web属性访客数的重叠。 重叠率越高，表示区段的许多成员都会访问您的Web资产。

## 使用区段添加设备重叠报表 {#using-the-report}

使用和 **[!UICONTROL Top N Ad Units]** 控 **[!UICONTROL Top N Segments]** 件为重叠选择所需数量的广告单位和区段。 每个项目最多可选择100个项目。

使用“ **日期范围** ” **和“通** 过日期”控件调整回顾范围。 请注意，7天和30天回顾期仅适用于星期日日期。

使用和 **[!UICONTROL Segment Name]** 框可 **[!UICONTROL Ad Unit]** 以过滤任何区段和广告单元。

>[!IMPORTANT]
>
>启用时， [!UICONTROL Audience Optimization for Publishers]必须包含描述性元数据， [!UICONTROL Ad Unit IDs]如将Google Ad Manager( [以前称为DFP)数据文件导入Audience Manager的步骤3中所述](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 通过执行此操作，您可以确保报告将Web属性详细 [!UICONTROL Ad Unit] 化为而非 [!UICONTROL Ad Unit ID]。

## 解释结果 {#interpreting-results}

您 [!UICONTROL Segment to Ad Unit Overlap] 的报告可能与下面的报告类似。 将鼠标悬停在任何单元格上可获得有关该特定重叠的详细信息。 有关其他信息，请参阅示例报告下表中的说明。

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
   <td colname="col1"> <p><span class="wintitle"> 广告单元 </span> </p> </td> 
   <td colname="col2"> <p>库存物料的名称。 例如，这可以是您的网站之一或您网站上的文章。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 细分实时唯一值计数</span> </p> </td> 
   <td colname="col2"> <p>在指定的时间范围内实时查看的唯一访客数，以及在Audience Manager看到区段时符合此区段条件的 <span class="keyword"> 数</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 广告单位唯一值计数</span> </p> </td> 
   <td colname="col2"> <p>此特定广告单元的访客数。 此信息从Google Ad Manager日志中提取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠唯一值计数</span> </p> </td> 
   <td colname="col2"> <p>您区段中接触到广告单元项的成员。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重叠百分比</span> </p> </td> 
   <td colname="col2"> <p>广告单位和细分群体之间的重叠。 这是重叠 <span class="wintitle"> 唯一值计数</span>，以段实时唯一值的 <span class="wintitle"> 百分比表示</span>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

