---
description: Audience Marketplace資料購買者同意報告使用資料摘要中包含的特徵提供的所有廣告曝光次數，這些特徵價格依據每千次廣告曝光次數(CPM)而定。 CPM使用量會在每個日曆月的第5天到期，並包含前一個月的資料。 固定費用訂閱者不需要報告使用量。
seo-description: Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions (CPM) basis. CPM usage is due on the 5th day of each calendar month and includes data for previous month. Flat fee subscribers do not need to report usage.
seo-title: Billing for Data Feed Buyers
solution: Audience Manager
title: 面向数据信息源购买者的账单
keywords: 區段層級報表、區段層級、區段層級
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2002'
ht-degree: 1%

---

# 面向数据信息源购买者的账单 {#billing-for-data-feed-buyers}

Audience Marketplace資料購買者同意報告使用資料摘要中包含的特徵所提供的所有廣告曝光次數，這些特徵的定價依據是每千個廣告曝光次數的成本([!DNL CPM])為基礎。 [!DNL CPM] 使用情形的截止日期是每個日曆月的第5天，且包含上個月的資料。 固定費用訂閱者不需要報告使用量。

<br> 

## 如何報告CPM使用量 {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] 資料購買者同意報告使用資料摘要中包含的特徵提供的所有廣告曝光次數，這些特徵的定價依據是每千個廣告曝光次的費用([!DNL CPM])為基礎。 [!DNL CPM] 使用情形的截止日期是每個日曆月的5日，包含上個月的資料。 固定費用訂閱者不需要報告使用量。

[!UICONTROL Audience Marketplace] 提供兩種報告方式 [!DNL CPM] 使用狀況：

