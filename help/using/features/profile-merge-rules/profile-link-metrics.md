---
description: 配置文件链接量度提供有关对您的网站进行身份验证的人员和设备的数据。 在创建合并规则或从“配置文件合并规则”仪表板单击现有规则时，配置文件链接中的数据和图形会动态更新。 这些量度可以包括来自其他第三方设备图源的设备图。
seo-description: Profile Link metrics provide data about people and devices that authenticate to your site. The data and graphs in Profile Link update dynamically as you create a merge rules or when you click an existing rule from the Profile Merge Rules dashboard. These metrics can include device graph from other third-party device graph sources.
seo-title: Report Metrics for Profile Merge Rules
solution: Audience Manager
title: 配置文件合并规则的报表量度
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: Profile Merge
exl-id: 2af59c60-2448-44af-90d2-eccc52f7ff02
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 0%

---

# 配置文件合并规则的报表量度 {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule]量度提供有关对您的网站进行身份验证的用户和设备的数据。 在创建合并规则或从[!UICONTROL Profile Merge Rules]仪表板单击现有规则时，[!UICONTROL Profile Merge Rule Reports]中的数据和图形会动态更新。 这些量度可以包括来自其他第三方设备图来源的设备图。

## 合并规则量度 {#merge-rule-metrics}

当合并规则使用您在[!DNL Audience Manager]中可能访问的第三方设备图中的数据时，报告以并排条形图形式返回数据。 这样，您就可以将经过身份验证的第一方数据与第三方设备图提供的跨设备数据进行比较。 此数据每天更新。

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle">已验证的活动</span></b> </p> </td> 
   <td colname="col2"> <p>显示： </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle">活跃人员</span>：过去60天内对您的网站进行身份验证的人员数。 </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle">跨设备</span>：在选定的<a href="merge-rule-definitions.md">已验证配置文件</a>的<a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html">数据Source</a>中存储的<a href="merge-rules-start.md#create-data-source">个跨设备ID</a>的总数，该数据源已存在该生命周期。 </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> %活动人员</span>：将<span class="wintitle">活动人员</span>显示为%。 </li> 
    </ul> <p> <span class="wintitle">已验证的活动</span>允许您按活动、卷和百分比比较数据源。 它可以帮助您查找拥有大量人员和高百分比活动用户的数据源。 或者，您可能会发现，比较活跃用户占总受众人数比例较高的数据源很有价值。 例如，有时总生命周期数低且活动数高的数据源比生命周期结果高且活动数低的数据源更有价值。 </p> <p> <p>注意： <span class="wintitle">已验证的活动</span>指标仅包含<span class="wintitle">配置文件链接</span>数据。 此报表不包括<span class="wintitle">设备图</span>数据。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle">每人平均设备数</span></b> </p> </td> 
   <td colname="col2"> <p> 显示经过网站身份验证的访客在所选数据源中使用的平均设备数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 总共<b><span class="wintitle">台设备</span></b> </p> </td> 
   <td colname="col2"> <p>显示用户用于针对所选数据源向您的站点进行身份验证的设备总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 总共<b><span class="wintitle">人</span></b> </p> </td> 
   <td colname="col2"> <p>显示已确定性地为所选数据源识别的总人数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 设备图指标 {#device-graph-metrics}

[!UICONTROL Merge Rules]报表还显示选定数据源和设备图中访问您网站的人员和设备的总数。 这些量度会根据预设时间间隔（回顾期间）返回数据，该时间间隔因您在创建规则时选择的设备选项而异。 下表列出了每个设备图选项的这些报告间隔。

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设备图选项 </th> 
   <th colname="col2" class="entry"> 报表回看间隔 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">配置文件链接</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">总人数：60天 </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">设备总数：120天 </li> 
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
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">设备总数（60天） </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例报告 {#sample-reports}

### 标准配置文件链接报表

标准[!UICONTROL Profile Link]报表类似于以下示例。 使用多个数据源（最多3个）的合并规则会在每个数据源的单独选项卡中显示图形。 此合并规则不包含[!UICONTROL external device graph]数据。

![](assets/profile-link-metrics.png)

### 包含设备图数据的配置文件链接报表

包含来自第三方设备图的设备图数据的[!UICONTROL Profile Link Device Graph]报告以并排条形图显示[!UICONTROL Profile Link]和设备图数据。 将这些图表彼此相邻可让您评估使用外部设备图表与[!UICONTROL Profile Link]本身相比的好处。 使用多个数据源（最多3个）的合并规则会在每个数据源的单独选项卡中显示图形。 提醒您，[!UICONTROL Authenticated Activity]图形和量度没有从[!DNL Adobe]设备图形或其他您在[!DNL Audience Manager]中可能有权访问的第三方设备图形返回数据。

![](assets/profile-link-graph.png)

## 配置文件链接趋势图 {#profile-link-trend}

除了其他数据可视化图表之外，[!UICONTROL Profile Link]报表还包含折线图。 折线图旨在向您显示配置文件规则随时间变化的趋势。 当您从[!UICONTROL Profile Merge Rules]登陆页面(**[!UICONTROL Audience Data > Profile Merge Rules]**)单击规则时，可以使用趋势图（和其他报表）。 如果您是第三方设备图的成员，则这些图包括设备图数据，您在[!DNL Audience Manager]中可能会访问这些设备图。 单击趋势线可查看基础数据。

>[!MORELIKETHIS]
>
>* [配置文件合并规则常见问题解答](../../faq/faq-profile-merge.md)
