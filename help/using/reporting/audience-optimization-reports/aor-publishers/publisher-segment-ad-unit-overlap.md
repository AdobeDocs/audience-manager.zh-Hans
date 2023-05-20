---
description: 「區段至廣告單位重疊」報表會以熱度圖顯示，並反白標示廣告單位與Audience Manager區段之間的高重疊和低重疊。
seo-description: The Segment to Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units and Audience Manager segments.
seo-title: Segment to Ad Unit Overlap
solution: Audience Manager
title: 区段到广告单元重叠
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# 区段到广告单元重叠{#segment-to-ad-unit-overlap}

「區段至廣告單位重疊」報表會以熱度圖顯示，並反白標示廣告單位與Audience Manager區段之間的高重疊和低重疊。

## 用例 {#use-cases}

使用 [!UICONTROL Segment to Ad Unit Overlap] 報表，您可以瞭解哪些對象造訪您的Web屬性。 報表會顯示您的成員之間的重疊 [!DNL Audience Manager] 區段和您Web屬性的訪客數。 重疊程度越高，表示區段的許多成員都會造訪您的Web屬性。

## 使用區段來廣告單位重疊報表 {#using-the-report}

使用 **[!UICONTROL Top N Ad Units]** 和 **[!UICONTROL Top N Segments]** 控制項來選取重疊所需的廣告單位和區段數。 您可以為每個專案選取最多100個專案。

使用 **日期範圍** 和 **日期截止日期** 控制項以調整回溯範圍。 請注意，7天和30天回顧期間僅適用於星期日日期。

使用 **[!UICONTROL Segment Name]** 和 **[!UICONTROL Ad Unit]** 方塊以篩選任何區段和廣告單位。

>[!IMPORTANT]
>
>啟用時 [!UICONTROL Audience Optimization for Publishers]，您必須包含的描述性中繼資料 [!UICONTROL Ad Unit IDs]，如步驟3中所述 [將Google Ad Manager （前身為DFP）資料檔案匯入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). 透過這樣做，您可以確保報告會將Web屬性的詳細資料顯示為 [!UICONTROL Ad Unit] 而非 [!UICONTROL Ad Unit ID].

## 解譯結果 {#interpreting-results}

您的 [!UICONTROL Segment to Ad Unit Overlap] 報表看起來可能類似於下文。 將游標暫留在任何儲存格上，即可取得該特定重疊的詳細資訊。 請參閱範例報表下表中其他資訊的說明。

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 廣告單位 </span> </p> </td> 
   <td colname="col2"> <p>存貨料號的名稱。 例如，這可以是您其中一個網站或您網站上的文章。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 區段即時不重複計數</span> </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時檢視的不重複訪客數量，以及在他們看到時符合區段資格的人數 <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 廣告單位不重複計數</span> </p> </td> 
   <td colname="col2"> <p>此特定廣告單位的訪客數。 此資訊擷取自Google廣告管理員記錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊不重複計數</span> </p> </td> 
   <td colname="col2"> <p>向廣告單位專案展示的區段成員。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊百分比</span> </p> </td> 
   <td colname="col2"> <p>廣告單位和區段母體之間的重疊。 這是 <span class="wintitle"> 重疊不重複計數</span>，以的百分比表示 <span class="wintitle"> 區段即時唯一值</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
