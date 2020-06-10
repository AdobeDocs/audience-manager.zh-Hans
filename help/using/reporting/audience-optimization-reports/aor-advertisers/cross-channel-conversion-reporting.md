---
description: 通过受众优化报告中的“跨渠道转换”选项，您可以将离线转化归因于提供的在线展示次数或点击次数。
seo-description: 通过受众优化报告中的“跨渠道转换”选项，您可以将离线转化归因于提供的在线展示次数或点击次数。
seo-title: 跨渠道转化
solution: Audience Manager
title: 跨渠道转化
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
translation-type: tm+mt
source-git-commit: 6988c6750c98f382a3440a606677243646551ad1
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 4%

---


# 跨渠道转化{#cross-channel-conversion}

通过受众优化报告中的“跨渠道转换”选项，您可以将离线转化归因于提供的在线展示次数或点击次数。

报 [!UICONTROL Cross Channel Conversion] 告将来自(DCM)平台的 [!DNL DoubleClick Campaign Manager] 结果与转换特征 [!DNL Audience Manager] 相结合。 这使您能够将线下转化关联到在线展示或点击。

您可以使用“ [!UICONTROL Cross Channel Conversion] 细分性 [能”和](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) “最 [佳频率”报表](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) 。

要视图报 [!UICONTROL Cross Channel Conversion] 表，请在 **[!UICONTROL AAM+DCM]** 下拉列表 **[!UICONTROL Platform]** 中选择项目。

下表列表了设置时的重要注意事项 [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>必须至少将一个转换特征分配给数据源，才能运行“交叉 <span class="wintitle"> 渠道转换</span> ”报表。 有关 <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> 特征的详细信息</a> ，请参阅特征的基本信息。 </p> </td> 
  </tr>
  <tr> 
   <td> <p>归因窗口 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+DCM归因窗口</span></b> 为14天，这意味着只考虑过去两周中显示的转换特征。 </p> </td> 
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
