---
description: “区段绩效”报告通过印象和实时细分统一来比较映射的和未映射的区段。映射的区段是您创建的区段，并发送到目标定位。未映射区段是您已创建但尚未发送到目标定位的区段。在报表内和报表之间比较这些不同的细分类型可帮助您优化现有营销活动并找到可能希望发送到目标定位的过度观察的细分。
seo-description: “区段绩效”报告通过印象和实时细分统一来比较映射的和未映射的区段。映射的区段是您创建的区段，并发送到目标定位。未映射区段是您已创建但尚未发送到目标定位的区段。在报表内和报表之间比较这些不同的细分类型可帮助您优化现有营销活动并找到可能希望发送到目标定位的过度观察的细分。
seo-title: 区段绩效报告
solution: Audience Manager
title: 区段绩效报告
uuid: c9a1e ad-4f3f-4334-a3 ff-0f241 c7303 c4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Performance Report{#segment-performance-report}

“区段绩效”报告通过印象和实时细分统一来比较映射的和未映射的区段。

映射的区段是您创建的区段，并发送到目标定位。未映射区段是您已创建但尚未发送到目标定位的区段。

在报表内和报表之间比较这些不同的细分类型可帮助您优化现有营销活动并找到可能希望发送到目标定位的过度观察的细分。

## 用例 {#use-cases}

[!UICONTROL Segment Performance] 通过报告，您可以：

* 确定驱动比例或性能的映射受众细分。
* 根据受众对过去效果的贡献确定未映射的细分，以在未来的营销活动中引入。

## Using the Segment Performance Report {#using-segment-performance-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. 请注意，天和30天回顾期仅可用于星期日日期。

Use the **[!UICONTROL Line Item]** drop-down box to select the web properties for which you want to return information.

In the **[!UICONTROL Segment Data Source]** drop-down box, select the data sources containing the segments you want to see in the report.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item ID].

## Interpreting the Results {#interpreting-results}

[!UICONTROL Segment Performance] 您的报表类似于下面的报告。在报表中，单击气泡以查看基础数据。有关详细信息，请参阅示例报告下表格中的其他信息。

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
   <td colname="col2"> <p>为此区段分配的字母数字名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>区段ID </p> </td> 
   <td colname="col2"> <p>此区段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Line项目 </p> </td> 
   <td colname="col2"> <p>您看到此报告的Web资产。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>点击次数 </p> </td> 
   <td colname="col2"> <p>该特征成员单击Web资产中的项目的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>展示次数 </p> </td> 
   <td colname="col2"> <p>此特征向您的库存公开的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>点进率. </p> <p>此指标计算印象的百分比，之后依次单击。按印象划分点击以获得此指标。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>实时细分群体 </p> </td> 
   <td colname="col2"> <p>The actual number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## How to Read Your Mapped Segment Results {#read-mapped-segment}

在报表中映射区段的位置可以告诉您哪些细分效果不错，以及您可能需要做些调整。

要阅读报表，可以使用假设线(红色)以及下面示例报告中显示的类别将结果分为四个部分。示例中的标签可以帮助您了解细分性能以及如何响应这些结果。

![](assets/publisher_segment_performance_mapped.png)

## How to Read Your Unmapped Segment Results {#read-unmapped-segment}

Looking at unmapped segments in a [!UICONTROL Segment Performance] report is a great way to find new segments you haven&#39;t considered for targeting. 事实上，其中部分区段可能超出您的映射区段。

要阅读此报告，可以使用以下示例报告中显示的虚构线(红色)和类别将结果分为四个部分。

![](assets/publisher_segment_performance_unmapped.png)
