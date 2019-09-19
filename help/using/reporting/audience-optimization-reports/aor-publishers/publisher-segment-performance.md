---
description: “区段性能”报表会按印象和实时区段唯一值比较映射的和未映射的区段。 映射的区段是您创建的区段，并将其发送到目标以进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 在报告内和报告之间比较这些不同的细分类型可以帮助您优化现有营销活动，并找到您可能希望发送到目标定位的被忽略的细分。
seo-description: “区段性能”报表会按印象和实时区段唯一值比较映射的和未映射的区段。 映射的区段是您创建的区段，并将其发送到目标以进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 在报告内和报告之间比较这些不同的细分类型可以帮助您优化现有营销活动，并找到您可能希望发送到目标定位的被忽略的细分。
seo-title: 细分绩效报告
solution: Audience Manager
title: 细分绩效报告
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 细分绩效报告{#segment-performance-report}

“区段性能”报表会按印象和实时区段唯一值比较映射的和未映射的区段。

映射的区段是您创建的区段，并将其发送到目标以进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。

在报告内和报告之间比较这些不同的细分类型可以帮助您优化现有营销活动，并找到您可能希望发送到目标定位的被忽略的细分。

## 用例 {#use-cases}

通过报 [!UICONTROL Segment Performance] 告，您可以：

* 识别驱动规模或业绩的映射受众细分。
* 根据受众对过去业绩的贡献，确定未映射的细分，以在将来的营销活动中引入。

## 使用细分绩效报告 {#using-segment-performance-report}

在和之 **[!UICONTROL Mapped]** 间切 **[!UICONTROL Unmapped]** 换以选择映射到或不映射到目标的区段。 选择 **[!UICONTROL All]** 以在报告中包含所有区段。

使用“ **日期范围** ”和“ **** 日期穿透”控件调整回顾范围。 请注意，7天和30天回顾期仅适用于星期日日期。

使用 **[!UICONTROL Line Item]** 下拉框选择要返回其信息的Web属性。

在下拉 **[!UICONTROL Segment Data Source]** 框中，选择包含要在报表中查看的区段的数据源。

使用下 **[!UICONTROL Segment]** 拉框选择要在报表中查看的区段。

>[!IMPORTANT]
>
>启用此 [!UICONTROL Audience Optimization for Publishers]项后，您必须包含描述性元数据， [!UICONTROL Line Item IDs]如将DFP数据文件导入Audience manager的 [步骤3中所述](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 通过执行此操作，您可以确保报告将Web属性详细 [!UICONTROL Line Item] 化为 [!UICONTROL Line Item ID]。

## 解释结果 {#interpreting-results}

您 [!UICONTROL Segment Performance] 的报告可能与以下报告类似。 在报表中，单击气泡图可查看基础数据。 有关示例报告下表中的其他信息，请参阅说明。

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
   <td colname="col1"> <p> 行项目 </p> </td> 
   <td colname="col2"> <p>要查看此报告的Web属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>点击次数 </p> </td> 
   <td colname="col2"> <p>此特征的成员单击Web属性中项的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>展示次数 </p> </td> 
   <td colname="col2"> <p>此特征的成员暴露给您的库存的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>点进率. </p> <p>此度量中继点击后的展示次数百分比。 将点击数除以展示次数以获取此量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>实时细分填充 </p> </td> 
   <td colname="col2"> <p>在指定时间范围内实时查看的唯一访客的实际数量，以及在 <span class="keyword"> Audience Manager查看时符合区段资格的访客数</span>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何阅读映射的区段结果 {#read-mapped-segment}

您在报表中映射的区段的位置可以告诉您许多关于哪些区段表现良好以及可能需要做出一些调整的位置。

要阅读报告，有助于将结果分为四个部分，其中虚线（以红色表示）和类别如下面的示例报告所示。 示例中的标签可以帮助您了解细分性能以及如何响应这些结果。

![](assets/publisher_segment_performance_mapped.png)

## 如何阅读未映射的区段结果 {#read-unmapped-segment}

在报表中查看未映射的 [!UICONTROL Segment Performance] 区段是查找尚未考虑定位的新区段的极好方法。 事实上，其中某些区段的表现可能优于映射的区段。

要阅读此报告，将结果分为四个部分，其中虚线（以红色表示）和类别如下面的示例报告所示。

![](assets/publisher_segment_performance_unmapped.png)
