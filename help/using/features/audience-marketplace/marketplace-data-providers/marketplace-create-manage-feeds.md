---
description: 資料摘要需要名稱、說明、資料來源及計畫型別。 在您儲存並啟動摘要之前，摘要都會停用。 在「Audience Marketplace>我的共用資料」中設定公開或私人資料摘要。 僅供資料賣家使用。
seo-description: A data feed requires a name, description, data source, and a plan type. Feeds are disabled until you save and activate the feed. Set up public or private data feeds in Audience Marketplace > My Shared Data. Available to data sellers only.
seo-title: Create, Price, and Manage Data Feeds
solution: Audience Manager
title: 创建、定价和管理数据信息源
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1257'
ht-degree: 2%

---

# 创建、定价和管理数据信息源 {#create-price-and-manage-data-feeds}

## 建立公開或私人資料摘要 {#create-public-private-data-feed}

資料摘要需要名稱、說明、資料來源及計畫型別。 在您儲存並啟動摘要之前，摘要都會停用。 在中設定公開或私人資料摘要 **[!UICONTROL Audience Marketplace > My Shared Data]**. 僅供資料賣家使用。

<!-- t_data_feed.xml -->

您必須擁有管理員許可權，才能建立公開或私人資料摘要。
若要建立資料摘要：

1. 单击 **[!UICONTROL New Data Feed]**.
1. 為資料摘要命名。 資料購買者可以根據名稱搜尋您的摘要。
1. 提供簡短說明（最多255個字元）。

   清楚的描述應該能準確描述您的摘要。 例如，您可以包含行銷類別、人口統計和地理涵蓋範圍的文字(例如 [!DNL US] 或北美洲)。 說明文字可供搜尋，可協助買家尋找或評估您的摘要。 良好的說明是吸引訂閱者使用資料摘要的重要環節。
1. 從中選擇資料來源 **[!UICONTROL Data Source]** 選項。 資料摘要僅限於單一資料來源。 您無法將多個資料來源指派給相同的資料摘要。

   >[!IMPORTANT]
   >
   >屬於此資料來源的任何目前和未來特徵都將作為此摘要的一部分，與您的資料購買者共用。

