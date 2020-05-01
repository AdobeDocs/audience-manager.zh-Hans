---
description: 用户档案链接指标提供有关对站点进行身份验证的人员和设备的数据。 在您创建合并规则或单击“用户档案合并规则”仪表板中的现有规则时，用户档案链接中的数据和图形会动态更新。 这些指标可以包括Adobe Experience Cloud Device Co-op或其他第三方设备图形源中的设备图。
seo-description: 用户档案链接指标提供有关对站点进行身份验证的人员和设备的数据。 在您创建合并规则或单击“用户档案合并规则”仪表板中的现有规则时，用户档案链接中的数据和图形会动态更新。 这些指标可以包括Adobe Experience Cloud Device Co-op或其他第三方设备图形源中的设备图。
seo-title: 用户档案合并规则的报告指标
solution: Audience Manager
title: 用户档案合并规则的报告指标
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# 用户档案合并规则的报告指标 {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] 度量提供有关对您的站点进行身份验证的人员和设备的数据。 在您创建合并规 [!UICONTROL Profile Merge Rule Reports] 则或单击仪表板中的现有规则时，数据和图形会动态 [!UICONTROL Profile Merge Rules] 更新。 这些指标可以包括来自或其 [!DNL Adobe Experience Cloud Device Co-op] 他第三方设备图形源的设备图。

## 合并规则度量 {#merge-rule-metrics}

当您的合并规则使用Adobe Experience Cloud Device Co-op或您可能在中访问的 [其他第三方设备图形中的数据时](https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html) ，报表会以并排条形图返回数据 [!DNL Audience Manager]。 这样，您就可以将已验证的第一方数据与由或另一第三方设备图形提供 [!UICONTROL Experience Cloud Device Co-op] 的跨设备数据进行比较。 有关返回的数据的信 [!UICONTROL Device Co-op]息，请 [参阅设备图： 内部流程和输出](https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html)。 此数据每天更新。

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
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> 活动人员</span>: 过去60天内通过网站身份验证的人数。 </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> 跨设备</span>: 在数据源存 <a href="merge-rules-start.md#create-data-source"> 在的生命</a> 期内，在选定的已验证 <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html"> 用户档案的数据源中存</a> 储的跨设备 <a href="merge-rule-definitions.md"></a> ID的总数。 </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> %活动人员</span>: 将活 <span class="wintitle"> 动人员</span> 显示为%。 </li> 
    </ul> <p> <span class="wintitle"> 通过身份验证</span> 活动，您可以按活动、卷和百分比比较数据源。 它可以帮助您找到一个人数众多、活跃用户比例较高的数据源。 或者，在比较数据源与活跃用户的高比例与受众总大小时，您会发现其价值。 例如，有时，总寿命数和活动率较低的数据源比寿命结果较高且活动率较低的数据源更有价值。 </p> <p> <p>注意： 已验 <span class="wintitle"> 证的活动</span> 度量仅 <span class="wintitle"> 包含用户档案链接</span> 数据。 此报告不包括设 <span class="wintitle"> 备图</span> 。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 每人平均设备数</span></b> </p> </td> 
   <td colname="col2"> <p> 显示已对所选数据源验证到您的站点的访客使用的设备平均数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 设备总数</span></b> </p> </td> 
   <td colname="col2"> <p>显示用户为选定数据源在站点上进行身份验证时使用的设备总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 总人数</span></b> </p> </td> 
   <td colname="col2"> <p>显示已确定为选定数据源标识的人员总数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 设备图表度量 {#device-graph-metrics}

报 [!UICONTROL Merge Rules] 告还显示有关选定数据源和设备图表访问过您的站点的人员和设备总数。 这些度量根据预设时间间隔（回顾期）返回数据，这些时间间隔根据您在创建规则时选择的设备选项而有所不同。 下表列表了每个设备图形选项的这些报告间隔。

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设备图形选项 </th> 
   <th colname="col2" class="entry"> 报告回顾间隔 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 配置文件链接</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">人员总数： 60天 </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">设备总数： 120天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 协作设备图</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">人员总数： 180天 </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">设备总数： 180天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">人员总数： 180天 </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">设备总数： 180天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">人员总数： 60天 </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">设备总数60天 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例报告 {#sample-reports}

### 标准用户档案链接报告

标准报 [!UICONTROL Profile Link] 表如下所示。 合并使用多个数据源（最多3个，最多3个）的规则会在每个数据源的单独选项卡中显示图形。 此合并规则不包括 [!UICONTROL Device Co-op] 数据。

![](assets/profile-link-metrics.png)

### 用户档案链接报告与设备图数据

包 [!UICONTROL Profile Link Device Graph] 括来自设备图形或第三方 [!UICONTROL Adobe Experience Cloud Device Co-op] 设备图形的设备图形数据的报表以 [!UICONTROL Profile Link] 及具有并排条形图的设备图形数据。 将这些图形彼此相邻，这样您就可以评估与单独使用 [!UICONTROL Experience Cloud Device Co-op] 图形相 [!UICONTROL Profile Link] 比的优势。 合并使用多个数据源（最多3个，最多3个）的规则会在每个数据源的单独选项卡中显示图形。 提醒您，图 [!UICONTROL Authenticated Activity] 形和度量不会返回设备图 [!DNL Adobe] 形或您可能在中访问的其他第三方设备图形的数据 [!DNL Audience Manager]。

![](assets/profile-link-graph.png)

## 用户档案链接趋势图 {#profile-link-trend}

除了其他数据可视化外，报 [!UICONTROL Profile Link] 表还包括线形图。 线形图旨在显示用户档案规则随时间推移的趋势。 单击登陆页()中的规则时，将显示趋势图(和其 [!UICONTROL Profile Merge Rules] 他报 **[!UICONTROL Audience Data > Profile Merge Rules]**&#x200B;表)。 如果您是您在中有权访问的其他第 [!UICONTROL Device Co-op] 三方设备图形的成员，则这些图形包括设备图形数据 [!DNL Audience Manager]。 单击趋势线可查看基础数据。

>[!MORELIKETHIS]
>
>* [用户档案合并规则常见问题解答](../../faq/faq-profile-merge.md)

