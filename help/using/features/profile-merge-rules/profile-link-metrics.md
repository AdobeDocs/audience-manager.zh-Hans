---
description: 用户档案链接量度提供有关对您的站点进行身份验证的人员和设备的数据。 在您创建合并规则时，或在您单击“用户档案合并规则”仪表板中的现有规则时，“用户档案链接”中的数据和图形会动态更新。 这些量度可以包括Adobe Experience Cloud Device Co-op中的设备图表或其他第三方设备图表源。
seo-description: 用户档案链接量度提供有关对您的站点进行身份验证的人员和设备的数据。 在您创建合并规则时，或在您单击“用户档案合并规则”仪表板中的现有规则时，“用户档案链接”中的数据和图形会动态更新。 这些量度可以包括Adobe Experience Cloud Device Co-op中的设备图表或其他第三方设备图表源。
seo-title: 配置文件合并规则的报表量度
solution: Audience Manager
title: 配置文件合并规则的报表量度
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: 用户档案合并
exl-id: 2af59c60-2448-44af-90d2-eccc52f7ff02
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 2%

---

# 配置文件合并规则的报表量度 {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] 量度提供有关对您的站点进行身份验证的人员和设备的数据。[!UICONTROL Profile Merge Rule Reports]中的数据和图形在您创建合并规则时或在您单击[!UICONTROL Profile Merge Rules]仪表板中的现有规则时动态更新。 这些量度可以包括来自[!DNL Adobe Experience Cloud Device Co-op]或其他第三方设备图形源的设备图形。

## 合并规则量度{#merge-rule-metrics}

当您的合并规则使用[Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html)或您在[!DNL Audience Manager]中可访问的其他第三方设备图形中的数据时，报表会以并排条形图返回数据。 这样，您就可以将已验证的第一方数据与[!UICONTROL Experience Cloud Device Co-op]或其他第三方设备图表提供的跨设备数据进行比较。 有关[!UICONTROL Device Co-op]返回的数据的信息，请参阅[设备图表：内部进程和输出](https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html)。 此数据每天更新。

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 已验证活动</span></b> </p> </td> 
   <td colname="col2"> <p>显示： </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> 活动人员</span>:过去60天内已通过网站身份验证的人数。 </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> 跨设备</span>:存储在所选已验 <a href="merge-rules-start.md#create-data-source"> 证</a> 的配置文件的 <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html"> 数据源中，</a> 在数据源存 <a href="merge-rule-definitions.md"> 在</a> 的存留期内的跨设备ID的总数。 </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> %活动人员</span>:显示 <span class="wintitle"> 活</span> 动人数%。 </li> 
    </ul> <p> <span class="wintitle"> 通过</span> 身份验证的活动允许您按活动、卷和百分比比较数据源。它可以帮助您找到一个拥有大量人员和高比例活跃用户的数据源。 或者，在比较数据源与活动用户的高比例与总受众大小时，您会发现有价值。 例如，有时，总寿命数和高活动的数据源比寿命结果高和活动数低的数据源更有价值。 </p> <p> <p>注意：<span class="wintitle">已验证活动</span>量度仅包含<span class="wintitle">用户档案链接</span>数据。 此报告不包括<span class="wintitle">设备图</span>数据。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 每人平均设备数</span></b> </p> </td> 
   <td colname="col2"> <p> 显示已对所选数据源的站点进行身份验证的访客使用的平均设备数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 设备总数</span></b> </p> </td> 
   <td colname="col2"> <p>显示用户为所选数据源向您的站点进行身份验证时使用的设备总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 总人数</span></b> </p> </td> 
   <td colname="col2"> <p>显示为选定数据源确定地识别的人员总数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 设备图度量{#device-graph-metrics}

[!UICONTROL Merge Rules]报告还显示选定数据源和设备图表访问过您站点的人员和设备总数。 这些量度根据预设时间间隔（回顾期）返回数据，这些时间间隔根据您在创建规则时选择的设备选项而有所不同。 下表列表了每个设备图表选项的这些报告间隔。

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设备图表选项 </th> 
   <th colname="col2" class="entry"> 报表回顾间隔 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 配置文件链接</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">总人数：60天 </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">设备总数：120天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 协作设备图表</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">总人数：180天 </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">设备总数：180天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">总人数：180天 </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">设备总数：180天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">总人数：60天 </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">设备总数60天 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例报表{#sample-reports}

### 标准用户档案链接报表

标准[!UICONTROL Profile Link]报表如下例所示。 合并使用多个数据源的规则（最多3个，最多3个）在每个数据源的单独选项卡中显示图形。 此合并规则不包括[!UICONTROL Device Co-op]数据。

![](assets/profile-link-metrics.png)

### 用户档案链接报表与设备图数据

[!UICONTROL Profile Link Device Graph]报表包含来自[!UICONTROL Adobe Experience Cloud Device Co-op]或第三方设备图形的设备图形数据，其中显示[!UICONTROL Profile Link]和具有并排条形图的设备图形数据。 将这些图形彼此相邻，这样您就可以评估与使用[!UICONTROL Profile Link]相比使用[!UICONTROL Experience Cloud Device Co-op]的优势。 合并使用多个数据源的规则（最多3个，最多3个）在每个数据源的单独选项卡中显示图形。 作为提醒，[!UICONTROL Authenticated Activity]图形和量度不会返回[!DNL Adobe]设备图或您在[!DNL Audience Manager]中可以访问的其他第三方设备图形中的数据。

![](assets/profile-link-graph.png)

## 用户档案链接趋势图{#profile-link-trend}

除了其他数据可视化之外，[!UICONTROL Profile Link]报表还包含线形图。 折线图旨在显示随时间变化的用户档案规则趋势。 单击[!UICONTROL Profile Merge Rules]登陆页(**[!UICONTROL Audience Data > Profile Merge Rules]**)中的规则时，趋势图（和其他报表）可用。 如果您是[!UICONTROL Device Co-op]的成员，则这些图形包括设备图形数据，或者您在[!DNL Audience Manager]中可以访问的其他第三方设备图形。 单击趋势线可查看基础数据。

>[!MORELIKETHIS]
>
>* [用户档案合并规则常见问题解答](../../faq/faq-profile-merge.md)

