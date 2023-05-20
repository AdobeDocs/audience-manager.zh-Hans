---
description: 「廣告單位重疊」報表會以熱度圖顯示，以強調廣告單位之間的高重疊和低重疊。
seo-description: The Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.
seo-title: Ad Unit Overlap
solution: Audience Manager
title: 广告单元重叠
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Audience Optimization Reports
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 2%

---

# 广告单元重叠{#ad-unit-overlap}

此 **[!UICONTROL Ad Unit Overlap]** 報告會以熱度圖顯示，強調廣告單位之間的高重疊和低重疊。

## 用例 {#use-cases}

使用 **[!UICONTROL Ad Unit Overlap]** 報表，您就能深入瞭解對象在Web屬性中重疊的位置。 報表會考量您的100個熱門相關屬性，並顯示它們之間的重疊。

## 使用廣告單位重疊報表 {#using-the-report}

使用 **[!UICONTROL Top N Base Ad Units]** 和 **[!UICONTROL Top N Overlapping Ad Units]** 控制項來選取重疊所需的廣告單位數量。 您可以為每個專案選取最多100個專案。

使用 **日期範圍** 和 **日期截止日期** 控制項以調整回溯範圍。 請注意，7天和30天回顧期間僅適用於星期日日期。

使用 **[!UICONTROL Base Ad Unit]** 和 **[!UICONTROL Overlap Ad Unit]** 控制項以選取要在重疊報表中顯示的廣告單位。

>[!IMPORTANT]
>
>啟用時 [!UICONTROL Audience Optimization for Publishers]，您必須包含的描述性中繼資料 [!UICONTROL Ad Unit IDs]，如步驟3中所述 [將Google Ad Manager （前身為DFP）資料檔案匯入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). 透過這樣做，您可以確保報告會將Web屬性的詳細資料顯示為 [!UICONTROL Ad Unit] 而非 [!UICONTROL Ad Unit ID].

## 解譯結果 {#interpreting-results}

您的 [!UICONTROL Ad Unit Overlap] 報表看起來可能類似於下文。 將游標暫留在任何儲存格上，即可取得該特定重疊的詳細資訊。 請參閱範例報表下表中其他資訊的說明。

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊廣告單位</span> </p> </td> 
   <td colname="col2"> <p>存貨料號的名稱。 例如，這可以是您其中一個網站或您網站上的文章。 在上圖中，基本廣告單位為第9至18條。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 基本廣告單位</span> </p> </td> 
   <td colname="col2"> <p>存貨料號的名稱。 例如，這可以是您其中一個網站或您網站上的文章。 在上圖中，基本廣告單位為文章1 - 8。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊廣告單位不重複計數</span> </p> </td> 
   <td colname="col2"> <p>造訪過廣告單位專案9 - 18的使用者人數。 此資訊擷取自Google廣告管理員記錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 基本廣告單位不重複計數</span> </p> </td> 
   <td colname="col2"> <p>造訪過廣告單位專案1 - 8的使用者人數。 此資訊擷取自Google廣告管理員記錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊不重複計數</span> </p> </td> 
   <td colname="col2"> <p>造訪過您的網站的使用者之間的重疊 <span class="wintitle"> 基本廣告單位</span> 和 <span class="wintitle"> 重疊廣告單位</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊百分比</span> </p> </td> 
   <td colname="col2"> <p>造訪過您的網站的使用者之間的重疊 <span class="wintitle"> 基本廣告單位</span> 和 <span class="wintitle"> 重疊廣告單位</span>. 這是 <span class="wintitle"> 重疊不重複計數</span>，以的百分比表示 <span class="wintitle"> 基本廣告單位</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
