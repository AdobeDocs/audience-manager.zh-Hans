---
description: 此報表會傳回在詳細目錄上收集並傳送至Audience Manager之所有未使用資訊的頻率計數。
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: 未使用的信号报表
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 8fd148df6c19a5d8331faf66c671f91686954a77
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 2%

---

# 未使用的信号报表{#unused-signals-report}

此報表會傳回在詳細目錄上收集並傳送至Audience Manager之所有未使用資訊的頻率計數。 若要存取此報表，請導覽至 **Analytics >受眾報表>其他報表>未使用的訊號**.

>[!NOTE]
>
>如果您看到「您沒有對象報表的存取權」訊息，請聯絡您的Audience Manager顧問或客戶服務，以布建報表。

![未使用的訊號報表熒幕擷圖](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## 概述

訊號是來自您網站的資訊，已傳入 [!DNL Audience Manager] 形式為 [機碼值組](../../reference/key-value-pairs-explained.md) (例如， `color=blue, price>100, gender=female`、等)。

未使用的訊號包含您收集但尚未對應至特徵的資料。 此 [!UICONTROL Unused Signals] 報告會依日期、索引鍵、值和頻率計數，在表格中顯示資料。 任何傳入的未對應訊號 [!DNL Audience Manager] 一天至少符合100次資格 [!UICONTROL Unused Signals] 報告。 未使用的訊號會儲存45天，然後捨棄。

請檢閱此報表，協助識別可對應至新特徵或現有特徵的孤立訊號。

>[!NOTE]
>
>在搜尋欄位中指定索引鍵或值名稱，以將結果限製為特定記錄。

## 用例

<table id="table_E5EE0EC078E14EF4B197243488517A2D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 示例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>確保特徵一致性或將相關值新增至單一索引鍵</b> </p> </td> 
   <td colname="col2"> <p>請檢閱報告，說明特定訊號的不同值變化。 </p> <p>例如，假設您在機碼值組中將「北卡羅來納州」的特徵定義為 <code> c_state = North Carolina</code>. 報表可協助您尋找名稱變體，並將其新增至特徵(例如 <code> c_state = North Carolina, NC, N.C., NCarolina</code>)。 或者，您也可以使用報告找出名稱變體，並將這些變體取代為所有網站的統一值。 </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>建立新特徵</b> </p> </td> 
   <td colname="col2"> <p>檢閱報告，檢視在特定索引鍵上傳入了哪些新值。 您可能想要根據這些新值建立新的機碼值組。 </p> <p> <p>注意：請每兩週檢查一次報表中是否有經常變更的值（例如節目、行銷活動、名人等）。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>尋找未對應的值</b> </p> </td> 
   <td colname="col2"> <p>檢閱數字1的報告。 中的數字1 <span class="wintitle"> 未使用的訊號</span> 報表代表null值。 這並不一定是壞事。 這僅表示特定索引鍵沒有關聯的值對應。 如果您看到重要變數的大量1個值，請洽詢您的網站團隊，確認所有頁面都已正確標籤。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最佳实践

執行並檢查 [!UICONTROL Unused Signals] 報告：

* 建立特徵或更新特徵規則之後。 這有助於確保您的特徵和規則已正確設定。 結果中的數字1表示新特徵可能未正確設定。
* 每兩週或每月。 已排程的檢閱有助於確保特徵對應是最新的。

>[!NOTE]
>
>在報告中搜尋未使用的值時，請考慮以下特殊性。 以下兩個範例之間的運算式不同：

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a！=23))
* 這兩個範例都顯示一個特徵，其中包含兩個機碼值組v和a。第一個運算式會轉換為：特徵包含值為1的索引鍵v [!UICONTROL AND NOT] 索引鍵a具有值23。 第二個運算式包含值為1的索引鍵v [!UICONTROL AND] 具有值的索引鍵a [!UICONTROL NOT EQUAL] 23.
* 考慮到上述兩種不同的運算式，假設您在 [!UICONTROL Unused Signals Report] 對於在索引鍵a上傳遞的值，如果值的值不是23，則只有在第一種情況下才會獲得結果，因為索引鍵的值完全沒有傳送。 在第二個案例中，系統傳送了與23不同的值，因此機碼a並未使用。

## 大量特徵建立

如果您需要根據從取得的資料大量建立許多特徵，請聯絡您的合作夥伴解決方案代表。 [!UICONTROL Unused Signals] 報告。
