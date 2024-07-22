---
description: 区段性能报表按展示次数和实时区段唯一性比较已映射和未映射的区段。 映射的区段是指您创建并发送到目标进行定位的区段。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 比较报表内和报表之间的这些不同区段类型有助于优化现有促销活动，并查找您可能希望发送到目标位置以进行定位的被忽略的区段。
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and Real-Time Segment Uniques. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: 发布者的区段性能报表
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Audience Optimization Reports
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---

# 区段绩效报表{#segment-performance-report}

区段性能报表按展示次数和实时区段唯一性比较已映射和未映射的区段。

映射的区段是指您创建并发送到目标进行定位的区段。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。

比较报表内和报表之间的这些不同区段类型有助于优化现有促销活动，并查找您可能希望发送到目标位置以进行定位的被忽略的区段。

## 用例 {#use-cases}

通过[!UICONTROL Segment Performance]报告，您可以：

* 确定推动规模或性能的映射受众区段。
* 根据受众对过去表现的贡献，确定要在未来营销活动中引入的未映射区段。

## 使用区段绩效报表 {#using-segment-performance-report}

在&#x200B;**[!UICONTROL Mapped]**&#x200B;和&#x200B;**[!UICONTROL Unmapped]**&#x200B;之间切换以选择是否映射到目标的区段。 选择&#x200B;**[!UICONTROL All]**&#x200B;以在报告中包含您的所有区段。

使用&#x200B;**日期范围**&#x200B;和&#x200B;**日期到**&#x200B;控件调整您的回顾范围。 请注意，7天和30天回顾期间仅适用于星期日日期。

使用&#x200B;**[!UICONTROL Line Item]**&#x200B;下拉框选择要返回其信息的Web属性。

在&#x200B;**[!UICONTROL Segment Data Source]**&#x200B;下拉框中，选择包含要在报表中查看的区段的数据源。

使用&#x200B;**[!UICONTROL Segment]**&#x200B;下拉框选择要在报告中查看的区段。

>[!IMPORTANT]
>
>启用[!UICONTROL Audience Optimization for Publishers]时，必须包括[!UICONTROL Line Item IDs]的描述性元数据，如[将Google广告管理器（以前为DFP）数据文件导入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步骤3中所述。 通过这样做，您可以确保报告将Web属性详细视为[!UICONTROL Line Item]，而不是[!UICONTROL Line Item ID]。

## 解释结果 {#interpreting-results}

您的[!UICONTROL Segment Performance]报表可能类似于下面的报表。 在报表中，单击气泡查看基础数据。 请参阅示例报表下表中其他信息的说明。

![](assets/publisher_segment_performance.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>区段 </p> </td> 
   <td colname="col2"> <p>分配给此区段的字母数字名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>区段ID </p> </td> 
   <td colname="col2"> <p>此区段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行项目 </p> </td> 
   <td colname="col2"> <p>您正在查看其此报表的Web属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>点击次数 </p> </td> 
   <td colname="col2"> <p>此特征成员单击Web属性中的项目的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>展示次数 </p> </td> 
   <td colname="col2"> <p>此特征的成员向您的清单公开的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>点进率。 </p> <p>此量度会中继展示的百分比，然后是点击次数。 将点击次数除以展示次数，以获取此量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>实时区段人口 </p> </td> 
   <td colname="col2"> <p>在指定时间范围内实时查看的实际独特访客数，以及在<span class="keyword">Audience Manager</span>查看这些访客时符合区段资格条件的访客数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何读取映射的区段结果 {#read-mapped-segment}

您的映射区段在报表中的位置可以让您详细了解哪些区段表现良好以及在何处可能需要做出一些调整。

要阅读报告，将结果分成四个部分会很有帮助，四个部分带有假想行（红色）以及下面示例报告中所示的类别。 示例中的标签可帮助您了解区段性能以及如何响应这些结果。

![](assets/publisher_segment_performance_mapped.png)

## 如何读取未映射的区段结果 {#read-unmapped-segment}

查看[!UICONTROL Segment Performance]报表中的未映射区段是查找尚未考虑定位的新区段的好方法。 事实上，其中某些区段的性能可能会优于您的映射区段。

要阅读本报告，将结果分为四个部分会有所帮助，其中虚线（红色）和类别如下面的示例报告中所示。

![](assets/publisher_segment_performance_unmapped.png)
