---
description: “区段趋势”报表会返回一段时间内映射和未映射区段的印象和点击率数据。 映射的区段是您创建的区段，并将其发送到目标以进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 比较所选指标的趋势和数量，以更好地了解受众随时间的变化情况。
seo-description: “区段趋势”报表会返回一段时间内映射和未映射区段的印象和点击率数据。 映射的区段是您创建的区段，并将其发送到目标以进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。 比较所选指标的趋势和数量，以更好地了解受众随时间的变化情况。
seo-title: 区段趋势报告
solution: Audience Manager
title: 区段趋势报告
uuid: f84e8d0a-74e5-430c-b61c-efb696fae93
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 区段趋势报告{#segment-trend-report}

“区段趋势”报表会返回一段时间内映射和未映射区段的印象和点击率数据。

映射的区段是您创建的区段，并将其发送到目标以进行定位。 未映射的区段是您已创建但尚未发送到目标进行定位的区段。

比较所选指标的趋势和数量，以更好地了解受众随时间的变化情况。

## 用例 {#use-cases}

使用该 [!UICONTROL Segment Trend] 报告可验证某个细分随时间的表现，并根据强大的性能或规模找出趋势。

通过此报告，您可以了解哪些Web属性显示了下降或故障增加，并根据需要进行疑难解答。 此报告是在您确定报告中感兴趣的受众之后的下一步 [!UICONTROL Segment Performance] ，以确保您在选项卡中看到的强或差表现随时间 [!UICONTROL Segment Performance] 保持一致。

## 使用区段趋势报表 {#using-the-report}

在和之 **[!UICONTROL Mapped]** 间切 **[!UICONTROL Unmapped]** 换以选择映射到或不映射到目标的区段。 选择 **[!UICONTROL All]** 以在报告中包含所有区段。

使用滑块调整回顾窗 **[!UICONTROL Date Through]** 口。

单击滑块下方的任意区 **[!UICONTROL Date Through]** 段，以显示选项，以便仅将该区段保留在报告中或将其排除。

使用 **[!UICONTROL Line Item]** 下拉框选择要返回信息的个人信息中的属性。

在下拉 **[!UICONTROL Segment Data Source]** 框中，选择包含要在报表中查看的区段的数据源。

使用下 **[!UICONTROL Segment]** 拉框选择要在报表中查看的区段。

>[!IMPORTANT]
>
>启用此 [!UICONTROL Audience Optimization for Publishers]功能时，您必须包含ID的描述性元数据， [!UICONTROL Line Item] 如将DFP数据文件导入Audience manager的 [步骤3中所述](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 通过执行此操作，您可以确保报告将Web属性详细 [!UICONTROL Line Item] 设置为而不是 [!UICONTROL Line Item] ID。

## 解释结果 {#interpreting-results}

报 [!UICONTROL Segment Trend] 告仅在14天的间隔内返回线形图中的数据。 在此示例中，报表显示一组映射和未映射的区段的印象和点进趋势。

将鼠标悬停在任何线上可获取有关该特定区段趋势的更多信息。 有关示例报告下表中的其他信息，请参阅说明。

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
   <td colname="col2"> <p>要查看此报告的Web属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 点击次数</span> </p> </td> 
   <td colname="col2"> <p>此特征的成员单击Web属性中项的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 展示次数</span> </p> </td> 
   <td colname="col2"> <p>此特征的成员暴露给您的库存的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">CTR</span> </p> </td> 
   <td colname="col2"> <p>点进率. 此度量中继点击后的展示次数百分比。 将点击量除以展示次数，以获得此指标。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 区段唯一值</span> </p> </td> 
   <td colname="col2"> <p>最近30天内的区段成员数。 </p> </td> 
  </tr> 
 </tbody> 
</table>
