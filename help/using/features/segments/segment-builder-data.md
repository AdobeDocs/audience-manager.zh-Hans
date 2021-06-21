---
description: 在区段生成器中添加和删除特征，以查看实际特征人口以及实际和估计的区段人口数据。 预计群体大小数据可帮助您为营销活动构建正确的客户群。
seo-description: 在区段生成器中添加和删除特征，以查看实际特征人口以及实际和估计的区段人口数据。 预计群体大小数据可帮助您为营销活动构建正确的客户群。
seo-title: 区段生成器中的特征和区段人口数据
solution: Audience Manager
title: 区段生成器中的特征和区段人口数据
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: 区段
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1251'
ht-degree: 2%

---

# [!UICONTROL Trait] 和中 [!UICONTROL Segment] 的人口数据  [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

在[!UICONTROL Segment Builder]中添加和删除[!UICONTROL traits]，以查看实际的[!UICONTROL trait]人口以及实际和估计的区段人口数据。 预计群体大小数据可帮助您为营销活动构建正确的客户群。

## [!UICONTROL Trait] 群体数据  {#trait-population-data}

[!UICONTROL Segment Builder] 显示 [!UICONTROL Total Trait Population] 您向区段添加的最后一 [!UICONTROL trait] 天的日期。此数据显示在[!UICONTROL Basic View]部分选定[!UICONTROL trait]周围的蓝色字段中。

![](assets/trait-size.png)

下表定义了特征人口量度：


| 量度 | 描述 |
|---------|----------|
| [!UICONTROL Total Trait Population] | 配置文件中具有选定特征的唯一ID数。 |


## 计算实际和估计的区段人口{#calculating-real-estimated-populations}

创建新区段或更改现有区段时，Audience Manager最多需要24小时才能显示实际实时区段人口和总区段人口的结果。

但是，Audience Manager可以立即估算区段的实时和总人口大小。 这些估计是基于在95%置信区间内采样的历史数据和返回结果。

![](assets/confidence-interval.png)

在[!UICONTROL Segment Builder]中，估计群体图上的蓝色条表示区段大小的可能上限和下限。 尽管过去的性能不能保证将来的结果，但预计数据可以帮助您了解新区段或已编辑区段的潜在大小。

## 区段人口数据概述{#segment-populations}

[!UICONTROL Segment Builder] 在创建和编辑区段时，会显示区段群体数据。

* 对于预计区段人口数据（实时和总计），在区段中添加或删除特征时，[!UICONTROL Segment Builder]不会自动更新图形。 单击&#x200B;**[!UICONTROL Calculate Estimates]**&#x200B;可查看（或刷新）预计群体数。

* 对于实际（实时）区段人口数据（实时和总计），[!UICONTROL Segment Builder]会在加载现有区段时自动更新区段图。 对于新区段，或者向现有区段添加新特征时，实际群体数据只有在创建区段后24小时才会更新。

![](assets/segment-data.png)

有关估计区段人口数据和实际区段人口数据的更多信息，请参阅下面的定义。

## 定义的预计区段人口数据{#estimated-segment-population}

下表定义了估计的群体量度。

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
   <td colname="col2"> <p>在指定的时间范围内实时查看的预计独特访客数，以及在Audience Manager看到符合区段资格条件的独特访客数。 </p> <p>在<span class="wintitle">区段生成器</span>中，特征的最近30天人口（<span class="wintitle">总特征人口</span>）可能与实时评估的特征和区段不同。 </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">对于特征，最近30天量度会计算过去30天内符合该特征的独特用户数。 </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">对于实时评估的区段，最近30天量度会计算过去某个时间点符合某个特征（在该区段中）的条件，且过去30天内Audience Manager再次查看该特征的用户数。 例如，假设某位用户在60天前符合某个特征的条件，且在10天前再次被看到。 在数据中，此用户不会添加到特征计数，因为他们30天前首次符合特征。 但是，这些量度将包含在实时评估的区段的最近30天计数中。 这是因为他们已在30天的时间间隔内符合区段资格条件。 </li>
     </ul> </p> <p> <p>注意：<span class="wintitle">估计实时人口</span>量度不包括根据<span class="wintitle">配置文件合并规则</span>提供的使用<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">设备图选项</a>的连接而符合区段资格条件的设备。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 估计总人口（潜在）</span> </p> </td> 
   <td colname="col2"> <p>新区段或修改区段中可能存在的预计独特访客数。 与几乎任何估计一样，过去的绩效并不保证将来的结果，但您可以使用估计的总数： </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">查看在构建区段时，新区段或已修订区段可能会访问多少人。 </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">根据您的目标调整区段。 例如，较大的客户群对品牌意识营销活动非常有用，而较小的客户群对于集中定位或重新定位营销活动非常有用。 </li> 
     </ul> </p> <p> <p>注意：<span class="wintitle">预计总人口</span>量度不包括根据<span class="wintitle">配置文件合并规则</span>提供的使用<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">设备图选项</a>的连接而符合区段资格条件的设备。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 定义的现有（实际）区段人口数据{#existing-segment-population}

