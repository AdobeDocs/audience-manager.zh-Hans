---
description: 在区段生成器中添加和删除特征，以查看实际特征群体以及实际和估计的区段群体数据。 估计的人口大小数据可帮助您为活动构建正确的细分。
seo-description: 在区段生成器中添加和删除特征，以查看实际特征群体以及实际和估计的区段群体数据。 估计的人口大小数据可帮助您为活动构建正确的细分。
seo-title: 区段生成器中的特征和区段人口数据
solution: Audience Manager
title: 区段生成器中的特征和区段人口数据
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 2%

---


# [!UICONTROL Trait] 和 [!UICONTROL Segment] 人口数据  [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

在[!UICONTROL Segment Builder]中添加和删除[!UICONTROL traits]以查看实际[!UICONTROL trait]人口以及实际和估计的细分人口数据。 估计的人口大小数据可帮助您为活动构建正确的细分。

## [!UICONTROL Trait] 人口数据  {#trait-population-data}

[!UICONTROL Segment Builder] 显示 [!UICONTROL Total Trait Population] 您添加区段的最 [!UICONTROL trait] 后一天。此数据显示在[!UICONTROL Basic View]部分选定[!UICONTROL trait]周围的蓝色字段中。

![](assets/trait-size.png)

下表定义特征填充度量：


| 量度 | 描述 |
---------|----------|
| [!UICONTROL Total Trait Population] | 在其用户档案中具有所选特征的唯一ID的数量。 |


## 计算实部和估计部分总体{#calculating-real-estimated-populations}

当您创建新区段或更改现有区段时，Audience Manager最多需要24小时才能显示实际实时和总区段总量的结果。

但是，Audience Manager可以立即估计细分的实时和总人口规模。 这些估计基于采样的历史数据和95%置信区间的回报结果。

![](assets/confidence-interval.png)

在[!UICONTROL Segment Builder]中，估计种群图上的蓝色条表示可能的段大小上限和下限。 尽管过去的表现不能保证将来的结果，但估计的数据可以帮助您了解新的或已编辑的区段的潜在大小。

## 区段填充数据概述{#segment-populations}

[!UICONTROL Segment Builder] 在创建和编辑区段时显示区段填充数据。

* 对于估计的区段填充数据（实时和总计）,[!UICONTROL Segment Builder]在添加或删除区段中的特征时不会自动更新图形。 单击&#x200B;**[!UICONTROL Calculate Estimates]**&#x200B;查看（或刷新）估计的人口数。

* 对于实际（实时）细分填充数据（实时和总计）,[!UICONTROL Segment Builder]会在加载现有细分时自动更新细分图。 对于新区段，或者在向现有区段添加新特征时，直到创建区段后24小时，才会更新实际人口数据。

![](assets/segment-data.png)

有关估计和实际细分填充数据的更多信息，请参阅以下定义。

## 定义的估计段填充数据{#estimated-segment-population}

下表定义了估计的人口量度。

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 估计实时人口（潜在）  </span> </p> </td> 
   <td colname="col2"> <p>在指定的时间范围内实时查看的估计唯一访客数，以及在Audience Manager看到这些数据时符合区段条件的数。 </p> <p>在<span class="wintitle">区段生成器</span>中，特征的最后30天群体（<span class="wintitle">总特征群体</span>）对于实时评估的特征和区段可能不同。 </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">对于特征，最后30天度量会计算过去30天内符合该特征条件的唯一用户数。 </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">对于实时评估的区段，最后30天指标会计算过去某个时点（该区段中）符合某个特征的用户数，并且过去30天内Audience Manager再次看到该特征的用户数。 例如，假设某个用户在60天前符合某个特征，10天前又再次出现。 在数据中，此用户不会添加到特征计数中，因为他们在30天前首次限定了特征。 但是，实时评估的细分在过去30天的计数中会包含这些信息。 这是因为他们在30天的时间间隔内符合区段条件。 </li>
     </ul> </p> <p> <p>注意：<span class="wintitle">估计实时填充</span>度量不包括根据使用<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">设备图形选项</a>的<span class="wintitle">用户档案合并规则</span>提供的连接符合段条件的设备。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 估计总人口（潜在）</span> </p> </td> 
   <td colname="col2"> <p>新区段或修改区段中可能存在的唯一访客的估计数。 与几乎任何估计一样，过去的绩效并不保证将来的结果，但您可以使用估计的总数： </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">查看在构建区段时新的或修订的区段可能触及的人数。 </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">根据您的目标调整区段。 例如，大型细分对品牌认知活动有用，小型细分对于重点定位或重新定位活动有用。 </li> 
     </ul> </p> <p> <p>注意：<span class="wintitle">估计总人口</span>度量不包括基于使用<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">设备图形选项</a>的<span class="wintitle">用户档案合并规则</span>提供的连接符合段条件的设备。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 已定义的现有（实际）段填充数据{#existing-segment-population}

