---
description: 在「區段產生器」中新增及移除特徵，以檢視實際特徵母體以及實際和預估的區段母體資料。 預估母體大小資料可協助您為行銷活動建立正確的區段。
seo-description: Add and remove traits in Segment Builder to see actual trait populations along with actual and estimated segment population data. The estimated population size data helps you build the right segment for your campaign.
seo-title: Trait and Segment Population Data in Segment Builder
solution: Audience Manager
title: 区段生成器中的特征和区段人口数据
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 1%

---

# [!UICONTROL Trait] 和 [!UICONTROL Segment] 母體資料於 [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

新增和移除 [!UICONTROL traits] 在 [!UICONTROL Segment Builder] 若要檢視實際值 [!UICONTROL trait] 母體以及實際和預估的區段母體資料。 預估母體大小資料可協助您為行銷活動建立正確的區段。

## [!UICONTROL Trait] 母體資料 {#trait-population-data}

[!UICONTROL Segment Builder] 顯示您 [!UICONTROL Total Trait Population] 在您新增 [!UICONTROL trait] 至區段。 此資料會顯示在您選取專案周圍的藍色欄位中 [!UICONTROL trait] 在 [!UICONTROL Basic View] 區段。

![](assets/trait-size.png)

下表定義特徵母體量度：


| 量度 | 描述 |
|---------|----------|
| [!UICONTROL Total Trait Population] | 個人資料中具有所選特徵的唯一ID數量。 |


## 計算實際和預估區段母體 {#calculating-real-estimated-populations}

建立新區段或變更現有區段時，最多需要24小時才能顯示Audience Manager實際即時和區段總母體的結果。

不過，Audience Manager可以立即估計區段的即時和總母體大小。 這些估計值是根據抽樣歷史資料和95%信賴區間的傳回結果。

![](assets/confidence-interval.png)

在 [!UICONTROL Segment Builder]，預估母體圖表上的藍色長條會指出區段大小的可能上限和下限。 雖然過去的效能無法保證未來的結果，但預估資料可協助您瞭解新區段或已編輯區段的潛在大小。

## 區段母體資料概述 {#segment-populations}

[!UICONTROL Segment Builder] 會在您建立和編輯區段時顯示區段母體資料。

* 針對預估區段母體資料（即時和總計）， [!UICONTROL Segment Builder] 當您新增或移除區段中的特徵時，不會自動更新圖形。 按一下 **[!UICONTROL Calculate Estimates]** 以檢視（或重新整理）預估母體數目。

* 若為實際（即時）區段母體資料（即時和總計）， [!UICONTROL Segment Builder] 載入現有區段時，會自動更新區段圖表。 對於新區段，或是在現有區段新增新特徵時，實際母體資料要等到區段建立後24小時才會更新。

![](assets/segment-data.png)

請參閱下列定義，以取得預估和實際區段母體資料的詳細資訊。

## 已定義的預估區段母體資料 {#estimated-segment-population}

