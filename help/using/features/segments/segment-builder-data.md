---
description: 在区段生成器中添加和删除特征，以查看实际特征人群以及实际和估计的细分人口数据。估计的人口规模数据可帮助您为营销活动构建正确的细分。
seo-description: 在区段生成器中添加和删除特征，以查看实际特征人群以及实际和估计的细分人口数据。估计的人口规模数据可帮助您为营销活动构建正确的细分。
seo-title: 区段生成器中的特征和区段人口数据
solution: Audience Manager
title: 区段生成器中的特征和区段人口数据
uuid: e1e59c0a-b4 c7-4design-8485-3667e0 a95 e83
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Trait and Segment Population Data in Segment Builder {#trait-and-segment-population-data-in-segment-builder}

Add and remove traits in [!UICONTROL Segment Builder] to see actual trait populations along with actual and estimated segment population data. 估计的人口规模数据可帮助您为营销活动构建正确的细分。

## Trait Population Data {#trait-population-data}

[!UICONTROL Segment Builder] 向您 [!UICONTROL Total Trait Population] 显示向区段添加特征的最后一天。This data appears in the blue field around your selected trait in the [!UICONTROL Basic View] section.

![](assets/trait-size.png)

下表定义特征人口指标

<table id="table_9D837CF9ACA04D04BEE5925EC0B4A5D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 特征总数</span> </p> </td>
   <td colname="col2"> <p>在其配置文件中具有选定特征的唯一ID的数量。 </p> </td>
  </tr> 
 </tbody> 
</table>

## Calculating Real and Estimated Segment Populations {#calculating-real-estimated-populations}

当您创建新区段或更改现有区段时，Audience Manager最多需要24小时才能显示实际实时和总细分人群的结果。

但是，Audience Manager可立即评估您的区段的实时和总人口规模。这些估算基于采样历史数据，并以95%置信区间返回结果。

![](assets/confidence-interval.png)

In [!UICONTROL Segment Builder], a blue bar on the estimated population graphs indicates the possible upper and lower ranges for segment size. 尽管过去的性能不能保证将来的结果，但是估计的数据可以帮助您了解新的或编辑过的区段的潜在大小。

## Segment Population Data Overview {#segment-populations}

[!UICONTROL Segment Builder] 显示在创建和编辑区段时细分人口数据。

* For estimated segment population data (real-time and total), [!UICONTROL Segment Builder] does not update the graphs automatically as you add or remove traits in a segment. Click **[!UICONTROL Calculate Estimates]** to see (or refresh) the estimated population numbers.

* For actual (real) segment population data (real-time and total), [!UICONTROL Segment Builder] updates the segment graph automatically when you load an existing segment. 对于新区段，或者当您向现有区段添加新特征时，实际人口数据直到创建区段后24小时才会更新。

![](assets/segment-data.png)

请参阅下面的定义以了解有关估计和实际细分人群数据的更多信息。

## Estimated Segment Population Data Defined {#estimated-segment-population}

下表定义了估计的人口指标。

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 估计的实时人口(潜在) </span> </p> </td> 
   <td colname="col2"> <p>预计在指定时间范围内实时查看的唯一访客数量，以及Audience Manager查看时获得区段的唯一访客数量。 </p> <p><span class="wintitle"> 在区段生成器</span>中，对于实时评估的特征和区段，过去30天的特征(<span class="wintitle"> 特征总数)</span>可能有所不同。 </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">对于特征，上30天的量度计算在过去30天内符合该特征的唯一用户的数量。 </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">对于实时评估的细分，过去30天的指标将计算过去在过去的某个时候有资格获得特征(在该细分中)的用户数，并在过去30天内由Audience Manager再次查看。例如，假设您有一个在60天前有资格参加特征的用户，10天前再次看到它。在数据中，此用户不会添加到特征计数，因为他们在30天前首次符合特征。但是，它们将包含在实时评估的区段的最后30天计数中。这是因为他们在30天的时间间隔内获得了区段资格。 </li>
     </ul> </p> <p> <p>Note: The <span class="wintitle"> Estimated Real-Time Population</span> metric does not include devices that have qualified for a segment based on connections provided by a <span class="wintitle"> Profile Merge Rule</span> that uses a <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> device graph option</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 估计总人口(潜在)</span> </p> </td> 
   <td colname="col2"> <p>可能位于新区段或修改区段中的估计访客数量。正如几乎任何估算一样，过去的效果不能保证将来的成效，但是您可以使用估计的总数： </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">了解在您构建区段时，新的或修改过的区段可能会达到多少用户。 </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">根据您的目标调整区段。例如，大细分对于品牌识别营销活动和更小的细分很有用，对于集中定位或重定向营销活动很有用。 </li> 
     </ul> </p> <p> <p>Note: The <span class="wintitle"> Estimated Total Population</span> metric does not include devices that have qualified for a segment based on connections provided by a <span class="wintitle"> Profile Merge Rule</span> that uses a <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> device graph option</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Existing (Actual) Segment Population Data Defined {#existing-segment-population}

[!UICONTROL Profile Merge Rules] 影响实际的实时和总人口总数。These totals vary depending on if the [!UICONTROL Profile Merge Rule] a segment belongs to uses a device graph option or not. See also, [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md).

### 在没有设备图表选项的情况下合并规则的区段人口数据

The following table defines the actual real-time and total population metrics when your segments are used by a [!UICONTROL Profile Merge Rule] created without a device graph option. These are the device options settings **[!UICONTROL No Device Options]** and **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 实时人口(现有)</span> </p> </td> 
   <td colname="col2"> <p>特定访客在指定时间范围内实时查看的实际数量，以及Audience Manager看到的区段。 </p> <p><span class="wintitle"> 在区段生成器</span>中，实时评估特征和<span class="wintitle"> 区段的特征和</span>区段的最后30天人群可以有所不同。 </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">对于特征，上30天的量度计算在过去30天内符合该特征的唯一用户的数量。 </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">对于实时评估的细分，过去30天的指标将计算过去在过去的某个时候有资格获得特征(在该细分中)的用户数，并在过去30天内由Audience Manager再次查看。例如，假设您有一个在60天前有资格参加特征的用户，10天前再次看到它。在数据中，此用户不会添加到特征计数，因为他们在30天前首次符合特征。但是，它们将包含在实时评估的区段的最后30天计数中。这是因为他们在30天的时间间隔内获得了区段资格。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 总人口(现有)</span> </p> </td> 
   <td colname="col2"> <p>自昨天起符合区段资格的实际访客数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 使用设备图表选项合并规则的区段人口数据

The following table defines the actual real-time and total population metrics when your segments are used by a [!UICONTROL Profile Merge Rule] created with a device graph option. These are the device options settings for the [!UICONTROL Profile Link Device Graph], the [!DNL Adobe] device graph, and other third-party device graph choices that are available to you.

<table id="table_157EC6E5B5C44EB899854CA10B090F60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 实时人口(现有)</span> </p> </td> 
   <td colname="col2"> <p>The actual number of devices seen in real-time with current profiles that, when merged with up to 3-other device profiles connected by the device graph, contains the traits to qualify for the segment the moment it was seen by <span class="keyword"> Audience Manager</span>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 总人口(现有)</span> </p> </td> 
   <td colname="col2"> <p>具有配置文件的设备总数(与设备图连接的其它最多个设备配置文件合并时)完全符合区段资格。 </p> </td>
  </tr>
 </tbody>
</table>

### 因评估细分人群而导致的最近缩进和频率表达式限制

[!UICONTROL Segment Builder] 对包含最多个新近度和频率表达式的细分规则支持细分大小的设置。在构建区段规则时选择超过个新近度和频率表达式会导致区段估计量在评估人群时显示错误。

### 因评估细分人群时合并规则的限制

目前存在一个已知限制，因为我们的细分大小估计器不考虑配置文件合并规则。For example, look at segments with the **No Authenticated Profile + Current Device Profile** [merge rule](../../features/profile-merge-rules/merge-rule-definitions.md). 由于我们当前计算细分估计数字的方式，估计的人群将包括经过身份验证的配置文件。但是，现有区段人群将正确忽略身份验证配置文件。

>[!MORE_ LIKE_ This]
>
>* [个人资料合并规则和设备图表常见问题解答](../../faq/faq-profile-merge.md)
>* [配置文件链接](../../features/profile-merge-rules/merge-rules-overview.md)