* **區段層級報表**：此為建議選項 [!DNL CPM] 使用情況報告方法。 當您報告時 [!DNL CPM] 區段層級的使用量時，資料摘要層級報表區段會根據中所述的演演算法，自動填入對應的使用量金額。 [CPM資料摘要的成本歸因](#cost-attribution).
* **資料摘要層級報表**：此方法需要您個別報告 [!DNL CPM] 每個資料摘要的使用情況，根據中所述的演演算法 [CPM資料摘要的成本歸因](#cost-attribution). 不過，此方法比區段層級報告更單調乏味，且容易出錯。

<br> 

## 報告區段層級的CPM使用量 {#segment-level-report}

此 [!UICONTROL Segment Usage] 索引標籤可讓您報告區段層級的使用量，同時顯示按其對應的目的地分組的區段。

報告後 [!DNL CPM] 區段層級的使用狀況、 [!UICONTROL Audience Marketplace] 會根據 [CPM資料摘要的成本歸因](#cost-attribution).

至報表 [!DNL CPM] 區段層級的使用狀況：

1. 前往 **[!UICONTROL Audience Marketplace > Payables]**.
1. 選取 **[!UICONTROL Segment Usage]** 標籤。
1. 填寫區段的使用情況。 您可以使用 [!UICONTROL Search] 方塊來篩選區段（若您只需要報告其中部分割槽段的使用量）。
1. 单击 **[!UICONTROL Edit Segments Usage]**.
1. 輸入 [!DNL CPM] 中的使用量 [!UICONTROL Usage] 欄。
1. 按一下 **[!UICONTROL Save]** 完成後，請檢閱確認對話方塊。

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. 单击 **[!UICONTROL Confirm]**.

另請觀看我們的影片示範，瞭解如何報告區段層級的使用情況：

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## 在資料摘要層級報告CPM使用量 {#feed-level-report}

資料摘要層級報告是更單調乏味且容易出錯的程式，因為您必須個別計算 [!DNL CPM] 每個資料摘要的使用情況。 我們建議您 [報告區段層級的CPM使用量](#segment-level-report) 而非。

至報表 [!DNL CPM] 區段層級的使用狀況：

1. 前往 **[!UICONTROL Audience Marketplace > Payables]**.
2. 選取 **[!UICONTROL Feed Usage]** 標籤。
3. 使用 [!UICONTROL Search] 方塊來篩選資料摘要，並識別您需要為其報告使用情況的資料摘要。
4. 单击 **[!UICONTROL Edit Feeds Usage]**.
5. 計算 [!DNL CPM] 每個資料摘要的使用情況根據 [CPM資料摘要的成本歸因](#cost-attribution)，並在 [!UICONTROL Usage] 欄。
6. 按一下 **[!UICONTROL Save]** 完成後，請檢閱確認對話方塊。

   ![confirm-feed-use](assets/confirm-feed-usage.png)

7. 单击 **[!UICONTROL Confirm]**.

<br> 

## 大量報告

減少報告時的錯誤與額外負荷 [!DNL CPM] 使用情形，您可使用大量報告選項下載 [!DNL CSV] 包含資料摘要和區段的檔案、填寫使用方式，然後將其上傳回 [!DNL Audience Manager]. 您可以使用大量報告來報告摘要和區段使用情況。

待更新 [!DNL CPM] 大量使用量：

1. 前往 **[!UICONTROL Audience Marketplace > Payables]**.
1. 選取 **[!UICONTROL Feed Usage]** 或 **[!UICONTROL Segment Usage]** 索引標籤，視您要更新的報表型別而定。
1. 按一下 **[!UICONTROL Edit Feeds Usage]** 或 **[!UICONTROL Edit Segments Usage]**.
1. 按一下 **[!UICONTROL download the current usage]** 以確保您使用有效的CSV檔案。
1. 開啟電腦上的檔案，並填寫使用情況報表。
1. 按一下 **[!UICONTROL Choose a CSV file]** 上傳更新的使用量報告。

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] 上傳檔案後會立即驗證該檔案，並在偵測到檔案中是否有任何錯誤時提示您。

<br> 

### 大量報告驗證錯誤

| 错误消息 | 描述 | 修复了“未定义”错误地 |
| ------------- | -------------| -----|
| 無效的輸入 | [!DNL Audience Manager] 偵測到 [!DNL CSV] 檔案結構描述，例如缺少欄或欄標題變更。 | 避免變更表格結構。 |
| 未找到” | 對象 [!UICONTROL Segment Level Reporting]， [!DNL Audience Manager] 無法識別 [!UICONTROL Segment ID] 和 [!UICONTROL Destination ID] 組合。 對象 [!UICONTROL Feed Level Reporting]， [!DNL Audience Manager] 無法識別 [!UICONTROL Data Provider Name]， [!UICONTROL Feed Name]、和 [!UICONTROL Use Case] 組合。 | 對象 [!UICONTROL Segment Level Reporting]，檢查 [!UICONTROL Segment ID] 和 [!UICONTROL Destination ID] 組合。 對象 [!UICONTROL Feed Level Reporting]，檢查 [!UICONTROL Data Provider Name]， [!UICONTROL Feed Name]、和 [!UICONTROL Use Case] 組合。 |
| 找到重複的記錄 | [!DNL Audience Manager] 偵測到具有不同曝光值的重複記錄。 | 檢閱報表，並確認您未針對相同的資料摘要或區段報告不同的使用量值。 |
| 不支援的值 | [!DNL Audience Manager] 在中偵測到非數值 [!DNL Audience Manager] 欄。 | 檢閱報告，並確認您只在 [!DNL Audience Manager] 欄。 |
| 必填欄位的標題遺失 | [!DNL Audience Manager] 偵測到必要欄位遺漏表格標頭。 對象 [!UICONTROL Segment Level Reporting]，必填欄位為： [!UICONTROL Segment ID]， [!UICONTROL Destination ID]. 對象 [!UICONTROL Feed Level Reporting]，必填欄位為： [!UICONTROL Data Provider Name]， [!UICONTROL Data Feed Name]，  [!UICONTROL Use Case] | 檢閱報告，並確認表格標題未遭竄改。 |

>[!NOTE]
>從移除列 [!DNL CSV] 使用情況報告對現有使用情況報告沒有任何影響。 [!DNL Audience Manager] 僅處理報表中包含的欄位。

<br> 

## [!DNL CPM] 報告最佳實務

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recommendations </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>一律報告曝光總數</b> </p> </td> 
   <td colname="col2"> <p>若為CPM曝光總數： </p>
   <p> 報告曝光總數，但不使用小數。 Audience Manager會根據您報告的總數自動計算CPM。</p><p>如果您需要報告1,234,567次曝光，請如實報告。 您不需要將曝光總數除以1,000即可計算CPM。</p><p>用來使用Adobe Target或Analytics目的地等工具最佳化您的網頁或應用程式內容（內容最佳化）的特徵，不會貢獻CPM計畫的使用量總計。 資料提供者通常會使用固定費用計畫獲得內容最佳化的補償。</p><p>另請參閱 <a href="#cost-attribution">CPM資料摘要的成本歸因</a> 以取得詳細資訊。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>遵循每月報告間隔</b> </p> </td> 
   <td colname="col2"> <p>報表系統會在每月5日之後關閉。 如果您無法在此日期之前報告CPM使用量，則必須將該金額新增至下一月的報表中。 例如，假設您在10月使用1000次曝光、錯過10月報告期限，並在11月使用1000次曝光。 在此情況下，您會在12月報告10月和11月總計(2000)，介於1日到5日之間。</p><p><b>秘訣</b>：您應一律嘗試在下個月的第1天和第5天之間報告上個月的CPM使用量。</p><p>您可以報告最晚在新日曆月5日的CPM使用量，但不建議這麼做。 在每月5日前報告CPM使用量，可讓Audience Manager有時間檢查及處理資料。</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## CPM資料摘要的成本歸因 {#cost-attribution}

在 [!UICONTROL Audience Marketplace] 您必須針對每個區段，每月自行報告曝光金額。 我們建議使用報告功能 [!DNL CPM] 區段層級的使用狀況，以便自動進行成本歸因。

<!-- marketplace_cpm_billing.xml -->

### 帳單摘要 {#billing-summary}

您必須提交 [!DNL CPM] 每個日曆月的第1天和第5天之間的資料摘要曝光量。 若要正確執行此操作，我們建議您 [報告區段層級的CPM使用量](#segment-level-report).

>[!TIP]
>當您報告時 [!DNL CPM] 區段層級的使用量時，資料摘要層級報表區段會自動填入對應的使用量金額。

您是否需要 [!UICONTROL Report CPM Usage at Data Feed Level]，您必須個別編譯每個摘要在上一個日曆月傳送的所有曝光數，並根據本文所述的計費分配回報。

在您報告之後 [!DNL CPM] 前一個日曆月的編號， [!DNL Adobe] 將執行下列動作：

* 建立商業發票，並根據下列專案開立帳單： [!DNL CPM] 每個訂閱資料摘要的速率。
* 根據您報告的，支付資料提供者（賣家）所缺費用 [!DNL CPM] use.

>[!IMPORTANT]
>
>身為購買者，所有回報的曝光總數都必須為真實且準確。 如果您未依每個月的第5天報告曝光總數，則必須包含下個月未報告月份的總數。

<br> 

## 根據特徵資格規則在摘要層級指派曝光 {#assign-impressions}

此 [!UICONTROL Activation] 使用案例可讓您在對應的資料摘要中使用特徵，在 [區段產生器](../../../features/segments/segment-builder.md) 並將這些區段對應至目的地。 布林值運運算元 [!UICONTROL AND]， [!UICONTROL OR]、和 [!UICONTROL NOT] 可讓您設定特徵和區段資格條件。

當您 [在資料摘要層級報告CPM使用量](#feed-level-report)，您必須根據每個資料摘要的 [!DNL Boolean] 特徵資格規則中使用的運運算元。 下表列出如何依布林值規則或特徵型別正確分配曝光次數。

>[!TIP]
>[報告區段層級的CPM使用量](#segment-level-report) 讓Audience Manager自動完成資料摘要層級報告。

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 規則資格邏輯或型別 </th> 
   <th colname="col2" class="entry"> 帳單分配 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 且</span> </p> </td> 
   <td colname="col2"> <p>將100%的傳遞曝光總數套用至使用布林值的規則型區段中的所有提供者特徵 <span class="wintitle"> 和</span> 條件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 或者</span> </p> </td> 
   <td colname="col2"> <p>將傳遞的曝光總計的加權配置套用至使用布林值OR條件的規則型區段中的所有提供者特徵。 加權配置使用下列公式計算：</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>將100%的傳遞曝光總數套用至使用布林值的規則型區段中的所有提供者特徵 <span class="wintitle"> NOT</span> 條件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>演演算法區段 </p> </td> 
   <td colname="col2"> <p>將100%已傳遞的曝光總數套用至包含演演算法特徵的區段中的所有提供者摘要。 </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## 計費範例 {#billing-examples}

以下範例旨在說明如何 [!DNL CPM] 使用配置在資料摘要層級完成。

>[!IMPORTANT]
>我們建議您 [報告區段層級的CPM使用量](#segment-level-report) 而是讓此程式自動完成。

讓我們考慮下列情況：

![billing-examples](assets/billing-examples.png)

<br> 

### 案例1：具有AND資格規則的區段

此區段包含來自不同資料提供者的3個特徵。 由於區段資格是根據 [!UICONTROL AND] 條件，訪客必須實現所有三個摘要中的特徵，才能符合區段的資格。

![](assets/billing-segment-and.png)

使用 [!UICONTROL AND] 條件，您必須將當月收到的100%曝光數指派給全部三個資料提供者。 在 [!UICONTROL Audience Marketplace > Payables] 區段，您會向每個提供者評分1,000,000次曝光。

此範例適用於使用的區段 [!DNL Boolean] [!UICONTROL NOT] 運運算元或適用於包含演演算法特徵的區段。

<br> 

### 案例2：具有OR資格規則的區段

此區段包含來自不同資料提供者的3個特徵。 由於區段資格是根據 [!UICONTROL OR] 條件，訪客必須實現三個特徵中的至少一個才能符合該區段的資格。

我們無法分辨哪個特徵對曝光負責，因為資格是以 [!UICONTROL OR] 條件。 因此，在 [!UICONTROL Audience Marketplace > Payables] 區段您會根據特徵母體，以曝光總數的加權配置來貸記給每個提供者。

![billing-segment-or](assets/billing-segment-or.png)

<br> 

### 案例3：包含模型與啟用使用案例的區段

此範例說明根據兩個資料摘要使用案例的歸因 — 建模和啟動。 在此範例中，我們檢視了提供下列資訊的兩個資料提供者：

![資料摘要](assets/feed-use-cases.png)

在下表中，區段X包含兩個特徵T1和T2，區段規則T1或T2，其中：

* T1是資料摘要A中的特徵；
* T2是根據資料摘要A和資料摘要B的第三方特徵模型化的演演算法特徵。

區段已對應至目的地，而且一個月內會為此區段輸入1,000,000次曝光次數，使用 [區段層級報表](#segment-level-report).

這1,000,000次曝光中：

* T1佔區段母體的40%，這表示對摘要A有400,000次曝光。
* T2佔區段母體的60%，這表示對摘要A和摘要B有600,000次曝光。

在資料摘要層級，曝光的分配方式為：

* 資料摘要A會從特徵T2 （根據資料摘要A和資料摘要B的特徵建模，因此兩者都會收到曝光數）接收600,000次曝光數，並從特徵T1 （資料摘要A的特徵）接收400,000次曝光數，總計為1,000,000次曝光數。
* 資料摘要B從特徵T2接收600,000次曝光數（請參閱以上說明），並從特徵T1接收0次曝光數。

依資料摘要和使用案例的概要劃分如下：

![摘要 — 劃分](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>對於模型使用案例，您應該只報告啟動時的CPM使用量。 如果您只執行模型，但不啟動模型，則不需要使用情況報表。

<br> 

## 固定費用資料摘要的計費和曝光分配 {#billing-flat-fee}

固定費用資料摘要每個月都會向您收取固定金額，無論訂閱何時開始或您使用的曝光次數為何。 部分月份的使用或間隔不會按比例分攤費用。 與CPM帳單一樣，Adobe會產生發票，並以您訂閱的資料摘要的每月固定費用率向您收費。

例如，假設您決定於月中開啟摘要中的某些特徵。 無論您何時開始訂閱或啟動特定特徵，您仍需按每月全額費率付費。