下表定義預估母體量度。

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 預估即時母體（潛在） </span> </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時檢視的不重複訪客的預估數量，以及在Audience Manager看到符合區段資格的人數。 </p> <p>在 <span class="wintitle"> 區段產生器</span>，特徵的最後30天母體(<span class="wintitle"> 特徵母體總數</span>)，對於即時評估的特徵和區段，可能會有所不同。 </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">對於特徵，過去30天的量度會計算過去30天內符合該特徵的不重複使用者人數。 </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">對於即時評估的區段，過去30天的量度會計算過去某個時間點符合某個特徵（在該區段中）的使用者人數，以及過去30天內Audience Manager再次檢視該特徵的使用者人數。 例如，假設您的使用者在60天前符合某個特徵的資格，而10天前又再次出現。 在資料中，此使用者不會新增至特徵計數，因為他們在30多天前才首次符合特徵資格。 不過，它們會包含在即時評估之區段的最後30天計數中。 這是因為他們已在30天的時間間隔內符合區段的資格。 </li>
     </ul> </p> <p> <p>注意： <span class="wintitle"> 預估的即時母體</span> 量度不包含根據提供的連線符合區段資格的裝置 <span class="wintitle"> 設定檔合併規則</span> 使用 <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> 裝置圖表選項</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 預估總人口（潛在）</span> </p> </td> 
   <td colname="col2"> <p>可能位於您新區段或修改過區段的不重複訪客的估計數量。 如同幾乎所有預估一樣，過去的效能無法保證未來的結果，但您可以將預估總計用於： </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">瞭解當您建立區段時，新區段或修訂區段可以影響多少人。 </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">根據您的目標調整區段。 例如，大型區段對品牌認知活動很有用，而小型區段對重點鎖定目標或重新鎖定目標活動很有用。 </li> 
     </ul> </p> <p> <p>注意： <span class="wintitle"> 估計總人口</span> 量度不包含根據提供的連線符合區段資格的裝置 <span class="wintitle"> 設定檔合併規則</span> 使用 <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> 裝置圖表選項</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 已定義的現有（實際）區段母體資料 {#existing-segment-population}

[!UICONTROL Profile Merge Rules] 會影響實際即時和總母體數量。 這些總數會因 [!UICONTROL Profile Merge Rule] 區段所屬是否使用裝置圖表選項。 另請參閱 [定義的設定檔合併規則選項](../../features/profile-merge-rules/merge-rule-definitions.md).

### 以下專案的區段母體資料： [!UICONTROL Merge Rules] 不含 [!UICONTROL Device Graph Option]

下表定義由使用您的區段時的實際即時和總人口量度 [!UICONTROL Profile Merge Rule] 建立時不使用 [!UICONTROL device graph] 選項。 這些是裝置選項設定 **[!UICONTROL No Device Options]** 和 **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 即時母體（現有）</span> </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時檢視的不重複訪客的實際數量，以及在Audience Manager看到符合區段資格的人數。 </p> <p>在 <span class="wintitle"> 區段產生器</span>，特徵的最後30天母體(<span class="wintitle"> 特徵母體總數</span>)，對於即時評估的特徵和區段，可能會有所不同。 </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">對於特徵，過去30天的量度會計算過去30天內符合該特徵的不重複使用者人數。 </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">對於即時評估的區段，過去30天的量度會計算過去某個時間點符合某個特徵（在該區段中）的使用者人數，以及過去30天內Audience Manager再次檢視該特徵的使用者人數。 例如，假設您的使用者在60天前符合某個特徵的資格，而10天前又再次出現。 在資料中，此使用者不會新增至特徵計數，因為他們在30多天前才首次符合特徵資格。 不過，它們會包含在即時評估之區段的最後30天計數中。 這是因為他們已在30天的時間間隔內符合區段的資格。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 母體總數（現有）</span> </p> </td> 
   <td colname="col2"> <p>截至昨天符合區段資格的實際不重複訪客數量。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 以下專案的區段母體資料： [!UICONTROL Merge Rules] 使用 [!UICONTROL Device Graph] 選項

下表定義由使用您的區段時的實際即時和總人口量度 [!UICONTROL Profile Merge Rule] 建立方式 [!DNL device graph] 選項。 這些是的裝置選項設定 [!UICONTROL Profile Link Device Graph]，則 [!DNL Adobe] [!DNL device graph]和其他協力廠商 [!DNL device graph] 您可用的選擇。


| 欄A | 欄B |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | 使用目前設定檔即時檢視的實際裝置數，這些設定檔與最多透過裝置圖表連線的100個其他裝置設定檔合併時，包含當Audience Manager看到符合區段資格的特徵。 |
| [!UICONTROL Total Population (Existing)] | 當具有設定檔的裝置總數與最多100個由裝置圖表連線的其他裝置設定檔合併時，這些裝置都符合區段的資格。 |

### 估算區段母體時，造訪間隔和頻率運算式造成的限制

[!UICONTROL Segment Builder] 支援區段規則的區段大小估計，該區段規則包含最多4個造訪間隔和頻率運算式。 建立區段規則時，選擇超過4個造訪間隔和頻率運算式會導致區段估算器在估算母體時顯示錯誤。

### 限制因 [!UICONTROL Merge Rules] 預估區段母體時

目前已知有一個限制，因為我們的區段大小估算器並未考慮 [!UICONTROL profile merge rules]. 例如，檢視包含 **[!UICONTROL No Authenticated Profile + Current Device Profile]** [合併規則](../../features/profile-merge-rules/merge-rule-definitions.md). 由於我們目前計算區段估計數字的方式，估計母體將包含已驗證的設定檔。 但是，現有的區段母體將正確地忽略已驗證的設定檔。

>[!MORELIKETHIS]
>
>* [配置文件合并规则和设备图常见问题解答](../../faq/faq-profile-merge.md)
>* [配置文件链接](../profile-merge-rules/merge-rules-overview.md)

