---
description: “区段性能”报表会按展示次数和实时区段独特数比较已映射和未映射的区段。 映射的区段是您创建的区段，并将其发送到目标进行定位。 未映射的区段是您创建但尚未发送到目标进行定位的区段。 在报表内和报表之间比较这些不同的区段类型有助于优化现有促销活动，并查找可能希望发送到目标进行定位的被忽视的区段。
seo-description: “区段性能”报表会按展示次数和实时区段独特数比较已映射和未映射的区段。 映射的区段是您创建的区段，并将其发送到目标进行定位。 未映射的区段是您创建但尚未发送到目标进行定位的区段。 在报表内和报表之间比较这些不同的区段类型有助于优化现有促销活动，并查找可能希望发送到目标进行定位的被忽视的区段。
seo-title: 区段绩效报表
solution: Audience Manager
title: 发布者的区段性能报表
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Audience Optimization 报表
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 2%

---

# 区段绩效报表{#segment-performance-report}

“区段性能”报表会按展示次数和实时区段独特数比较已映射和未映射的区段。

映射的区段是您创建的区段，并将其发送到目标进行定位。 未映射的区段是您创建但尚未发送到目标进行定位的区段。

在报表内和报表之间比较这些不同的区段类型有助于优化现有促销活动，并查找可能希望发送到目标进行定位的被忽视的区段。

## 用例 {#use-cases}

通过[!UICONTROL Segment Performance]报表，您可以：

* 识别可提高规模或性能的已映射受众区段。
* 根据受众对过去效果的贡献，确定要在未来促销活动中引入的未映射区段。

## 使用区段性能报表{#using-segment-performance-report}

在&#x200B;**[!UICONTROL Mapped]**&#x200B;和&#x200B;**[!UICONTROL Unmapped]**&#x200B;之间切换，以选择是否映射到目标的区段。 选择&#x200B;**[!UICONTROL All]**&#x200B;以在报表中包含您的所有区段。

使用&#x200B;**日范围**&#x200B;和&#x200B;**日期至**&#x200B;控件调整回顾范围。 请注意，7天和30天的回顾时段仅适用于星期日日期。

使用&#x200B;**[!UICONTROL Line Item]**&#x200B;下拉框选择要返回其信息的Web属性。

在&#x200B;**[!UICONTROL Segment Data Source]**&#x200B;下拉框中，选择包含要在报表中查看的区段的数据源。

使用&#x200B;**[!UICONTROL Segment]**&#x200B;下拉框选择要在报表中查看的区段。

>[!IMPORTANT]
>
>启用[!UICONTROL Audience Optimization for Publishers]时，必须包含[!UICONTROL Line Item IDs]的描述性元数据，如[将Google Ad Manager（以前称为DFP）数据文件导入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步骤3中所述。 通过执行此操作，您可以确保报告将Web属性详细描述为[!UICONTROL Line Item]，而不是[!UICONTROL Line Item ID]。

## 解释结果{#interpreting-results}

您的[!UICONTROL Segment Performance]报表可能与下面的报表类似。 在报表中，单击气泡以查看基础数据。 有关其他信息，请参阅示例报表下表中的说明。

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
   <td colname="col2"> <p>您看到此报表的Web属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>点击次数 </p> </td> 
   <td colname="col2"> <p>此特征的成员点击您Web属性中项目的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>展示次数 </p> </td> 
   <td colname="col2"> <p>此特征的成员被显示到您的库存中的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>点进率. </p> <p>此量度中继展示次数的百分比，后跟点击次数。 将点击次数除以展示次数，以获取此量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>实时区段填充 </p> </td> 
   <td colname="col2"> <p>在指定的时间范围内实时查看的独特访客数，以及当<span class="keyword">Audience Manager</span>看到符合区段资格条件的独特访客数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何读取映射的区段结果{#read-mapped-segment}

映射的区段在报表中的位置可以告诉您许多有关哪些区段表现良好以及可能需要进行一些调整的位置。

要阅读报告，有助于将结果分为四个部分，其中包含虚线（以红色表示）和下面示例报告中显示的类别。 示例中的标签可帮助您了解区段性能以及如何响应这些结果。

![](assets/publisher_segment_performance_mapped.png)

## 如何读取未映射的区段结果{#read-unmapped-segment}

在[!UICONTROL Segment Performance]报表中查看未映射的区段是查找未考虑进行定位的新区段的绝佳方法。 事实上，其中某些区段的表现可能优于映射的区段。

要阅读此报告，有助于将结果分为四个部分，其中虚线（以红色表示）和类别显示在下面的示例报告中。

![](assets/publisher_segment_performance_unmapped.png)
