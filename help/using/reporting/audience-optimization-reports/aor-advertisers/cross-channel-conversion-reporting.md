---
description: 通过Audience Optimization报表中的“跨渠道转换”选项，您可以将脱机转换归因于提供的在线展示次数或点击次数。
seo-description: 通过Audience Optimization报表中的“跨渠道转换”选项，您可以将脱机转换归因于提供的在线展示次数或点击次数。
seo-title: 跨渠道转化
solution: Audience Manager
title: 跨渠道转化
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 97129b435ab8e13def14bc85dcaab8254b2c4bda
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---


# 跨渠道转化{#cross-channel-conversion}

通过Audience Optimization报表中的“跨渠道转换”选项，您可以将脱机转换归因于提供的在线展示次数或点击次数。

[!UICONTROL Cross Channel Conversion]报告将来自[!DNL Google Campaign Manager]平台的结果与[!DNL Audience Manager]转换特征相结合。 这使您能够将线下转化关联到在线展示或点击。

可以对[段性能](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md)和[最佳频率](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md)报告使用[!UICONTROL Cross Channel Conversion]。

要视图[!UICONTROL Cross Channel Conversion]报告，请在&#x200B;**[!UICONTROL Platform]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL AAM + Ad Server Name]**&#x200B;项。

下表列表了设置[!UICONTROL Cross Channel Conversion]时的重要注意事项：

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> 注意事项 </th> 
   <th class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>转化特征的最小数量 </p> </td> 
   <td colname="col1"> <p>必须至少将一个转换特征分配给数据源，才能运行<span class="wintitle">交叉渠道转换</span>报告。 有关特征的详细信息，请参阅<a href="../../../features/traits/create-onboarded-rule-based-traits.md">特征的基本信息</a>。 </p> </td> 
  </tr>
  <tr> 
   <td> <p>归因窗口 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+Google活动管</span></b> 理器归因窗口为14天，这意味着只考虑过去两周中显示的转化特征。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>最近接触方法 </p> </td> 
   <td> <p>用户在转换前最后看到的创意是获得转换的创意。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>点击与展示次数 </p> </td> 
   <td> <p>如果同时确定归因，则单击优先于印象。 例如，在显示多个创意的页面上，被点击的一个将获得转换。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>数据最近 </p> </td> 
   <td> <p>报告始终会针对前一天可用的数据进行计算。 </p> </td> 
  </tr> 
 </tbody> 
</table>
