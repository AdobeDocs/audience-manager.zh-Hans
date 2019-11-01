---
description: 在区段生成器中添加和删除特征，以查看实际特征群体以及实际和估计的区段群体数据。 估计的人口规模数据可帮助您为营销活动构建正确的细分。
seo-description: 在区段生成器中添加和删除特征，以查看实际特征群体以及实际和估计的区段群体数据。 估计的人口规模数据可帮助您为营销活动构建正确的细分。
seo-title: 区段生成器中的特征和区段填充数据
solution: Audience Manager
title: 区段生成器中的特征和区段填充数据
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Trait and Segment Population Data in Segment Builder {#trait-and-segment-population-data-in-segment-builder}

在中添加和删除特征， [!UICONTROL Segment Builder] 以查看实际特征群体以及实际和估计的区段群体数据。 估计的人口规模数据可帮助您为营销活动构建正确的细分。

## 特征群体数据 {#trait-population-data}

[!UICONTROL Segment Builder] 显示 [!UICONTROL Total Trait Population] 向区段添加特征的最后一天。 此数据显示在部分中选定特征周围的蓝色字 [!UICONTROL Basic View] 段中。

![](assets/trait-size.png)

下表定义了特征填充度量

<table id="table_9D837CF9ACA04D04BEE5925EC0B4A5D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 总特征人口</span> </p> </td>
   <td colname="col2"> <p>在其配置文件中具有选定特征的唯一ID的数量。 </p> </td>
  </tr> 
 </tbody> 
</table>

## 计算实数和估计的段总体 {#calculating-real-estimated-populations}

当您创建新细分或更改现有细分时，Audience Manager最多需要24小时才能显示实际实时和总细分人口的结果。

但是，Audience Manager可以立即估计您细分的实时和总人口规模。 这些估计是基于采样的历史数据和95%置信区间的回报结果。

![](assets/confidence-interval.png)

在 [!UICONTROL Segment Builder]中，估计的人口图上的蓝色条指示段大小的可能上限和下限。 虽然过去的表现不能保证将来的结果，但估计的数据可以帮助您了解新区段或已编辑区段的潜在大小。

## 细分人口数据概述 {#segment-populations}

[!UICONTROL Segment Builder] 在创建和编辑区段时显示区段人口数据。

* 对于估计的细分人口数据（实时和总计）, [!UICONTROL Segment Builder] 在您添加或删除细分中的特征时不会自动更新图形。 单击 **[!UICONTROL Calculate Estimates]** 查看（或刷新）估计的人口数。

* 对于实际（实时）细分人口数据（实时和总计）, [!UICONTROL Segment Builder] 在加载现有细分时会自动更新细分图。 对于新区段，或当您向现有区段添加新特征时，实际人口数据直到创建区段后24小时才会更新。

![](assets/segment-data.png)

有关估计和实际细分人口数据的更多信息，请参阅以下定义。

## 定义的估计细分人口数据 {#estimated-segment-population}

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
   <td colname="col1"> <p> <span class="wintitle"> 估计实时人口（潜在） </span> </p> </td> 
   <td colname="col2"> <p>在指定时间范围内实时查看以及在Audience manager看到区段时符合相应资格的唯一访客的估计数。 </p> <p>在 <span class="wintitle"> Segment Builder</span>，特征的最后30天人群(<span class="wintitle"> Total Trait Popets</span>)可以不同于实时评估的特征和区段。 </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">对于特征，最近30天的度量将计算在最近30天内符合该特征的唯一用户数。 </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">对于实时评估的区段，最后30天指标会计算过去某个时间符合某个特征（在该区段中）的用户数，并在过去30天内再次由Audience manager查看。 例如，假设您有一个用户在60天前符合某个特征的条件，并且在10天前再次被看到。 在数据中，此用户不会添加到特征计数中，因为他们在30天前首次符合特征的条件。 但是，实时评估的区段的最后30天计数中会包含这些字段。 这是因为他们在30天的时间间隔内符合区段的条件。 </li>
     </ul> </p> <p> <p>注意：“估 <span class="wintitle"> 计实时人口</span> ”量度不包括基于使用设备图形选项的“配置文件合并规则”提供的连接而符合区段条件的 <span class="wintitle"> 设备</span><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"></a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 估计总人口（潜在）</span> </p> </td> 
   <td colname="col2"> <p>新区段或修改区段中可能存在的唯一访客估计数。 与几乎任何估计一样，过去的绩效并不保证将来的结果，但您可以使用估计的总数来： </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">查看在构建区段时新细分或修订细分可能触及的人数。 </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">根据您的目标调整区段。 例如，较大的细分对品牌认知度营销活动很有用，而较小的细分对于重点定位或重定向营销活动很有用。 </li> 
     </ul> </p> <p> <p>注意：“估 <span class="wintitle"> 计总人口</span> ”量度不包括基于使用设备图形选项的“配置文件合并规则”提供的连接符合区段条件的 <span class="wintitle"> 设备</span><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"></a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 已定义现有（实际）细分人口数据 {#existing-segment-population}

[!UICONTROL Profile Merge Rules] 影响实时和总人口数。 这些总数因区段是否 [!UICONTROL Profile Merge Rule] 使用设备图形选项而异。 另请参阅已定 [义的配置文件合并规则选项](../../features/profile-merge-rules/merge-rule-definitions.md)。

### 无设备图选项的合并规则的细分填充数据

下表定义了在没有设备图表选项的情况下创建的区段使用您的区段时的实际实 [!UICONTROL Profile Merge Rule] 时和总人口量度。 这些是设备选项设 **[!UICONTROL No Device Options]** 置和 **[!UICONTROL Current Device Proflie]**。

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
   <td colname="col2"> <p>在指定时间范围内实时查看的唯一访客的实际数量，以及在Audience manager查看区段时有资格访问这些访客的实际数量。 </p> <p>在 <span class="wintitle"> Segment Builder</span>，特征的最后30天人群(总特征人群<span class="wintitle"></span>)可以不同于实时评估的特征和区段。 </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">对于特征，最近30天的度量将计算在最近30天内符合该特征的唯一用户数。 </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">对于实时评估的区段，最后30天指标会计算过去某个时间符合某个特征（在该区段中）的用户数，并在过去30天内再次由Audience manager查看。 例如，假设您有一个用户在60天前符合某个特征的条件，并且在10天前再次被看到。 在数据中，此用户不会添加到特征计数中，因为他们在30天前首次符合特征的条件。 但是，实时评估的区段的最后30天计数中会包含这些字段。 这是因为他们在30天的时间间隔内符合区段的条件。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 总人口（现有）</span> </p> </td> 
   <td colname="col2"> <p>截至昨天符合此区段资格的实际唯一访客数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 使用设备图选项合并规则的细分填充数据

下表定义了使用设备图形选项创建的区段使用时的实际实时和总 [!UICONTROL Profile Merge Rule] 人口指标。 这些是可供您选择的设 [!UICONTROL Profile Link Device Graph]备选 [!DNL Adobe] 项设置、设备图形和其他第三方设备图形选项。

<table id="table_157EC6E5B5C44EB899854CA10B090F60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 实时人口（现有）</span> </p> </td> 
   <td colname="col2"> <p>实时查看的设备的实际数量与当前配置文件（与通过设备图连接的多达3个其他设备配置文件合并后）包含 <span class="keyword"> Audience Manager查看区段时符合条件的特征</span>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 总人口（现有）</span> </p> </td> 
   <td colname="col2"> <p>配置文件与设备图形连接的多达3个其他设备配置文件合并后，所有设备均符合此区段的条件。 </p> </td>
  </tr>
 </tbody>
</table>

### 在估计段总体时由于最近度和频率表达式的限制

[!UICONTROL Segment Builder] 支持对最多包含4个最近和频率表达式的段规则进行段大小估计。 在建立段规则时选择4个以上的最近度和频率表达式会导致在估计种群时段估计器显示错误。

### 在估计段总体时合并规则的限制

目前，由于我们的细分大小估计器没有考虑配置文件合并规则，因此存在已知的限制。 例如，使用“无验证配置文件”+“当 **前设备配置文件”合并规则查看**&#x200B;区段[](../../features/profile-merge-rules/merge-rule-definitions.md)。 由于我们目前计算细分估计数的方法，估计的总体将包含经过认证的档案。 但是，现有细分群将正确忽略经过身份验证的配置文件。

>[!MORELIKETHIS]
>
>* [配置文件合并规则和设备图常见问题解答](../../faq/faq-profile-merge.md)
>* [配置文件链接](../../features/profile-merge-rules/merge-rules-overview.md)

