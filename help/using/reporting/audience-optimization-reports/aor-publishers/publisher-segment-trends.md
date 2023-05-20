---
description: 「區段趨勢」報表會傳回對應和未對應區段在一段時間內的曝光次數和點進率資料。 對應的區段是您建立並傳送至目的地以進行定位的區段。 未對應的區段是您已建立但尚未傳送至目的地進行定位的區段。 比較您選取量度的趨勢和數量，以更清楚瞭解對象在一段時間內的行為。
seo-description: The Segment Trend report returns data on impressions and click-through rates of mapped and unmapped segments over time. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Compare trends and volume for your selected metrics to get a better picture of how your audiences behave over time.
seo-title: Segment Trend Report
solution: Audience Manager
title: 区段趋势报表
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization Reports
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 2%

---

# 区段趋势报表{#segment-trend-report}

「區段趨勢」報表會傳回對應和未對應區段在一段時間內的曝光次數和點進率資料。

對應的區段是您建立並傳送至目的地以進行定位的區段。 未對應的區段是您已建立但尚未傳送至目的地進行定位的區段。

比較您選取量度的趨勢和數量，以更清楚瞭解對象在一段時間內的行為。

## 用例 {#use-cases}

使用 [!UICONTROL Segment Trend] 報表可驗證區段在一段時間內的效能，並根據強大的效能或規模找出趨勢。

透過此報告，您可以瞭解哪些Web屬性會顯示谷值或錯誤增加，並視需要疑難排解。 此報表是您識別感興趣對象後的下一個步驟。 [!UICONTROL Segment Performance] 報告，以確保您在中看到的強大或低效效能 [!UICONTROL Segment Performance] 標籤會隨著時間而改變。

## 使用區段趨勢報表 {#using-the-report}

切換於 **[!UICONTROL Mapped]** 和 **[!UICONTROL Unmapped]** 以選取是否對應至目的地的區段。 選取 **[!UICONTROL All]** 以將您的所有區段納入報表中。

使用調整回顧視窗 **[!UICONTROL Date Through]** 滑桿。

按一下下方的任何區段 **[!UICONTROL Date Through]** 滑桿，可顯示僅將該區段保留在報表中或將其排除的選項。

使用 **[!UICONTROL Line Item]** 下拉式方塊，選取您想要傳回資訊的投資組合中的屬性。

在 **[!UICONTROL Segment Data Source]** 下拉式方塊中，選取包含您想在報表中檢視之區段的資料來源。

使用 **[!UICONTROL Segment]** 下拉式方塊以選取您想在報告中檢視哪些區段。

>[!IMPORTANT]
>
>啟用時 [!UICONTROL Audience Optimization for Publishers]，您必須包含的描述性中繼資料 [!UICONTROL Line Item] ID，如步驟3中所述， [將Google Ad Manager （前身為DFP）資料檔案匯入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). 透過這樣做，您可以確保報告會將Web屬性的詳細資料顯示為 [!UICONTROL Line Item] 而非 [!UICONTROL Line Item] ID。

## 解譯結果 {#interpreting-results}

此 [!UICONTROL Segment Trend] 報表只會傳回14天間隔的線圖資料。 在此範例中，報表會顯示一組對應和未對應區段的曝光次數和點進趨勢。

將滑鼠指標暫留在任何線條上，即可取得該特定區段趨勢的詳細資訊。 請參閱範例報表下表中其他資訊的說明。

![](assets/publisher_segment_trend.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 区段</span> </p> </td> 
   <td colname="col2"> <p>您指派給此區段的英數字元名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 區段ID</span> </p> </td> 
   <td colname="col2"> <p>此區段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 條列專案</span> </p> </td> 
   <td colname="col2"> <p>您要檢視此報表的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 单击次数</span> </p> </td> 
   <td colname="col2"> <p>此特徵的成員已點按您Web屬性中的專案的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 展示次数</span> </p> </td> 
   <td colname="col2"> <p>此特徵的成員已公開至您詳細目錄的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">CTR</span> </p> </td> 
   <td colname="col2"> <p>点进率. 此量度會轉送閱聽的百分比，以及點按次數。 將點按次數除以曝光次數，即可取得此量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 區段唯一值</span> </p> </td> 
   <td colname="col2"> <p>過去30天內的區段成員數。 </p> </td> 
  </tr> 
 </tbody> 
</table>
