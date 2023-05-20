---
description: 建立和管理在相似建模中使用的特徵或區段。
keywords: 相對權重，相似對象
seo-description: Build and manage the traits or segments used in look-alike modeling.
seo-title: About Look-Alike Modeling
solution: Audience Manager
title: 關於相似建模
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1576'
ht-degree: 1%

---

# 瞭解 [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## 透過以下方式尋找新使用者 [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] 可協助您透過自動化資料分析，探索新的不重複受眾。 當您選取「 」時，程式就會開始 [!UICONTROL trait] 或 [!UICONTROL segment]、時間間隔，以及第一方和第三方 [!UICONTROL data sources]. 您的選擇會提供演演算法模型的輸入。 分析程式執行時，會根據所選母體的共用特性來尋找合格使用者。 完成後，此資料可用於 [特徵產生器](../../features/traits/about-trait-builder.md) 您可以在其中根據下列專案建立特徵： [精確度和觸及](../../features/traits/trait-accuracy-reach.md). 此外，您也可以建立將演演算法特徵與下列專案結合的區段： [!UICONTROL rules-based traits] 並新增其他資格要求 [!DNL Boolean] 運算式和比較運運算元。 [!UICONTROL Look-Alike Modeling] 可讓您以動態方式從所有可用特徵資料中擷取值。

## 优势 {#advantages}

使用的主要優點 [!UICONTROL Look-Alike Modeling] 包括：

* **資料準確度：** 演演算法會定期執行，有助於保持結果的最新性和相關性。
* **自動化：** 您不需要管理大量靜態規則。 演演算法會為您尋找對象。
* **節省時間並減少工作量：** 使用我們的模型化程式，您不必猜測什麼 [!UICONTROL traits]/[!UICONTROL segments] 可能會花時間在行銷活動上，以探索新對象。 模型可以為您執行此操作。
* **可靠性：** 模型適用於伺服器端探索和資格鑑定程式，以評估您自己的資料和您有權存取的選定第三方資料。 這表示您不需要看見網站上的訪客，就能符合特徵資格。

## 工作流 {#workflow}

您管理模型 **[!UICONTROL Audience Data > Models]**. 在高層面上，工作流程程式涉及以下內容：

* 選取您要演演算法評估的基準線資料。 這包括 [!UICONTROL trait] 或 [!UICONTROL segment]，時間範圍，和 [!UICONTROL data sources] （您自己的資料和您已透過存取的第三方資料） [!DNL Audience Manager])。 在模型建立工作流程中，您可以排除 [!UICONTROL traits] 您不想干擾模型。
* 儲存您的模型。 儲存後，演演算法評估程式會自動執行。 但請注意，此程式最多可能需要7天才能完成。 [!DNL Audience Manager] 演演算法完成且結果可供使用時傳送電子郵件給您 [!UICONTROL trait] 建立。
* 建置演演算法 [!UICONTROL traits] 在 [!UICONTROL Trait Builder].
* 合併 [!UICONTROL traits] 到 [!UICONTROL segments] 在 [!UICONTROL Segment Builder].
* 建立並傳送 [!UICONTROL segment] 資料至 [!UICONTROL destination].

## 故障排除 {#troubleshooting}

我們停用任何 [!UICONTROL Look-Alike Model] 無法產生連續三個回合的資料。 請注意，您之後無法將模型的狀態設定回「使用中」。 為確保您的模型產生資料，我們建議您從資料來源建立模型，並具備足夠的 [!UICONTROL traits] 以從中累積資料。

## 瞭解 [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] 是一種專有的演演算法，用來發現新的 [!UICONTROL traits] 自動。 它比較 [!UICONTROL trait] 您目前的資料 [!UICONTROL traits] 和 [!UICONTROL segments] 針對您有權存取的所有其他第一方和第三方資料 [!DNL Audience Manager]. 請參閱本節，瞭解 [!UICONTROL TraitWeight] 演演算法探索程式。

![](assets/algo_model.png)

下列步驟說明 [!UICONTROL TraitWeight] 評估程式。

### 步驟1：建立基準線 [!UICONTROL Trait] 比較

若要建立基準線， [!UICONTROL TraitWeight] 測量所有 [!UICONTROL traits] 30、60或90天間隔內與對象建立關聯。 接下來，它會排名 [!UICONTROL traits] 根據它們的頻率和相關性。 頻率計數會測量通用性。 關聯會測量發生錯誤的可能性 [!UICONTROL trait] 僅存在於基線對象中。 [!UICONTROL Traits] 這些經常出現據說表現出高度的共性，這是結合時用來設定加權分數的重要特性 [!UICONTROL traits] 在您選取的專案中探索 [!UICONTROL data sources].

