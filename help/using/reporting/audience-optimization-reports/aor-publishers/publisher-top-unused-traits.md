---
description: 顶部未使用的特征以散点图表示，该图显示的是尚未成为区段成员的特征，具体取决于特征类型、数据源和性能。
seo-description: 顶部未使用的特征以散点图表示，该图显示的是尚未成为区段成员的特征，具体取决于特征类型、数据源和性能。
seo-title: 排名最前的未使用特征
solution: Audience Manager
title: 排名最前的未使用特征
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: Audience Optimization Reports
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 2%

---

# 排名最前的未使用特征{#top-unused-traits}

顶部未使用的特征以散点图表示，该图显示的是尚未成为区段成员的特征，具体取决于特征类型、数据源和性能。

## 用例 {#use-cases}

通过[!UICONTROL Top Unused Traits]报表，您可以分析和比较当前未映射到区段的第一方和第三方特征的性能。 此视图可以指出在受众区段中用于活动优化或净化新机会的最佳特征。

## 使用“Top Unused Traits Report {#using-the-report}（最大未使用特征报表）”

使用&#x200B;**[!UICONTROL Data Provider Type]**&#x200B;控件在第一方和第三方特征之间切换。 选择&#x200B;**[!UICONTROL All]**&#x200B;以在报表中返回第一方和第三方特征。

使用&#x200B;**[!UICONTROL Impressions]**&#x200B;滑块，可以为返回的展示次数选择最小值和最大值。 对您设置的限制负有或超过限制的任何特征不会显示在报表中。

使用&#x200B;**[!UICONTROL Day Range]**&#x200B;和&#x200B;**[!UICONTROL Date Through]**&#x200B;控件调整回顾范围。 请注意，此报表仅提供30天回顾期。

使用&#x200B;**[!UICONTROL Order]**&#x200B;下拉框选择要返回信息的个人信息中的Web属性。

在&#x200B;**[!UICONTROL Data Provider]**&#x200B;下拉框中，选择包含要在报表中查看的特征的数据源。

使用&#x200B;**[!UICONTROL Traits]**&#x200B;下拉框选择要在报表中查看哪些特征。

>[!IMPORTANT]
>
>启用[!UICONTROL Audience Optimization for Publishers]时，必须包含[!UICONTROL Order IDs]的描述性元数据，如[将Google Ad Manager（以前称为DFP）数据文件导入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步骤3中所述。 通过执行此操作，您可以确保报告将web属性详细描述为[!UICONTROL Order]而不是[!UICONTROL Order ID]。

## 解释结果{#interpreting-results}

**示例报告**

您的[!UICONTROL Top Unused Traits]报表可能与下面报表类似。 在报表中，单击气泡以视图基础数据。

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
   <td colname="col2"> <p>您看到此报表的Web属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 展示次数</span> </p> </td> 
   <td colname="col2"> <p>此特征的成员向您的库存公开的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特征唯一值</span> </p> </td> 
   <td colname="col2"> <p>最近30天内的特征成员数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

您的特征在报表中的位置可以告诉您许多可用于优化现有受众区段的特征。

“展示次数”轴上较高的特征是您要在活动中使用的特征。 对于印象较少的特征，您不太可能根据您的[!DNL Google Ad Manager]数据在您的Web属性上达到此受众。

查看[!UICONTROL Unique Trait Realizations]轴的左侧，了解高度准确的特征，右侧，了解可驱动缩放的特征。

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
   <td colname="col2"> <p>展示次数多，特征实现次数少。 </p> <p>这是一个非常准确的受众，它尚未成为细分的成员。 考虑定位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下</b> </p> </td> 
   <td colname="col2"> <p>展示次数少，特征实现次数少。 </p> <p> 排除这些特征，因为成员不会对您的Web属性上的展示次数产生影响。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上</b> </p> </td> 
   <td colname="col2"> <p>展示次数多，特征实现次数多。 </p> <p>对尚未在区段中指示的受众进行高访问。 由于展示次数和规模很大，此受众是定位的首选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下</b> </p> </td> 
   <td colname="col2"> <p>展示次数少，特征实现次数多。 </p> <p> 您可以排除这些特征，因为成员不会对您的Web属性上的展示次数产生影响。 </p> </td> 
  </tr> 
 </tbody> 
</table>
