---
description: “区段趋势”报表会返回一段时间内映射和未映射区段的展示次数和点击率数据。 映射的区段是您创建的区段，并将其发送到目标进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 比较所选指标的趋势和数量，更好地了解受众的行为方式。
seo-description: “区段趋势”报表会返回一段时间内映射和未映射区段的展示次数和点击率数据。 映射的区段是您创建的区段，并将其发送到目标进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 比较所选指标的趋势和数量，更好地了解受众的行为方式。
seo-title: 区段趋势报表
solution: Audience Manager
title: 区段趋势报表
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---


# 区段趋势报表{#segment-trend-report}

“区段趋势”报表会返回一段时间内映射和未映射区段的展示次数和点击率数据。

映射的区段是您创建的区段，并将其发送到目标进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。

比较所选指标的趋势和数量，更好地了解受众的行为方式。

## 用例 {#use-cases}

使用该 [!UICONTROL Segment Trend] 报告验证细分的长期表现，并根据强大的性能或规模查明趋势。

通过此报告，您可以了解哪些Web属性显示缺陷或错误增加，并根据需要进行疑难解答。 此报告是您确定您对报告感兴趣的受众后的下 [!UICONTROL Segment Performance] 一步，旨在确保您在选项卡中看到的强或差表现随 [!UICONTROL Segment Performance] 时间而保持一致。

## 使用区段趋势报表 {#using-the-report}

在和之 **[!UICONTROL Mapped]** 间切 **[!UICONTROL Unmapped]** 换，以选择映射到或未映射到目标的区段。 选择 **[!UICONTROL All]** 以在报告中包含所有区段。

使用滑块调整回顾窗 **[!UICONTROL Date Through]** 口。

单击滑块下的任何区 **[!UICONTROL Date Through]** 段，以显示选项，仅将该区段保留在报告中或将其排除。

使用 **[!UICONTROL Line Item]** 下拉框选择要返回信息的个人信息中的属性。

在下 **[!UICONTROL Segment Data Source]** 拉框中，选择包含您要在报告中看到的区段的数据源。

使用下 **[!UICONTROL Segment]** 拉框选择要在报表中查看的区段。

>[!IMPORTANT]
>
>启用此 [!UICONTROL Audience Optimization for Publishers]功能时，必须包含ID的描述性元 [!UICONTROL Line Item] 数据，如将Google Ad Manager( [以前称为DFP)数据文件导入Audience Manager的步骤3中所述](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 通过执行此操作，您可以确保报告将Web属性详细 [!UICONTROL Line Item] 化为ID而 [!UICONTROL Line Item] 非ID。

## 解释结果 {#interpreting-results}

报 [!UICONTROL Segment Trend] 表仅在14天间隔内以线形图返回数据。 在此示例中，报表显示一组映射和未映射的区段的印象和点进趋势。

将鼠标悬停在任何行上可获取有关特定区段趋势的更多信息。 有关其他信息，请参阅示例报告下表中的说明。

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
   <td colname="col2"> <p>分配给此区段的字母数字名称。 </p> </td> 
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
   <td colname="col2"> <p>此特征的成员暴露到您的库存的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">CTR</span> </p> </td> 
   <td colname="col2"> <p>点进率. 此指标中继展示次数的百分比，点击次数。 将点击次数除以展示次数，以获得此指标。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 段唯一值</span> </p> </td> 
   <td colname="col2"> <p>最近30天内的区段成员数。 </p> </td> 
  </tr> 
 </tbody> 
</table>
