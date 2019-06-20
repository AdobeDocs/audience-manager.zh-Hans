---
description: 个人资料链接指标提供有关对您的站点进行身份验证的人员和设备的数据。配置文件链接中的数据和图形会在您创建合并规则时动态更新，或者当您单击配置文件合并规则仪表板中的现有规则时动态更新。这些指标可包括Adobe Experience Cloud Device Co-op或其他第三方设备图源中的设备图表。
seo-description: 个人资料链接指标提供有关对您的站点进行身份验证的人员和设备的数据。配置文件链接中的数据和图形会在您创建合并规则时动态更新，或者当您单击配置文件合并规则仪表板中的现有规则时动态更新。这些指标可包括Adobe Experience Cloud Device Co-op或其他第三方设备图源中的设备图表。
seo-title: 个人资料合并规则报告指标
solution: Audience Manager
title: 个人资料合并规则报告指标
uuid: 76a86ff0-4c644-4734-aec0-0a8828942096
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Report Metrics for Profile Merge Rules {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Link] 指标提供有关对您的网站进行身份验证的人员和设备的数据。The data and graphs in [!UICONTROL Profile Link] update dynamically as you create a merge rules or when you click an existing rule from the [!UICONTROL Profile Merge Rules] dashboard. These metrics can include device graph from the [!DNL Adobe Experience Cloud Device Co-op] or other third-party device graph sources.

## Merge Rule Metrics {#merge-rule-metrics}

Reports return data in side-by-side bar graphs when your merge rules use data from the [Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/) or other, third-party device graphs you may have access to in [!DNL Audience Manager]. This lets you compare your authenticated, first-party data with cross-device data provided by the [!UICONTROL Experience Cloud Device Co-op] or another, third-party device graph. For information about data returned by the [!UICONTROL Device Co-op], see [The Device Graph: Internal Processes and Output](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html). 此数据每天更新。

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 身份验证活动</span></b> </p> </td> 
   <td colname="col2"> <p>显示： </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> 活动人员</span>：过去60天内已对您的站点进行身份验证的人员数量。 </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> 跨设备</span>：在数据源 <a href="../../features/profile-merge-rules/merge-rules-start.md#create-data-source"> 存在的</a> 生命周期中 <a href="../../features/manage-datasources.md#create-data-source"> 所选</a><a href="../../features/profile-merge-rules/merge-rule-definitions.md"> 身份验证配置文件</a> 的数据源中存储的跨设备ID总数。 </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> 活动人员</span>：将 <span class="wintitle"> 活动人员</span> 显示为%。 </li> 
    </ul> <p> <span class="wintitle"> 通过实名活动</span> ，您可以按活动、数量和百分比比较数据源。它可以帮助您找到具有大量人员和大量活跃用户的数据源。或者，您可能会发现与活跃用户相比，比较数据源的价值与受众总数相比有很大的区别。例如，有时具有低终生数字和高活动的数据源比寿命较长、活动数量较低的数据源更有价值。 </p> <p> <p>Note: The <span class="wintitle"> Authenticated Activity</span> metrics contain <span class="wintitle"> Profile Link</span> data only. This report does not include <span class="wintitle"> Device Graph</span> data. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 每人平均设备</span></b> </p> </td> 
   <td colname="col2"> <p> 显示已为选定数据源已过身份验证的访客使用的平均设备数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 设备总数</span></b> </p> </td> 
   <td colname="col2"> <p>显示人们用于对选定数据源进行身份验证的设备总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 总人数</span></b> </p> </td> 
   <td colname="col2"> <p>显示已为选定数据源确定的用户总数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Device Graph Metrics {#device-graph-metrics}

[!UICONTROL Merge Rules] 报告还显示已访问选定数据源和设备图表的访客和设备总数数据。这些量度根据预设置的时间间隔(回顾期)返回数据，该时间间隔因您在创建规则时所选择的设备选项而异。下表列出了每个设备图表选项的这些报告间隔。

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设备图表选项 </th> 
   <th colname="col2" class="entry"> 报告回顾间隔 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 配置文件链接</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">总人数：60天 </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">总设备：120天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 计划设备图表</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">总人数：180天 </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">总设备：180天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveMP</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">总人数：180天 </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">总设备：180天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">总人数：60天 </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">总设备60天 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sample Reports {#sample-reports}

### 标准配置文件链接报告

A standard [!UICONTROL Profile Link] report looks like the following example. 合并使用多个数据源(最多个，最大)的规则在每个数据源的单独选项卡中显示图形。This merge rule does not include [!UICONTROL Device Co-op] data.

![](assets/coop-metrics1.png)

### 配置文件链接报告与设备图表数据

[!UICONTROL Profile Link] 一个报表，其中包含来自或 [!UICONTROL Adobe Experience Cloud Device Co-op] 第三方设备图的设备图表数据，以及 [!UICONTROL Profile Link] 带有并排条形图的设备图表数据。Placing these graphs adjacent to each other lets you evaluate the benefits of using the [!UICONTROL Experience Cloud Device Co-op] compared to [!UICONTROL Profile Link] by itself. 合并使用多个数据源(最多个，最大)的规则在每个数据源的单独选项卡中显示图形。As a reminder, the [!UICONTROL Authenticated Activity] graph and metrics do not return data from the [!DNL Adobe] device graph or other, third-party device graphs you may have access to in [!DNL Audience Manager].

![](assets/coop-metrics2.png)

## Profile Link Trend Graphs {#profile-link-trend}

In addition to the other data visualizations, [!UICONTROL Profile Link] reports include a line graph. 折线图旨在显示您的个人资料规则随时间推移的趋势。Trend graphs (and the other reports) are available when you click a rule from the [!UICONTROL Profile Merge Rules] landing page ( **[!UICONTROL Audience Data > Profile Merge Rules]**). These graphs include device graph data if you&#39;re a member of the [!UICONTROL Device Co-op] or other, third-party device graphs you may have access to in [!DNL Audience Manager]. 单击趋势线可查看基本数据。

![](assets/authenticated_trends.png)

>[!MORE_ LIKE_ This]
>
>* [个人资料合并规则常见问题解答](../../faq/faq-profile-merge.md)