### 步驟2：找到相同專案 [!UICONTROL Traits] 在 [!UICONTROL Data Source]

在建置要比較的基準線後，演演算法會尋找完全相同的 [!UICONTROL traits] 在您選取的專案中 [!UICONTROL data sources]. 在此步驟中， [!UICONTROL TraitWeight] 執行所有發現的頻率計數 [!UICONTROL traits] 並將它們與基準線做比較。 不過，與基線不同，不常見 [!UICONTROL traits] 排名高於出現頻率較高的專案。 罕見 [!UICONTROL traits] 據說具有高度的特異性。 [!UICONTROL TraitWeight] 評估通用基準線的組合 [!UICONTROL traits] 和不常見（高度特定） [!UICONTROL data source] [!UICONTROL traits] 影響力或吸引力大於 [!UICONTROL traits] 兩個資料集都有。 事實上，我們的模型能辨識這些大型的、常見的 [!UICONTROL traits] 且不會將過多優先順序指派給具有高關聯性的資料集。 罕見 [!UICONTROL traits] 獲得更高的優先順序，因為它們更有可能代表新的、不重複的使用者，而不是 [!UICONTROL traits] 通用性高。

### 步驟3：指定權重

在此步驟中， [!UICONTROL TraitWeight] 新發現的排名 [!UICONTROL traits] 依影響力或可取性的順序排列。 重量比例是從0%到100%的百分比。 [!UICONTROL Traits] 排名更接近於100%，表示他們更像是基線母體中的受眾。 此外，權重也較高 [!UICONTROL traits] 很有價值，因為它們代表全新的不重複使用者，其行為可能與您建立的基線受眾類似。 請記住， [!UICONTROL TraitWeight] 考量 [!UICONTROL traits] 在基準線中具有高度共性，且在比較的資料來源中具有高度特異性，因此比以下用途更有價值： [!UICONTROL traits] 在每個資料集中都很常見。

### 步驟4：評分使用者

所選中的每個使用者 [!UICONTROL data sources] 會獲得使用者分數，該分數等於具有影響力之使用者所有權重的總和 [!UICONTROL traits] 在該使用者的設定檔上。 然後會將使用者分數標準化，在0到100%之間。

### 步驟5：顯示和使用結果

[!DNL Audience Manager] 顯示加權模型結果於 [!UICONTROL Trait Builder]. 當您想要建置 [!UICONTROL algorithmic trait]， [!UICONTROL Trait Builder] 可讓您建立 [!UICONTROL traits] 根據資料執行期間演演算法產生的加權分數。 您可以選擇更高的準確度，以僅符合擁有非常高使用者分數、因此與基線對象（而非其餘對象）非常類似的使用者資格。 如果您想要觸及更多對象（觸及率），您可以降低準確度。

### 步驟6：重新評估 [!UICONTROL Trait] 跨處理週期

定期， [!UICONTROL TraitWeight] 重新評估 [!UICONTROL trait] 根據的規模和母體變化 [!UICONTROL trait]. 當符合資格的使用者人數時，就會發生這種情況 [!UICONTROL trait] 會隨著時間增加或減少。 在變得非常大的特徵中，這種行為表現得最為明顯。 例如，假設演演算法使用 [!UICONTROL trait A] 用於模型化。 作為母體 [!UICONTROL trait A] 增加、 [!UICONTROL TraitWeight] 重新評估該專案的重要性 [!UICONTROL trait] 並且可以指派較低的分數或忽略該分數。 在這種情況下， [!UICONTROL trait A] 過於常見或過大，無法對其人口發表任何重要評論。 晚於 [!UICONTROL TraitWeight] 減少 [!UICONTROL trait A] （或在模型中忽略），演演算法特徵的母體會減少。 具影響力者清單 [!UICONTROL traits] 反映基線母體的演變。 使用具影響力者清單 [!UICONTROL traits] 以瞭解這些變更為何發生。

相關連結：

* [模型產生器](../../features/algorithmic-models/create-model.md)
* [精度和范围](../../features/traits/trait-accuracy-reach.md)

## 更新排程 [!UICONTROL Look-Alike Models] 和 [!UICONTROL Traits] {#update-schedule}

