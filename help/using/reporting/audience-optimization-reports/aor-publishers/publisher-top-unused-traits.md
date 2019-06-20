---
description: 未使用的未使用特征表示为根据特征类型、数据源和性能而不是区段成员的特征的散点图。
seo-description: 未使用的未使用特征表示为根据特征类型、数据源和性能而不是区段成员的特征的散点图。
seo-title: 未使用的主要特征
solution: Audience Manager
title: 未使用的主要特征
uuid: 90bcd333-41b8-416e-aa4 e-a8661891 df50
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Top Unused Traits{#top-unused-traits}

未使用的未使用特征表示为根据特征类型、数据源和性能而不是区段成员的特征的散点图。

## 用例 {#use-cases}

With the [!UICONTROL Top Unused Traits] report, you can analyze and compare the performance of first and third party traits that are currently not mapped to a segment. 此视图可指出在受众细分中使用的最佳特征，以进行营销活动优化或获得新的商机。

## Using the Top Unused Traits Report {#using-the-report}

Use the **[!UICONTROL Data Provider Type]** controls to toggle between first party and third party traits. Select **[!UICONTROL All]** to return first and third party traits in the report.

**[!UICONTROL Impressions]** 使用滑块，您可以为返回的印象选择最小值和最大值。任何负责小于或超过设置限制的特征均不会显示在报告中。

Use the **[!UICONTROL Day Range]** and **[!UICONTROL Date Through]** controls to adjust your look-back range. 请注意，此报告只有30天的回顾期。

Use the **[!UICONTROL Order]** drop-down box to select the web properties in your portfolio for which you want to return information.

In the **[!UICONTROL Data Provider]** drop-down box, select the data sources containing the traits you want to see in the report.

Use the **[!UICONTROL Traits]** drop-down box to select which traits you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Order IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Order] instead of the [!UICONTROL Order ID].

## Interpreting the Results {#interpreting-results}

**示例报告**

[!UICONTROL Top Unused Traits] 您的报表类似于下面的报告。在报表中，单击气泡以查看基础数据。

有关详细信息，请参阅示例报告下表格中的其他信息。

![](assets/publisher_unused_traits.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 数据提供者类型</span> </p> </td> 
   <td colname="col2"> <p>指定选定的数据源是否包含第一方或第三方特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特征ID</span> </p> </td> 
   <td colname="col2"> <p>此特征的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特征名称</span> </p> </td> 
   <td colname="col2"> <p>您或为此特征分配的数据提供程序的字母数字名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 订购</span> </p> </td> 
   <td colname="col2"> <p>您看到此报告的Web资产。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 展示次数</span> </p> </td> 
   <td colname="col2"> <p>此特征向您的库存公开的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特征统一</span> </p> </td> 
   <td colname="col2"> <p>特征会员的数量，在过去30天内。 </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

您在报告中的特征位置可以告诉您可用于优化现有受众细分的特征。

在“印象轴”上更高的特征是您要在营销活动中使用的特征。对于印象较少的特征，根据您的DFP数据，您不太可能在Web资产上触及此受众。

Look to the left of the [!UICONTROL Unique Trait Realizations] axis for highly accurate traits and to the right for traits that can drive scale.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 位置指示 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上角</b> </p> </td> 
   <td colname="col2"> <p>印象很大，特征真实性低。 </p> <p>这是尚未成为区段成员的高度准确的受众。考虑定位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下部</b> </p> </td> 
   <td colname="col2"> <p>印象数量低，特征真实性低。 </p> <p> 排除这些特征，因为成员不会对您的Web资产造成影响。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上方</b> </p> </td> 
   <td colname="col2"> <p>印象很大，特征真实性很高。 </p> <p>面向尚未在细分中表示的受众。由于印象和规模很大，此受众是定位的主要候选者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下角</b> </p> </td> 
   <td colname="col2"> <p>印象数量低，特征真实性高。 </p> <p> 您可以排除这些特征，因为成员不会对您的Web资产造成影响。 </p> </td> 
  </tr> 
 </tbody> 
</table>
