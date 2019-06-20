---
description: 通过受众优化报告中的“跨渠道转换”选项，您可以将脱机转化率归为提供在线印象或点击。
seo-description: 通过受众优化报告中的“跨渠道转换”选项，您可以将脱机转化率归为提供在线印象或点击。
seo-title: 跨渠道转化
solution: Audience Manager
title: 跨渠道转化
uuid: execec23-e502-490b-b7 dd-47a3753 a3 f75
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 跨渠道转化{#cross-channel-conversion}

通过受众优化报告中的“跨渠道转换”选项，您可以将脱机转化率归为提供在线印象或点击。

[!UICONTROL Cross Channel Conversion] 报告将来自 [!DNL DoubleClick Campaign Manager] (DCM)平台的结果与 [!DNL Audience Manager] 转化特征相结合。这允许您将脱机转换链接到在线印象或点击。

You can use the [!UICONTROL Cross Channel Conversion] for the [Segment Performance](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) and [Optimal Frequency](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) reports.

To view the [!UICONTROL Cross Channel Conversion] reports, select the **[!UICONTROL AAM+DCM]** item in the **[!UICONTROL Platform]** drop-down list.

The following table lists important considerations when setting up [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> 注意事项 </th> 
   <th class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>最低转化特征数 </p> </td> 
   <td colname="col1"> <p>At least one conversion trait must be assigned to a data source in order for the <span class="wintitle"> Cross Channel Conversion</span> reports to run. See <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Basic Information for Traits</a> for more information on traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>转换特征的最大数量 </p> </td> 
   <td colname="col1"> <p>The reports pull in a <i>maximum</i> of 50 conversion traits from the user. 如果达到最大值，报表将根据特征ID以升序ID使用前50个转化特征。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>归因窗口 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+ DCM</span></b> 归因窗口为14天，这意味着只考虑过去两周显示的转换特征。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>上一触控方法 </p> </td> 
   <td> <p>用户在转化前看到的创意就是转换。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>点击次数与展示次数 </p> </td> 
   <td> <p>如果在同时发生属性的情况下，单击，则在确定归因时优先。例如，在显示多个创意的页面上，被点击的那一个将获得转换。 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>数据新近度 </p> </td> 
   <td> <p>将始终为上一天提供的数据计算报告。 </p> </td> 
  </tr> 
 </tbody> 
</table>