建立及更新新的或現有的排程 [!UICONTROL algorithmic models] 和 [!UICONTROL traits].

### [!UICONTROL Look-Alike Model] 建立和更新排程

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> 活动类型 </th>
   <th colname="col2" class="entry"> 描述 </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>建立或複製模型</b> </td>
   <td colname="col2"> <p>針對新的或複製的 [!UICONTROL Look-Alike Models]，建立程式會在以下位置每天執行一次： 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 東部時間下午5點（11月至3月） </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 東部夏令時間下午6點（3月至11月） </li> 
     </ul> </p> <p>在建立截止日期後建立或複製的模型會在隔天處理。 </p> <p>如果模型的第一次執行未產生任何資料，則會於次日執行第二次。 如果第二次嘗試也未產生任何資料，則會在隔天進行第三次嘗試。 如果第三次嘗試也未產生任何資料，則模型將停止執行。 在此情況下，我們將停用模型。 檢視更多資訊： <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> 疑難排解相似模型</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>更新模型</b> </td> 
   <td colname="col2"> <p>在理想的情況下，現有模型會在工作日執行，至少每7天執行一次。 例如，如果您在星期一建立模型（在截止日期前），則模型最晚會更新下個星期一。 </p> <p>如果模型符合下列任一條件，則會重新執行： </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">其上次執行不成功。 </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">它之前已順利執行，而且在過去7天內完全未執行，而且模型至少附加一個作用中特徵。 </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] 建立和更新排程

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 活动类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>建立特徵</b> </td> 
   <td colname="col2"> <p>特徵建立程式每天都會執行，星期一到星期五。 通常，新的演演算法特徵會在48小時內出現在UI中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>更新特徵</b> </td> 
   <td colname="col2"> <p>現有特徵至少每7天更新一次，並遵循模型更新排程。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模型清單檢視 {#models-list-view}

清單檢視是一個中央工作區，可協助您建立、檢閱和管理模型。

此 [!UICONTROL Models] 清單頁面包含可協助您：

* 建立新模型。
* 管理現有模型（編輯、暫停、刪除或複製）。
* 依名稱搜尋模型。
* 建立 [!UICONTROL algorithmic traits] 使用任何指定模型。

## 模型摘要檢視 {#models-summary-view}

摘要頁面會顯示模型詳細資訊，例如，名稱、觸及率/精確度、處理歷史記錄，以及 [!UICONTROL traits] 從模型建立。 此頁面也包含可讓您建立和管理模型的設定。 按一下摘要清單中的模型名稱以檢視其詳細資訊。

模型摘要頁面包含下列區段。

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 区域 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> 基本信息</span> </p> </td>
   <td colname="col2"> <p>包含模型的基本資訊，例如名稱和上次執行時間。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型觸及範圍和準確度</span> </p> </td> 
   <td colname="col2"> <p>顯示 <a href="../../features/traits/trait-accuracy-reach.md"> 精確度和觸及</a> 上次模型執行的資料。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型處理歷史記錄</span> </p> </td> 
   <td colname="col2"> <p>顯示最後10次執行的處理日期和時間，以及這些執行是否產生資料。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 具影響力的特徵</span> </p> </td> 
   <td colname="col2"> <p>此 <span class="wintitle"> 具影響力的特徵</span> 表格： </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 列出在模型的基線母體中表現最佳的前50個具影響力的特徵。 </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">依每個特徵排名的順序 <span class="wintitle"> 相對權數</span> 排名。 此 <span class="wintitle"> 相對權數</span> 依影響或可取性的順序排序新發現的特徵。 重量比例是從0%到100%的百分比。 特徵排名接近100%，表示它們更像是基線母體的受眾。 另請參閱 <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> 瞭解TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">顯示30天不重複值和每個特徵的總特徵人口。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 使用模型的特徵</span> </p> </td>
   <td colname="col2"> <p>根據選取的模型顯示演演算法特徵清單。 按一下特徵名稱或特徵ID，即可取得特徵的詳細資訊。 選取 <b><span class="uicontrol"> 使用模型建立新特徵</span></b> 前往演演算法特徵建立程式。 </p> <p>區段標籤會根據您的模型名稱而變更。 例如，假設您建立模型並將其命名為「模型A」。載入摘要頁面時，此區段的名稱會變更為 <span class="wintitle"> 使用模型A的特徵</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [目标](../../features/destinations/destinations.md)
>* [特征](../../features/traits/trait-details-page.md)
>* [区段](../../features/segments/segments-purpose.md)

