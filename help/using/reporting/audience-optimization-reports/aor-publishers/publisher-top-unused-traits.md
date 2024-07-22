---
description: 排名最前的未使用特征以区段成员的特征散点图表示，具体取决于特征类型、数据源和性能。
seo-description: Top Unused Traits are represented as a scatter diagram of traits that are not yet members of a segment, based on trait type, data source, and performance.
seo-title: Top Unused Traits
solution: Audience Manager
title: 排名最前的未使用特征
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: Audience Optimization Reports
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 0%

---

# 排名最前的未使用特征{#top-unused-traits}

排名最前的未使用特征以区段成员的特征散点图表示，具体取决于特征类型、数据源和性能。

## 用例 {#use-cases}

通过[!UICONTROL Top Unused Traits]报表，您可以分析和比较当前未映射到区段的第一方和第三方特征的性能。 此视图可指出要在受众区段中使用的最佳特征，以便优化促销活动或创造全新商机。

## 使用“排名最前的未使用特征”报表 {#using-the-report}

使用&#x200B;**[!UICONTROL Data Provider Type]**&#x200B;控件在第一方和第三方特征之间切换。 选择&#x200B;**[!UICONTROL All]**&#x200B;以在报表中返回第一方和第三方特征。

使用&#x200B;**[!UICONTROL Impressions]**&#x200B;滑块，可以为返回的展示次数选择最小值和最大值。 任何导致限制小于或大于您设置的限制的特征都不会显示在报表中。

使用&#x200B;**[!UICONTROL Day Range]**&#x200B;和&#x200B;**[!UICONTROL Date Through]**&#x200B;控件调整您的回顾范围。 请注意，此报表仅提供30天的回顾期间。

使用&#x200B;**[!UICONTROL Order]**&#x200B;下拉框选择项目组合中要返回其信息的Web属性。

在&#x200B;**[!UICONTROL Data Provider]**&#x200B;下拉框中，选择包含要在报表中查看的特征的数据源。

使用&#x200B;**[!UICONTROL Traits]**&#x200B;下拉框选择要在报表中查看的特征。

>[!IMPORTANT]
>
>启用[!UICONTROL Audience Optimization for Publishers]时，必须包括[!UICONTROL Order IDs]的描述性元数据，如[将Google广告管理器（以前为DFP）数据文件导入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步骤3中所述。 通过这样做，您可以确保报告将Web属性详细视为[!UICONTROL Order]，而不是[!UICONTROL Order ID]。

## 解释结果 {#interpreting-results}

**示例报告**

您的[!UICONTROL Top Unused Traits]报表可能类似于下面的报表。 在报表中，单击气泡查看基础数据。

请参阅示例报表下表中其他信息的说明。

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
   <td colname="col1"> <p><span class="wintitle">数据提供程序类型</span> </p> </td> 
   <td colname="col2"> <p>指定所选数据源是包含第一方特征还是第三方特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">特征ID</span> </p> </td> 
   <td colname="col2"> <p>此特征的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">特征名称</span> </p> </td> 
   <td colname="col2"> <p>您或分配给此特征的数据提供程序的字母数字名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">订单</span> </p> </td> 
   <td colname="col2"> <p>您正在查看其此报表的Web属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">展示次数</span> </p> </td> 
   <td colname="col2"> <p>此特征的成员向您的清单公开的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">特征独特</span> </p> </td> 
   <td colname="col2"> <p>过去30天内特征成员的数量。 </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

特征在报表中的位置可告知您可用来优化现有受众区段的特征。

位于展示次数轴上较高位置的特征，是您希望在营销活动中使用的特征。 对于展示次数较少的特征，根据您的[!DNL Google Ad Manager]数据，您在Web资产上不太可能联系到此受众。

请向[!UICONTROL Unique Trait Realizations]轴左边查找高度准确的特征，向右边查找可推动缩放的特征。

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 放置指示 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上</b> </p> </td> 
   <td colname="col2"> <p>展示次数高，特征实现次数低。 </p> <p>这是尚未成为区段成员的高精度受众。 考虑进行定位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下</b> </p> </td> 
   <td colname="col2"> <p>展示次数低，特征实现次数低。 </p> <p> 排除这些特征，因为成员不会增加您的Web资产展示次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上</b> </p> </td> 
   <td colname="col2"> <p>展示次数多，特征实现次数多。 </p> <p>针对尚未在区段中表示的受众的高覆盖率。 由于展示次数多，规模大，因此该受众是目标定位的主要候选受众。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下</b> </p> </td> 
   <td colname="col2"> <p>展示次数低，特征实现次数高。 </p> <p> 您可以排除这些特征，因为成员不会对Web资产的展示次数产生影响。 </p> </td> 
  </tr> 
 </tbody> 
</table>
