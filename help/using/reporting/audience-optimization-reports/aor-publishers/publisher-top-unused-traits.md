---
description: 顶部未使用的特征以散点图的形式表示，该散点图中的特征尚未成为区段的成员，具体取决于特征类型、数据源和性能。
seo-description: 顶部未使用的特征以散点图的形式表示，该散点图中的特征尚未成为区段的成员，具体取决于特征类型、数据源和性能。
seo-title: 排名最前的未使用特征
solution: Audience Manager
title: 排名最前的未使用特征
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 2%

---


# 排名最前的未使用特征{#top-unused-traits}

顶部未使用的特征以散点图的形式表示，该散点图中的特征尚未成为区段的成员，具体取决于特征类型、数据源和性能。

## 用例 {#use-cases}

通过报 [!UICONTROL Top Unused Traits] 告，您可以分析和比较当前未映射到区段的第一方和第三方特征的性能。 此视图可以指出在受众区段中用于活动优化或净化新机会的最佳特征。

## 使用“最大未使用特征”报表 {#using-the-report}

使用控 **[!UICONTROL Data Provider Type]** 件在第一方和第三方特征之间切换。 选择 **[!UICONTROL All]** 以在报表中返回第一方和第三方特征。

使用滑 **[!UICONTROL Impressions]** 块，您可以为返回的印象选择最小值和最大值。 任何对您设置的限制负有或超过限制的特征均不会显示在报告中。

使用 **[!UICONTROL Day Range]** 和 **[!UICONTROL Date Through]** 控件调整回顾范围。 请注意，此报表仅提供30天回顾期。

使用 **[!UICONTROL Order]** 下拉框选择您要返回信息的个人信息中的Web属性。

在下 **[!UICONTROL Data Provider]** 拉框中，选择包含要在报表中查看的特征的数据源。

使用下 **[!UICONTROL Traits]** 拉框选择要在报表中查看的特征。

>[!IMPORTANT]
>
>启用时， [!UICONTROL Audience Optimization for Publishers]必须包含描述性元数据， [!UICONTROL Order IDs]如将Google Ad Manager( [以前称为DFP)数据文件导入Audience Manager的步骤3中所述](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 通过执行此操作，您可以确保报告将Web属性详细 [!UICONTROL Order] 化为而非 [!UICONTROL Order ID]。

## 解释结果 {#interpreting-results}

**示例报告**

您 [!UICONTROL Top Unused Traits] 的报告可能与下面的报告类似。 在报表中，单击气泡以视图基础数据。

有关其他信息，请参阅示例报告下表中的说明。

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
   <td colname="col1"> <p><span class="wintitle"> 数据提供程序类型</span> </p> </td> 
   <td colname="col2"> <p>指定所选数据源是包含第一方特征还是第三方特征。 </p> </td> 
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
   <td colname="col2"> <p>您看到此报表的Web属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 展示次数</span> </p> </td> 
   <td colname="col2"> <p>此特征的成员暴露到您的库存的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特征唯一</span> </p> </td> 
   <td colname="col2"> <p>过去30天内的特征成员数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

您的特征在报表中的位置可以告诉您许多可用于优化现有受众段的特征。

“展示次数”轴上较高的特征是您要在活动中使用的特征。 对于印象较少的特征，您不太可能根据您的受众在您的Web资产上获得此 [!DNL Google Ad Manager] 。

请向左侧查找高度精 [!UICONTROL Unique Trait Realizations] 确的特征，向右查找可驱动缩放的特征。

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 放置指示 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上角</b> </p> </td> 
   <td colname="col2"> <p>展示次数多，特征实现次数少。 </p> <p>这是一个非常准确的受众，它尚未成为某个细分的成员。 考虑定位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下</b> </p> </td> 
   <td colname="col2"> <p>展示次数少，特征实现次数少。 </p> <p> 排除这些特征，因为成员不会对您的Web属性上的印象产生影响。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上</b> </p> </td> 
   <td colname="col2"> <p>展示次数多，特征实现次数多。 </p> <p>对尚未在区段中表示的受众的高范围。 此受众是定位的主要候选者，因为展示次数和规模很大。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下</b> </p> </td> 
   <td colname="col2"> <p>展示次数少，特质实现次数多。 </p> <p> 您可以排除这些特征，因为成员不会对您的Web属性上的印象产生影响。 </p> </td> 
  </tr> 
 </tbody> 
</table>