[!UICONTROL Profile Merge Rules] 影响实际实时和总人口数。这些总数因区段所属的[!UICONTROL Profile Merge Rule]是否使用设备图选项而异。 另请参阅[定义的配置文件合并规则选项](../../features/profile-merge-rules/merge-rule-definitions.md)。

### [!UICONTROL Merge Rules]的区段人口数据（不含[!UICONTROL Device Graph Option]）

下表定义了当区段由不带[!UICONTROL device graph]选项的[!UICONTROL Profile Merge Rule]创建时使用的实际实时和总人口量度。 这些是设备选项设置&#x200B;**[!UICONTROL No Device Options]**&#x200B;和&#x200B;**[!UICONTROL Current Device Proflie]**。

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
   <td colname="col2"> <p>在指定的时间范围内实时查看的独特访客的实际数量，以及在Audience Manager看到符合区段资格条件的独特访客的数量。 </p> <p>在<span class="wintitle">区段生成器</span>中，特征的最近30天人口（<span class="wintitle">总特征人口</span>）可能与实时评估的特征和区段不同。 </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">对于特征，最近30天量度会计算过去30天内符合该特征的独特用户数。 </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">对于实时评估的区段，最近30天量度会计算过去某个时间点符合某个特征（在该区段中）的条件，且过去30天内Audience Manager再次查看该特征的用户数。 例如，假设某位用户在60天前符合某个特征的条件，且在10天前再次被看到。 在数据中，此用户不会添加到特征计数，因为他们30天前首次符合特征。 但是，这些量度将包含在实时评估的区段的最近30天计数中。 这是因为他们已在30天的时间间隔内符合区段资格条件。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 总人口（现有）</span> </p> </td> 
   <td colname="col2"> <p>截至昨天，符合该区段资格条件的实际独特访客数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 使用[!UICONTROL Device Graph]选项的[!UICONTROL Merge Rules]区段人口数据

下表定义了当您的区段由使用[!DNL device graph]选项创建的[!UICONTROL Profile Merge Rule]选项使用时，实际的实时和总人口量度。 这些是可用于[!UICONTROL Profile Link Device Graph]、[!DNL Adobe] [!DNL device graph]和其他第三方[!DNL device graph]选项的设备选项设置。


| 列A | B列 |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | 与当前配置文件实时查看的实际设备数量，当这些设备与通过设备图连接的多达100个其他设备配置文件合并时，这些配置文件包含在Audience Manager看到时符合区段资格条件的特征。 |
| [!UICONTROL Total Population (Existing)] | 与设备图连接的多达100个其他设备配置文件合并后，配置文件符合区段条件的设备总数。 |

### 估计区段人口时，由于回访间隔和频度表达式的限制

[!UICONTROL Segment Builder] 支持对最多包含4个回访间隔和频率表达式的区段规则进行区段大小估计。在构建区段规则时选择4个以上的回访间隔和频率表达式，会导致区段估算器在估计群体时显示错误。

### 由于[!UICONTROL Merge Rules]估算区段人口时的限制

目前存在已知的限制，因为我们的区段大小估算器不考虑[!UICONTROL profile merge rules]。 例如，查看具有&#x200B;**[!UICONTROL No Authenticated Profile + Current Device Profile]** [合并规则](../../features/profile-merge-rules/merge-rule-definitions.md)的区段。 由于我们当前计算区段估计数的方式，估计人口将包括经过验证的用户档案。 但是，现有区段人口将正确忽略已验证的用户档案。

>[!MORELIKETHIS]
>
>* [配置文件合并规则和设备图常见问题解答](../../faq/faq-profile-merge.md)
* [配置文件链接](../profile-merge-rules/merge-rules-overview.md)

