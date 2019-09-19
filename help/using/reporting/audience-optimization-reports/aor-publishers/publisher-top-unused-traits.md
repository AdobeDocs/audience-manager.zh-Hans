---
description: 顶部未使用的特征以散点图的形式表示，该散点图中的特征尚未成为区段的成员，具体取决于特征类型、数据源和性能。
seo-description: 顶部未使用的特征以散点图的形式表示，该散点图中的特征尚未成为区段的成员，具体取决于特征类型、数据源和性能。
seo-title: 最大未使用特征
solution: Audience Manager
title: 最大未使用特征
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 最大未使用特征{#top-unused-traits}

顶部未使用的特征以散点图的形式表示，该散点图中的特征尚未成为区段的成员，具体取决于特征类型、数据源和性能。

## 用例 {#use-cases}

通过报 [!UICONTROL Top Unused Traits] 告，您可以分析和比较当前未映射到区段的第一方和第三方特征的性能。 此视图可以指出受众细分中用于营销活动优化或净化新机会的最佳特征。

## 使用“Top Unused Traits”报告 {#using-the-report}

使用控 **[!UICONTROL Data Provider Type]** 件在第一方和第三方特征之间切换。 选择 **[!UICONTROL All]** 以在报表中返回第一方和第三方特征。

使用滑 **[!UICONTROL Impressions]** 块，您可以为返回的展示次数选择最小值和最大值。 对您设置的限制以下的任何特征均不显示在报告中。

使用 **[!UICONTROL Day Range]** 和 **[!UICONTROL Date Through]** 控件调整回顾范围。 请注意，此报告仅提供30天回顾期。

使用 **[!UICONTROL Order]** 下拉框选择您要返回其信息的作品集中的Web属性。

在下 **[!UICONTROL Data Provider]** 拉框中，选择包含要在报表中查看的特征的数据源。

使用 **[!UICONTROL Traits]** 下拉框选择要在报表中查看的特征。

>[!IMPORTANT]
>
>启用此 [!UICONTROL Audience Optimization for Publishers]项后，您必须包含描述性元数据， [!UICONTROL Order IDs]如将DFP数据文件导入Audience manager的 [步骤3中所述](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 通过执行此操作，您可以确保报告将Web属性详细 [!UICONTROL Order] 化为 [!UICONTROL Order ID]。

## 解释结果 {#interpreting-results}

**示例报告**

您 [!UICONTROL Top Unused Traits] 的报告可能与以下报告类似。 在报表中，单击气泡图可查看基础数据。

有关示例报告下表中的其他信息，请参阅说明。

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
   <td colname="col2"> <p>指定所选数据源是包含第一方特征还是包含第三方特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特征ID</span> </p> </td> 
   <td colname="col2"> <p>此特征的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特征名称</span> </p> </td> 
   <td colname="col2"> <p>您或分配给此特征的数据提供程序的字母数字名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 订购</span> </p> </td> 
   <td colname="col2"> <p>要查看此报告的Web属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 展示次数</span> </p> </td> 
   <td colname="col2"> <p>此特征的成员暴露给您的库存的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特征唯一值</span> </p> </td> 
   <td colname="col2"> <p>最近30天内的特征成员数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

报表中特征的位置可以告诉您许多可用于优化现有受众细分的特征。

“展示次数”轴上较高的特征是您希望在营销活动中使用的特征。 对于印象较少的特征，您不太可能根据DFP数据在您的Web资产上触及此受众。

请向左侧查看轴的 [!UICONTROL Unique Trait Realizations] 高度精确的特征，向右查看可驱动缩放的特征。

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
   <td colname="col2"> <p>展示次数多，特征实现次数少。 </p> <p>这是一个非常准确的受众，但尚未成为细分成员。 考虑定位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下角</b> </p> </td> 
   <td colname="col2"> <p>展示次数少，特征实现次数少。 </p> <p> 排除这些特征，因为成员不会对您的Web属性上的印象产生影响。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上</b> </p> </td> 
   <td colname="col2"> <p>高印象，高特质实现。 </p> <p>对尚未在细分中表示的受众的高覆盖度。 此受众是定位的主要候选者，因为其印象和规模都很高。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下</b> </p> </td> 
   <td colname="col2"> <p>展示次数少，特征实现数量大。 </p> <p> 您可以排除这些特征，因为成员不会对您的Web属性上的印象产生影响。 </p> </td> 
  </tr> 
 </tbody> 
</table>
