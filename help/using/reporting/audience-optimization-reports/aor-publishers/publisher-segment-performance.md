---
description: 「區段效能」報表可依曝光次數和即時區段不重複來比較對應和未對應的區段。 對應的區段是您建立並傳送至目的地以進行定位的區段。 未對應的區段是您已建立但尚未傳送至目的地進行定位的區段。 比較報表內和報表之間的這些不同區段型別，有助於最佳化現有行銷活動，並找出您可能想要傳送至目的地以進行鎖定的被忽略區段。
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and Real-Time Segment Uniques. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: 發佈商的區段效能報表
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Audience Optimization Reports
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 2%

---

# 区段绩效报表{#segment-performance-report}

「區段效能」報表可依曝光次數和即時區段不重複來比較對應和未對應的區段。

對應的區段是您建立並傳送至目的地以進行定位的區段。 未對應的區段是您已建立但尚未傳送至目的地進行定位的區段。

比較報表內和報表之間的這些不同區段型別，有助於最佳化現有行銷活動，並找出您可能想要傳送至目的地以進行鎖定的被忽略區段。

## 用例 {#use-cases}

使用 [!UICONTROL Segment Performance] 報告，您可以：

* 識別帶動規模或效能的對應受眾區段。
* 根據對象對過去績效的貢獻，識別要在未來行銷活動中引入的未對應區段。

## 使用區段績效報表 {#using-segment-performance-report}

切換於 **[!UICONTROL Mapped]** 和 **[!UICONTROL Unmapped]** 以選取是否對應至目的地的區段。 選取 **[!UICONTROL All]** 以將您的所有區段納入報表中。

使用 **日期範圍** 和 **日期截止日期** 控制項以調整回溯範圍。 請注意，7天和30天回顧期間僅適用於星期日日期。

使用 **[!UICONTROL Line Item]** 下拉式方塊以選取您要傳回資訊的Web屬性。

在 **[!UICONTROL Segment Data Source]** 下拉式方塊中，選取包含您想在報表中檢視之區段的資料來源。

使用 **[!UICONTROL Segment]** 下拉式方塊以選取您想在報告中檢視哪些區段。

>[!IMPORTANT]
>
>啟用時 [!UICONTROL Audience Optimization for Publishers]，您必須包含的描述性中繼資料 [!UICONTROL Line Item IDs]，如步驟3中所述 [將Google Ad Manager （前身為DFP）資料檔案匯入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). 透過這樣做，您可以確保報告會將Web屬性的詳細資料顯示為 [!UICONTROL Line Item] 而非 [!UICONTROL Line Item ID].

## 解譯結果 {#interpreting-results}

您的 [!UICONTROL Segment Performance] 報表看起來可能類似於下文。 在您的報表中，按一下泡泡圖以檢視基礎資料。 請參閱範例報表下表中其他資訊的說明。

![](assets/publisher_segment_performance.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>区段 </p> </td> 
   <td colname="col2"> <p>您指派給此區段的英數字元名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>區段ID </p> </td> 
   <td colname="col2"> <p>此區段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>條列專案 </p> </td> 
   <td colname="col2"> <p>您要檢視此報表的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>单击次数 </p> </td> 
   <td colname="col2"> <p>此特徵的成員已點按您Web屬性中的專案的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>展示次数 </p> </td> 
   <td colname="col2"> <p>此特徵的成員已公開至您詳細目錄的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>点进率. </p> <p>此量度會轉送閱聽的百分比，以及點按次數。 將點按數除以曝光數，即可取得此量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>即時區段母體 </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時檢視的實際不重複訪客數量，以及在他們看到時符合區段資格的人數 <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何讀取對應的區段結果 {#read-mapped-segment}

報表中對應區段的位置可告知您哪些區段表現良好，以及您可能需要在何處進行某些調整。

若要閱讀報表，將結果分成四個區段會有幫助，其中虛線（紅色）與下列範例報表中所顯示的類別。 範例中的標籤可協助您瞭解區段效能，以及如何回應這些結果。

![](assets/publisher_segment_performance_mapped.png)

## 如何讀取未對應的區段結果 {#read-unmapped-segment}

在中檢視未對應的區段 [!UICONTROL Segment Performance] 報表是尋找您尚未考慮用於鎖定目標的新區段的絕佳方式。 事實上，其中某些區段的表現可能會優於對應的區段。

若要閱讀此報告，將結果分成四個區段會有幫助，虛線（紅色）和類別如下方範例報告中所示。

![](assets/publisher_segment_performance_unmapped.png)
