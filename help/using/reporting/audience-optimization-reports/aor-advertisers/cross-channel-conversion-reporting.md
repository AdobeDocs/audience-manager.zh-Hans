---
description: 受众优化报告中的“跨渠道转化”选项允许您将离线转化归因于提供的在线印象或点击。
seo-description: 受众优化报告中的“跨渠道转化”选项允许您将离线转化归因于提供的在线印象或点击。
seo-title: 跨渠道转化
solution: Audience Manager
title: 跨渠道转化
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 跨渠道转化{#cross-channel-conversion}

受众优化报告中的“跨渠道转化”选项允许您将离线转化归因于提供的在线印象或点击。

报 [!UICONTROL Cross Channel Conversion] 告将(DCM)平台的结果 [!DNL DoubleClick Campaign Manager] 与转换特征结 [!DNL Audience Manager] 合在一起。 这使您能够将线下转化关联到在线印象或点击量。

您可以使用作 [!UICONTROL Cross Channel Conversion] 为“区 [段性能](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) ”和“ [最佳频率](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) ”报表。

要查看报 [!UICONTROL Cross Channel Conversion] 告，请在下拉列 **[!UICONTROL AAM+DCM]** 表中选择 **[!UICONTROL Platform]** 相应的项目。

下表列出了设置时的重要注意事项 [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>必须至少为数据源分配一个转换特征，才能运行“跨渠 <span class="wintitle"> 道转换</span> ”报告。 有关 <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> 特征的详细信息</a> ，请参阅特征的基本信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>最大转化特征数 </p> </td> 
   <td colname="col1"> <p>报告从用户中提 <i>取</i> 50个转化特征。 如果达到最大值，则报表将根据特征ID按升序使用前50个转换特征。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>归因窗口 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+DCM归因窗口为</span></b> 14天，这意味着只考虑过去两周中显示的转换特征。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>最近接触方法 </p> </td> 
   <td> <p>用户在转换前最后看到的创意是获得转换的创意。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>点击与展示次数 </p> </td> 
   <td> <p>在确定属性时，单击优先于印象（如果它们同时发生）。 例如，在显示多个创意的页面上，被点击的创意将获得转化。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>数据新近度 </p> </td> 
   <td> <p>报告始终会针对前一天可用的数据进行计算。 </p> </td> 
  </tr> 
 </tbody> 
</table>
