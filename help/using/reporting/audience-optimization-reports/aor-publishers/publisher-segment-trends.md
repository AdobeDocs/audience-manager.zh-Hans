---
description: “区段趋势”报表会返回一段时间内映射和未映射区段的展示次数和点击率数据。 映射的区段是您创建的区段，并将其发送到目标进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 比较所选量度的趋势和数量，更好地了解受众的行为方式。
seo-description: “区段趋势”报表会返回一段时间内映射和未映射区段的展示次数和点击率数据。 映射的区段是您创建的区段，并将其发送到目标进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 比较所选量度的趋势和数量，更好地了解受众的行为方式。
seo-title: 区段趋势报表
solution: Audience Manager
title: 区段趋势报表
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization Reports
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 3%

---

# 区段趋势报表{#segment-trend-report}

“区段趋势”报表会返回一段时间内映射和未映射区段的展示次数和点击率数据。

映射的区段是您创建的区段，并将其发送到目标进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。

比较所选量度的趋势和数量，更好地了解受众的行为方式。

## 用例 {#use-cases}

使用[!UICONTROL Segment Trend]报告可验证一段时间内的区段性能，并根据强性能或规模找出趋势。

通过此报告，您可以了解哪些Web属性显示有缺陷或有缺陷的增加，并根据需要进行疑难解答。 在您确定[!UICONTROL Segment Performance]报表中的关注受众后，此报告是下一步，以确保您在[!UICONTROL Segment Performance]选项卡中看到的强或弱性能随着时间的推移保持一致。

## 使用区段趋势报表{#using-the-report}

在&#x200B;**[!UICONTROL Mapped]**&#x200B;和&#x200B;**[!UICONTROL Unmapped]**&#x200B;之间切换，以选择映射到或不映射到目标的区段。 选择&#x200B;**[!UICONTROL All]**&#x200B;以在报表中包含您的所有区段。

使用&#x200B;**[!UICONTROL Date Through]**&#x200B;滑块调整回顾窗口。

单击&#x200B;**[!UICONTROL Date Through]**&#x200B;滑块下的任意区段，以显示选项以仅将该区段保留在报表中或将其排除。

使用&#x200B;**[!UICONTROL Line Item]**&#x200B;下拉框选择要返回信息的个人信息中的属性。

在&#x200B;**[!UICONTROL Segment Data Source]**&#x200B;下拉框中，选择包含要在报表中查看的区段的数据源。

使用&#x200B;**[!UICONTROL Segment]**&#x200B;下拉框选择要在报表中查看的区段。

>[!IMPORTANT]
>
>启用[!UICONTROL Audience Optimization for Publishers]时，必须包含[!UICONTROL Line Item] ID的描述性元数据，如[将Google Ad Manager（以前称为DFP）数据文件导入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步骤3中所述。 通过执行此操作，您可以确保报告将web属性详细信息设为[!UICONTROL Line Item]，而不是[!UICONTROL Line Item] ID。

## 解释结果{#interpreting-results}

[!UICONTROL Segment Trend]报表只返回14天间隔的线形图中的数据。 在此示例中，报表显示一组映射和未映射区段的印象和点进趋势。

将鼠标悬停在任何行上可获得有关该特定区段趋势的更多信息。 有关其他信息，请参阅示例报告下表中的说明。

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
   <td colname="col1"> <p><span class="wintitle"> 区段</span> </p> </td> 
   <td colname="col2"> <p>您分配给此区段的字母数字名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 区段ID</span> </p> </td> 
   <td colname="col2"> <p>此区段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 行项目</span> </p> </td> 
   <td colname="col2"> <p>您看到此报表的Web属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 点击次数</span> </p> </td> 
   <td colname="col2"> <p>此特征的成员单击Web属性中项的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 展示次数</span> </p> </td> 
   <td colname="col2"> <p>此特征的成员向您的库存公开的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">CTR</span> </p> </td> 
   <td colname="col2"> <p>点进率. 此量度中继点击后的展示次数百分比。 按展示次数划分点击量以获取此量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 段唯一</span> </p> </td> 
   <td colname="col2"> <p>最近30天内的区段成员数。 </p> </td> 
  </tr> 
 </tbody> 
</table>
