---
description: Audience Optimization报表中的跨渠道转化选项允许您将离线转化归因于提供的在线展示次数或点击次数。
seo-description: Audience Optimization报表中的跨渠道转化选项允许您将离线转化归因于提供的在线展示次数或点击次数。
seo-title: 跨渠道转化
solution: Audience Manager
title: 跨渠道转化
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization 报表
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 5%

---

# 跨渠道转化{#cross-channel-conversion}

Audience Optimization报表中的跨渠道转化选项允许您将离线转化归因于提供的在线展示次数或点击次数。

[!UICONTROL Cross Channel Conversion]报表将[!DNL Google Campaign Manager]平台的结果与[!DNL Audience Manager]转化特征相结合。 这可让您将离线转化链接到在线展示次数或点击次数。

您可以将[!UICONTROL Cross Channel Conversion]用于[区段性能](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md)和[最佳频率](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md)报表。

要查看[!UICONTROL Cross Channel Conversion]报表，请在&#x200B;**[!UICONTROL Platform]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL AAM + Ad Server Name]**&#x200B;项目。

下表列出了在设置[!UICONTROL Cross Channel Conversion]时的重要注意事项：

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> 注意事项 </th> 
   <th class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>最小转化特征数 </p> </td> 
   <td colname="col1"> <p>必须至少将一个转化特征分配给数据源，才能运行<span class="wintitle">跨渠道转化</span>报表。 有关特征的更多信息，请参阅<a href="../../../features/traits/create-onboarded-rule-based-traits.md">特征的基本信息</a> 。 </p> </td> 
  </tr>
  <tr> 
   <td> <p>归因窗口 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+Google促销活动管</span></b> 理器归因窗口为14天，这意味着仅考虑过最近两周显示的转化特征。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>最近联系方法 </p> </td> 
   <td> <p>用户在转化前最后看到的创作元素是授予转化的创作元素。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>点击次数与展示次数 </p> </td> 
   <td> <p>在决定是否同时发生归因时，点击优先于展示次数。 例如，在显示多个创作元素的页面上，被点击的创作元素会获得转化。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>数据新近度 </p> </td> 
   <td> <p>报表始终针对前一天的可用数据进行计算。 </p> </td> 
  </tr> 
 </tbody> 
</table>
