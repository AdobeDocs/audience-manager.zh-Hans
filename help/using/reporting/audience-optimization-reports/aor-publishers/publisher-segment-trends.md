---
description: “区段趋势”报告返回一段时间内映射和未映射区段的印象和点击率数据。映射的区段是您创建的区段，并发送到目标定位。未映射区段是您已创建但尚未发送到目标定位的区段。对比选定指标的趋势和音量，更好地了解受众随着时间的推移行为。
seo-description: “区段趋势”报告返回一段时间内映射和未映射区段的印象和点击率数据。映射的区段是您创建的区段，并发送到目标定位。未映射区段是您已创建但尚未发送到目标定位的区段。对比选定指标的趋势和音量，更好地了解受众随着时间的推移行为。
seo-title: 区段趋势报告
solution: Audience Manager
title: 区段趋势报告
uuid: f84e8d0-74e5-430c-b61 c-efb696 faee93
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Trend Report{#segment-trend-report}

“区段趋势”报告返回一段时间内映射和未映射区段的印象和点击率数据。

映射的区段是您创建的区段，并发送到目标定位。未映射区段是您已创建但尚未发送到目标定位的区段。

对比选定指标的趋势和音量，更好地了解受众随着时间的推移行为。

## 用例 {#use-cases}

Use the [!UICONTROL Segment Trend] report to validate a segment's performance over time and to pinpoint trends based on strong performance or scale.

通过此报告，您可以根据需要了解哪些Web属性会显示下降或错误的增加和故障排除。This report is the next step after you identify your audience of interest in the [!UICONTROL Segment Performance] report, to ensure that the strong or poor performance you saw in the [!UICONTROL Segment Performance] tab is consistent over time.

## Using the Segment Trend Report {#using-the-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Adjust the look-back window with the **[!UICONTROL Date Through]** slider.

Click any of the segments under the **[!UICONTROL Date Through]** slider to bring up the option to keep only that segment in the report or exclude it.

Use the **[!UICONTROL Line Item]** drop-down box to select the properties in your portfolio for which you want to return information.

In the **[!UICONTROL Segment Data Source]** drop-down box, select the data sources containing the segments you want to see in the report.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item] IDs, as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item] ID.

## Interpreting the Results {#interpreting-results}

[!UICONTROL Segment Trend] 报告将返回折线图中的数据，仅限14天间隔。在此示例中，报告显示一组映射的未映射区段的印象和点击趋势。

将鼠标悬停在任何线上可获得有关该特定区段趋势的更多信息。有关详细信息，请参阅示例报告下表格中的其他信息。

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
   <td colname="col2"> <p>为此区段分配的字母数字名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 区段ID</span> </p> </td> 
   <td colname="col2"> <p>此区段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Line项目</span> </p> </td> 
   <td colname="col2"> <p>您看到此报告的Web资产。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 点击次数</span> </p> </td> 
   <td colname="col2"> <p>该特征成员单击Web资产中的项目的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 展示次数</span> </p> </td> 
   <td colname="col2"> <p>此特征向您的库存公开的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">CTR</span> </p> </td> 
   <td colname="col2"> <p>点进率. 此指标计算印象的百分比，之后依次单击。除以印象，获得此指标。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 区段统一</span> </p> </td> 
   <td colname="col2"> <p>在过去30天内区段成员的数量。 </p> </td> 
  </tr> 
 </tbody> 
</table>
