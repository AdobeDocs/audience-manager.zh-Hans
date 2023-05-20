---
description: 傳回特定特徵和整個區段之間共用的不重複使用者人數資料。
seo-description: Returns data on the number of unique users shared between a particular trait and an entire segment.
seo-title: Segment-to-Trait Overlap Report
solution: Audience Manager
title: 区段到特征重叠报表
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Overlap Reports
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 5%

---

# 区段到特征重叠报表{#segment-to-trait-overlap-report}

傳回特定特徵和整個區段之間共用的不重複使用者人數資料。

>[!NOTE]
>
>Audience Manager中的重疊報表遵循RBAC原則。 您只能根據以下專案從您有權存取的資料來源檢視區段和特徵 [rbac使用者群組](/help/using/features/administration/administration-overview.md) 您所屬的。

<!-- 

c_segment_trait_overlap.xml

 -->

## 概述

作為最佳化工具， [!UICONTROL Segment to Trait Overlap] 報表可協助您建立高度聚焦的區段，或擴大區段觸及率。 例如，您可以建立高度重疊的重點區段和特徵，以觸及特定對象。 不過，大量重疊可能代表不重複使用者較少（觸及範圍較小）。 執行此報告可移除有許多區段重疊的特徵，並以重疊較少的特徵取代，以協助擴大觸及率。

### 範例報告

下圖提供 [!UICONTROL Segment-to-Trait Overlap] 報告。

![](assets/segment-to-trait-overlap.png)

### 深入研究個別資料點

選取個別點，以在快顯視窗中檢視資料詳細資訊。 您的點按動作會自動更新報表中顯示的資料。

## 比較區段與特徵 {#comparing-segments-to-traits}

說明如何比較區段和特徵，以從結果中得出有意義的資訊。

<!-- 

c_compare_s2t.xml

 -->

### 比較特徵和區段唯一性：範例

乍看之下，將區段與特徵進行比較並嘗試從結果中得出結論似乎不合邏輯。 畢竟，區段和特徵是不同的，所以從不同的專案衍生的資料有什麼意義？ 不過，在此案例中，我們並非比較特徵和區段，而是比較兩者之間共用的不重複訪客數量。 共用的不重複訪客計數提供通用值，可讓區段與特徵比較。

下圖說明特徵與其所屬區段之間的關係。 在此案例中，我們有一個特徵包含10位訪客，而區段包含1,000位訪客。 他們共用3個不重複訪客。

![](assets/s2t.png)

不重複訪客計數是這些不同物件類別之間共用的共同常數值。 因此，您可以依照下列方式判斷兩者之間的不重複訪客關係：

* 特徵的30%不重複訪客與該區段共用(3/10 = 0.30)。
* 區段與特徵共用0.3%的不重複訪客(3/1,000 = 0.003)

### 尋找區段值以進行特徵比較

檢視特徵和區段之間的重疊有助於估計可用的訪客集區總數（預測），或找出重疊太多且效率低下的區段。

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>預測</b> </td> 
   <td colname="col2"> <p>若要判斷可用的訪客集區，請加總特徵總計（較少重疊）和區段總計（較少重疊）之間的差異。 </p> <p>此區段特徵組合最多可達1004名新使用者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>尋找低效區段</b> </td> 
   <td colname="col2"> <p>如果特徵屬於 <span class="wintitle"> 和</span> 群組，則具有該特徵的不重複訪客已存在於區段中，且無法新增至區段。 您可以使用此報表尋找低重疊的相關特徵，並將其新增至區段定義，藉此擴大該區段受眾集區的觸及率。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 瞭解區段對特徵重疊報表中的資料篩選器 {#data-filters-s2t-report}

說明特徵和區段不重複重疊%滑桿如何運作。

<!-- 

r_s2t_sliders.xml

 -->

此 [!UICONTROL Segment-to-Trait overlap] 報表可讓您使用兩個滑桿，依特徵或區段依重疊百分比篩選資料。

* **[!UICONTROL Filter Trait Uniques %:]** 依特徵和區段之間共用的不重複訪客百分比篩選資料。
* **[!UICONTROL Filter Segment Uniques Overlap %:]** 依區段和特徵之間共用的不重複訪客百分比篩選資料。

### 示例

下圖說明特徵唯一值%與區段唯一值%之間的差異。 在這種情況下，特徵和區段共用3個不重複訪客。 以比例顯示：

* 特徵的30%不重複訪客與該區段共用(3/10 = 0.30)。
* 區段與特徵共用0.3%的不重複訪客(3/1,000 = 0.003)

![](assets/s2t.png)

## 定義的區段對特徵資料快顯欄位 {#fields-defined}

說明當您按一下個別資料點時，彈出式視窗中顯示的量度。

<!-- 

r_s2t_data_pop.xml

 -->

的快顯視窗 [!UICONTROL Segment-to-Trait Overlap] 報表包含下列量度。 請注意，表格中的不重複量度代表 *即時使用者*.

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 區段ID</span></b> </td> 
   <td colname="col2"> 區段的不重複數值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵資料來源 </span></b> </td> 
   <td colname="col2"> 特徵擁有者的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 資料來源型別</span></b> </td> 
   <td colname="col2">定義特徵所屬的提供者型別。 可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一方（您自己的特徵）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方（來自外部資料合作夥伴/廠商）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵ID</span></b> </td> 
   <td colname="col2"> 特徵的不重複數值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵名稱</span></b> </td> 
   <td colname="col2"> 特徵名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵不重複重疊百分比</span></b> </td> 
   <td colname="col2"> 特徵與此區段共用的不重複訪客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 區段不重複重疊百分比</span></b> </td> 
   <td colname="col2"> 某個區段與某個特徵共用的不重複訪客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊不重複專案</span></b> </td> 
   <td colname="col2"> 區段和特徵之間共用的不重複訪客數量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 區段唯一值</span></b> </td> 
   <td colname="col2"> 區段中的不重複訪客數量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵不重複</span></b> </td> 
   <td colname="col2"> 特徵中的不重複訪客數量。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用数据滑块筛选报表结果](../../reporting/dynamic-reports/data-sliders.md)
>* [互動式報表中使用的形狀、顏色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [說明報表圖示和工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重叠报表：更新计划和最小区段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [选定 Audience Manager 报表中的数据取样率和错误率...](../../reporting/report-sampling.md)
>* [重叠报表的 CSV 文件](../../reporting/dynamic-reports/overlap-csv-files.md)