[!UICONTROL Profile Merge Rules] 影响实时和总人口数。这些总数因段[!UICONTROL Profile Merge Rule]是否使用设备图形选项而异。 另请参阅[已定义的用户档案合并规则选项](../../features/profile-merge-rules/merge-rule-definitions.md)。

### [!UICONTROL Merge Rules]没有[!UICONTROL Device Graph Option]的区段填充数据

下表定义了当您的区段由未使用[!UICONTROL device graph]选项创建的[!UICONTROL Profile Merge Rule]使用时的实际实时和总填充量度。 这些是设备选项设置&#x200B;**[!UICONTROL No Device Options]**&#x200B;和&#x200B;**[!UICONTROL Current Device Proflie]**。

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 实时人口（现有）</span> </p> </td> 
   <td colname="col2"> <p>在指定的时间范围内实时查看的唯一访客的实际数量，以及在Audience Manager看到这些数据时符合区段条件的。 </p> <p>在<span class="wintitle">区段生成器</span>中，特征的最后30天群体（<span class="wintitle">总特征群体</span>）对于实时评估的特征和区段可能不同。 </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">对于特征，最后30天度量会计算过去30天内符合该特征条件的唯一用户数。 </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">对于实时评估的区段，最后30天指标会计算过去某个时点（该区段中）符合某个特征的用户数，并且过去30天内Audience Manager再次看到该特征的用户数。 例如，假设某个用户在60天前符合某个特征，10天前又再次出现。 在数据中，此用户不会添加到特征计数中，因为他们在30天前首次限定了特征。 但是，实时评估的细分在过去30天的计数中会包含这些信息。 这是因为他们在30天的时间间隔内符合区段条件。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 总人口（现有）</span> </p> </td> 
   <td colname="col2"> <p>截至昨天符合区段条件的实际唯一访客数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Merge Rules]的段填充数据（带有[!UICONTROL Device Graph]选项）

下表定义了使用[!DNL device graph]选项创建的[!UICONTROL Profile Merge Rule]使用区段时的实际实时和总填充量度。 这些是您可用的[!UICONTROL Profile Link Device Graph]、[!DNL Adobe] [!DNL device graph]和其他第三方[!DNL device graph]选项的设备选项设置。


| 列A | 列B |
---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | 当前用户档案与设备图所连接的多达100个其他设备用户档案合并时，实时查看的设备的实际数量包含Audience Manager所看到的区段的特征。 |
| [!UICONTROL Total Population (Existing)] | 具有用户档案的设备总数，当与通过设备图形连接的多达100个其他设备用户档案合并时，这些设备均符合该段的条件。 |

### 在估计段总体时由于最近和频率表达式的限制

[!UICONTROL Segment Builder] 支持对最多包含4个最近和频率表达式的细分规则进行细分大小估计。在构建段规则时选择4个以上的最近和频率表达式会导致在估计种群时段估计器显示错误。

### 在估计段总体时由于[!UICONTROL Merge Rules]的限制

目前，存在已知限制，因为我们的细分大小估计器不包括[!UICONTROL profile merge rules]。 例如，查看具有&#x200B;**[!UICONTROL No Authenticated Profile + Current Device Profile]** [合并规则](../../features/profile-merge-rules/merge-rule-definitions.md)的段。 由于我们目前计算段估计数的方式，估计的总体将包括经过身份验证的用户档案。 但是，现有段群将正确忽略经过身份验证的用户档案。

>[!MORELIKETHIS]
>
>* [配置文件合并规则和设备图常见问题解答](../../faq/faq-profile-merge.md)
>* [配置文件链接](../profile-merge-rules/merge-rules-overview.md)

