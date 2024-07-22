---
description: 区段趋势报表会返回一段时间内，已映射和未映射区段的展示次数和点进率数据。 映射的区段是指您创建并发送到目标进行定位的区段。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 比较所选量度的趋势和数量，以更好地了解受众在一段时间内的行为。
seo-description: The Segment Trend report returns data on impressions and click-through rates of mapped and unmapped segments over time. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Compare trends and volume for your selected metrics to get a better picture of how your audiences behave over time.
seo-title: Segment Trend Report
solution: Audience Manager
title: 区段趋势报表
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization Reports
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---

# 区段趋势报表{#segment-trend-report}

区段趋势报表会返回一段时间内，已映射和未映射区段的展示次数和点进率数据。

映射的区段是指您创建并发送到目标进行定位的区段。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。

比较所选量度的趋势和数量，以更好地了解受众在一段时间内的行为。

## 用例 {#use-cases}

使用[!UICONTROL Segment Trend]报表验证区段在一段时间内的性能并根据强大的性能或规模查明趋势。

通过此报表，您可以了解哪些Web属性显示低谷或错误增加，并根据需要进行故障排除。 当您在[!UICONTROL Segment Performance]报表中确定感兴趣的受众后，此报表是下一步，以确保您在[!UICONTROL Segment Performance]选项卡中看到的强劲或低劣性能随着时间的推移保持一致。

## 使用区段趋势报表 {#using-the-report}

在&#x200B;**[!UICONTROL Mapped]**&#x200B;和&#x200B;**[!UICONTROL Unmapped]**&#x200B;之间切换以选择是否映射到目标的区段。 选择&#x200B;**[!UICONTROL All]**&#x200B;以在报告中包含您的所有区段。

使用&#x200B;**[!UICONTROL Date Through]**&#x200B;滑块调整回看窗口期。

单击&#x200B;**[!UICONTROL Date Through]**&#x200B;滑块下的任何区段，可显示相应选项，即在报表中仅保留或排除该区段。

使用&#x200B;**[!UICONTROL Line Item]**&#x200B;下拉框选择项目组合中要返回其信息的属性。

在&#x200B;**[!UICONTROL Segment Data Source]**&#x200B;下拉框中，选择包含要在报表中查看的区段的数据源。

使用&#x200B;**[!UICONTROL Segment]**&#x200B;下拉框选择要在报告中查看的区段。

>[!IMPORTANT]
>
>启用[!UICONTROL Audience Optimization for Publishers]时，必须包括[!UICONTROL Line Item] ID的描述性元数据，如[将Google Ad Manager（以前为DFP）数据文件导入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步骤3中所述。 通过执行此操作，您可以确保报告将Web属性的详细信息显示为[!UICONTROL Line Item]，而不是[!UICONTROL Line Item] ID。

## 解释结果 {#interpreting-results}

[!UICONTROL Segment Trend]报表仅返回14天间隔的折线图数据。 在此示例中，报表显示了一组已映射和未映射区段的展示和点进趋势。

将鼠标悬停在任意线条上可获取有关特定区段趋势的更多信息。 请参阅示例报表下表中其他信息的说明。

![](assets/publisher_segment_trend.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">区段</span> </p> </td> 
   <td colname="col2"> <p>分配给此区段的字母数字名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">区段ID</span> </p> </td> 
   <td colname="col2"> <p>此区段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">行项目</span> </p> </td> 
   <td colname="col2"> <p>您正在查看其此报表的Web属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">次点击</span> </p> </td> 
   <td colname="col2"> <p>此特征成员单击Web属性中的项目的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">展示次数</span> </p> </td> 
   <td colname="col2"> <p>此特征的成员向您的清单公开的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>点进率。 此量度会中继展示的百分比，然后是点击次数。 将点击次数除以展示次数，以获取此量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">区段唯一值</span> </p> </td> 
   <td colname="col2"> <p>过去30天内的区段成员数。 </p> </td> 
  </tr> 
 </tbody> 
</table>