1. 在 [!UICONTROL Plan Types]，選取您要使用的選項，然後按一下 **[!UICONTROL Add Plan]**.

   摘要可包含多個計畫。 計畫可包含多個使用案例。 如需詳細資訊，請參閱 [資料摘要的計畫型別](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. 按一下 **[!UICONTROL Save]** 以儲存您的資料摘要 *不含* 啟用它。
1. 若要儲存及啟用資料摘要：
   1. 移動 **[!UICONTROL Availability]** 滑桿至 **[!UICONTROL Active]**.
   1. 单击 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* 無法刪除已儲存和已啟動的資料摘要。
   >* 購買者只會看到作用中的摘要。


### 可選：建立私人資料摘要

在 [!UICONTROL Settings] 區段，將滑桿移動到：

* **[!UICONTROL Private]** 和 **[!UICONTROL Branded]**：購買者的 [!UICONTROL Marketplace] 清單會在「提供者」欄中顯示賣家名稱，而所有其他資料則會隱藏。

* **[!UICONTROL Private]** 和 **[!UICONTROL Unbranded]**：購買者的 [!UICONTROL Marketplace] 清單僅顯示資料摘要名稱和說明。 資料提供者名稱顯示為 [!UICONTROL Private Seller].

若要檢視私人摘要對買家而言的外觀，請參閱以下的「買家」區段： [私人資料摘要](../../../features/audience-marketplace/marketplace-private-feeds.md).

## 停用订阅者的数据馈送 {#deactivate-data-feed}

作為 [!UICONTROL Audience Marketplace] 資料提供者，您可以撤銷購買者對訂閱資料摘要的存取權。 您可能因為延遲付款/未支付費用或如果買家不當使用特徵資料，而想要從摘要中移除買家。

<!-- marketplace-deactiva4te-subscribers.xml -->

撤銷訂閱者：

1. 在 [!UICONTROL My Shared Data]，尋找訂閱者正在使用的摘要。

   >[!NOTE]
   >
   >逾期帳戶的資料摘要會以三角形/驚歎號圖示標示。

1. 在 [!UICONTROL Subscribers] 欄中，按一下計算該摘要之訂閱者的藍色數字。 如此將可開啟訂閱詳細資訊頁面。
1. 移動 **[!UICONTROL Subscription]** 滑桿至 **[!UICONTROL Off]**. 這會開啟確認對話方塊視窗。
1. 在 [!UICONTROL Confirmation] pop，按一下 **[!UICONTROL Yes]** 若要停用訂閱或 **[!UICONTROL Cancel]** 結束而不變更訂閱。

### 停用訂閱者後會發生什麼事

撤銷資料摘要的存取權會傳送通知電子郵件給資料購買者帳戶中的所有管理員使用者。 電子郵件包含列出撤銷特徵的附件。 此清單可協助訂閱者尋找及移除其區段和模型中的已停用特徵。

### 帳單和摘要停用

在您移除資料摘要的存取權後，訂閱者需根據您停用摘要的時間，負責上月或當月的費用。

## 資料摘要的計畫型別 {#plan-types}

[!DNL Plan types] 是中的重要元件 [!UICONTROL Audience Marketplace] 資料摘要。 身為資料提供者，他們可讓您為摘要建立多個使用案例和價格選項。 此外，為每個資料摘要建立一些計畫也是不錯的策略。 當買家尋找要建立模型或傳送至目的地的資料時，這可為其提供不同的選項供他們選擇。

[建立資料摘要](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) 以選取 [!UICONTROL Plan Types].

![](assets/plan_types.png)

## 計畫型別和使用案例選項 {#plan-types-use-cases}

<!-- c_feed_options.xml -->

此 [!UICONTROL Use Case] 設定可讓賣家控制買家如何使用您的資料。

### 區段和重疊

A **[!UICONTROL Segments and Overlap]** 使用案例會建立計畫，讓買家比較 [特徵對特徵重疊報表](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). 此外，購買者可以將您的資料新增至區段，並與 [區段對特徵](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) 和 [區段對區段](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) 報表。

每個資料摘要必須至少包含一個 [!UICONTROL Segments and Overlap] 使用案例。 如果摘要未包含，購買者無法訂閱資料摘要中的其他計畫。 [!UICONTROL Segments and Overlap] 使用案例，其本身或與其他使用案例結合使用。

重疊比較可協助買家：

* **擴大受眾範圍：** 低重疊表示您的特徵包含購買者之前未曾見過的使用者。 因此，購買者可能希望這些特徵可將新使用者新增至其受眾區段。
* **增強現有對象：** 高度重疊表示您的特徵包含的使用者與購買者已知的使用者類似。 因此，購買者可能希望這些特徵有助於針對已開發受眾進行有針對性的漸進式改善。

依照下列方式為此使用案例定價：

* 單位：固定費用
* 價格：免費($0.00)

### 模型

A **[!UICONTROL Modeling]** 使用案例可建立計畫，讓買家比較您與他們的特徵 [演演算法建模](../../../features/algorithmic-models/understanding-models.md#understanding-models). 買家會檢視模型結果，在您的資料中尋找與其擁有類似轉換屬性的新受眾。 依照下列方式為此使用案例定價：

* 單位：固定費用
* 價格：折扣或市價價格

### 激活

一個 **[!UICONTROL Activation]** 使用案例可讓買家將資料傳送至 [目的地](../../../features/destinations/destinations.md). 透過此使用案例，買家無法比較資料與重疊報表或演演算法模型中的資料。 依照下列方式為此使用案例定價：

* 單位： [!DNL CPM]
* 價格： [!DNL CPM] 市價

## 帳單與價格選項 {#billing}

帳單和價格選項可控制購買者如何為您的資料付款。

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选项 </th> 
   <th colname="col2" class="entry"> 描述 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 計費週期</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 每月缺款</span></b> 是唯一選項。 計費週期於每月第10日結束。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 測量單位</span></b> </td> 
   <td colname="col2">以CPM費率或固定費用向資料購買者收費。 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> 若使用CPM定價，資料購買者必須自行報告使用量。 </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">若使用固定費用定價，資料購買者不會報告使用量，因為他們是以固定費率收費。 </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 价格</span></b> </td>
   <td colname="col2"> 賣家以CPM費率或統一費用價格向買家收取的金額（以美元計）。 </td>
  </tr> 
 </tbody> 
</table>

## 計畫備註 {#plan-notes}

在 **[!UICONTROL Additional Notes]** 欄位，請花一些時間說明摘要中的每個資料計畫。 良好的簡短說明可協助購買者瞭解資料摘要中每個計畫的內容或目的。 買家在搜尋或評估新資料來源時，可以閱讀資料摘要和計畫說明。

## 管理私人資料摘要請求 {#manage-private-requests}

管理買家私人摘要請求的提供者工作流程。

若要複查、核准或拒絕採購員請求，請移至 [!UICONTROL My Shared Data] 和：

<!-- t_private_feed_workflows.xml -->

1. 按一下私人資料摘要的名稱。
2. 按一下 **[!UICONTROL Access Requests]** 以檢閱所有想要存取您資料摘要的買家。
3. 在 [!UICONTROL Allow Access] 區段內，按一下核取標籤以核准要求，或按一下X以拒絕存取。
4. 在確認快顯視窗中確認或取消選取的動作。

## 資料提供者的折扣 {#discounts}

在 [!UICONTROL Audience Marketplace]，折扣可讓您為個別訂閱者降低資料摘要的發佈價格。 您可以為已提交訂閱請求的訂閱者或請求資料摘要詳細資訊的訂閱者提供折扣。 折扣適用於 [!DNL CPM] 和平均速率饋送。 如果您想要為新客戶提供訂閱獎勵或獎勵客戶忠誠度，折扣可能會很有幫助。

## 將折扣套用至資料摘要 {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

若要折扣摘要，請將折扣金額以%的形式新增至折扣欄位，並確認您的變更。 資料提供者可對以下專案的資料摘要提供折扣： [!UICONTROL Audience Marketplace] 從：

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

在這些範例中，賣家已將10%的折扣新增至 [!UICONTROL Software Audience] 資料摘要。

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## 檢閱折扣摘要 {#review-discounted-feeds}

資料提供者可以在以下位置檢視其所有訂閱者和折扣摘要： **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [专用数据信息源](../../../features/audience-marketplace/marketplace-private-feeds.md)

