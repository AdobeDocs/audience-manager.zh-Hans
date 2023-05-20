---
description: 說明如何使用區段產生器建立區段。
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: 区段生成器
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 2%

---

# [!UICONTROL Segment Builder] {#segment-builder}

說明在中建立區段的必要和選用步驟 [!UICONTROL Segment Builder].

## 影片示範

從觀看 [在Audience Manager影片中建立區段](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). 影片會逐步帶您瞭解區段的建立流程。 如需詳細資訊，請閱讀以下章節。

## 创建一个 [!UICONTROL Segment] {#create-segment}

### 區段產生器區段

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 由3個不同的區段組成： [!UICONTROL Basic Information]， [!UICONTROL Traits]、和 [!UICONTROL Destinations Mapping]. 若要建立 [!UICONTROL segment]，填妥 [!UICONTROL Basic Information] 和 [!UICONTROL Traits] 區段。 [!UICONTROL Destinations Mapping] 設定是選用的。 如需其他說明，請參閱下列說明。

1. 在 [基本資訊](../../features/segments/segment-builder.md#segment-builder-controls-basics) 區段：

   ![create-segment](assets/create-segment.png)

   * 為命名 [!UICONTROL segment]. 最大長度 [!UICONTROL segment] 名稱是255個字元。
   * 設定 [!UICONTROL segment] 狀態（預設為「進行中」）。
   * 選擇 [!UICONTROL data source]. 使用第一個下拉式功能表，在Audience Manager之間篩選 [!UICONTROL data sources]和/或Adobe Analytics報表套裝。 然後，使用第二個下拉式功能表來選擇 [!UICONTROL data source]. 如果您沒有使用Adobe Analytics報表套裝， [!UICONTROL data source] 型別選擇器已停用，且僅預設為Audience Manager資料來源。
   * 選取 [!UICONTROL profile merge rule] 使用於 [!UICONTROL segment] 資格。
   * 指派 [!UICONTROL segment] 至儲存資料夾。

1. 在 [特徵](../../features/segments/segment-builder.md#segment-builder-controls-traits) 區段：
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * 搜尋 [!UICONTROL trait] 您想要新增至區段，然後按一下 **[!UICONTROL Add Trait]**. 新增另一個 [!UICONTROL trait] 建立 [!UICONTROL trait] 群組。
   * 開啟 [!UICONTROL Advanced Search] 按一下以強制回應視窗 **[!UICONTROL Browse All Traits]**. 搜尋 [!UICONTROL traits] 依名稱、ID、說明或 [!UICONTROL data source]. 搜尋時按一下資料夾，將結果限制在該資料夾及其子資料夾內。 您也可以篩選 [!UICONTROL traits] 作者： [!UICONTROL trait type] ([!UICONTROL Folder Trait]， [!UICONTROL Rule-based]， [!UICONTROL Onboarded]、和 [!UICONTROL Algorithmic])或母體型別([裝置ID](../../reference/ids-in-aam.md) 和 [跨裝置ID](../../reference/ids-in-aam.md))。
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * 上線 [特徵建議](trait-recommendations.md) 當您建置 [!UICONTROL segment].
   * 按一下並拖曳 [!UICONTROL traits] 以建立不同的群組。
   * 在群組之間暫留，以使用布林值設定關係 [!UICONTROL AND]， [!UICONTROL OR]， [!UICONTROL AND NOT] 值。
   * 將游標停留在時鐘圖示上以新增 [造訪間隔和頻率](../../features/segments/recency-and-frequency.md) 的規則 [!UICONTROL trait].
   * 新增或移除時檢視區段母體資料 [!UICONTROL traits]. 按一下 **[!UICONTROL Calculate Estimates]** 以檢視（或重新整理）預估母體數目。 深入瞭解 [區段母體資料](../../features/segments/segment-builder-data.md#segment-populations) 在 [!UICONTROL Segment Builder].
   * 按一下 **[!UICONTROL Save]** 完成時。

1. *（可選）* 對應 [!UICONTROL segment] 至 [!UICONTROL destination] 在 [目的地對應](../../features/segments/segment-builder.md#segment-builder-controls-destinations) 區段：
   * 搜尋 [!UICONTROL destination] 並按一下 **[!UICONTROL Add Destination]**. 請注意， [!UICONTROL destination] 必須先存在，您才能將其新增至 [!UICONTROL segment].
   * 按一下 **[!UICONTROL Save]** 完成時。

請觀看以下影片，詳細瞭解跨裝置量度的運作方式。

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] 控制項： [!UICONTROL Basic Information] 章節 {#segment-builder-controls-basics}

在 [!UICONTROL Segment Builder]， [!UICONTROL the Basic Information] 設定可讓您建立新特徵或編輯現有特徵。 若要建立新的 [!UICONTROL segment]，提供名稱、 [!UICONTROL data source]，然後選取儲存資料夾。 所有其他欄位都是選用欄位。 移至 [!UICONTROL Traits] 區段。

<!-- r_segment_basic_info_section.xml -->

<!--

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Name</b> </td> 
   <td colname="col2"> <p>Give the segment a short, logical name that describes its function or purpose. Avoid abbreviations and special characters. The maximum length of a segment name is 255 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>A field for additional descriptive information about the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integration Code</b> </td> 
   <td colname="col2"> <p>A field for a user-defined ID or other company-specific information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <p>Associates the segment with a specific data provider. <p>Use the first drop-down menu to filter between Audience Manager data sources, Adobe Analytics report suites, or both. Then, use the second drop-down menu to choose your data source.</p><p> If you are not using Adobe Analytics report suites, the data source type selector is disabled and defaulted to Audience Manager data sources only.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Profile Merge Rule</b> </td> 
   <td colname="col2"> <p>Selects the Profile Merge Rule to use for segment qualification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Activates or deactivates the segment (active by default). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Folder Storage</b> </td> 
   <td colname="col2"> <p>Determines which storage folder the segment belongs to. </p> </td> 
  </tr> 
 </tbody> 
</table>

-->

| 字段 | 描述 |
---------|----------
| **[!UICONTROL Name]** | 為區段提供一個簡短的邏輯名稱，說明其功能或用途。 避免使用縮寫和特殊字元。 區段名稱的最大長度為255個字元。 |
| **[!UICONTROL Description]** | 有關區段的其他描述性資訊的欄位。 |
| **[!UICONTROL Integration Code]** | 使用者定義的ID或其他公司特定資訊的欄位。 |
| **[!UICONTROL Data Source]** | 將區段與特定資料提供者建立關聯。 <br> 使用第一個下拉式選單，在Audience Manager資料來源、Adobe Analytics報表套裝或兩者之間篩選。 然後，使用第二個下拉式選單來選擇資料來源。 <br> 如果您未使用Adobe Analytics報表套裝，資料來源型別選擇器會停用，並預設為僅Audience Manager資料來源。 |
| **[!UICONTROL Profile Merge Rule]** | 選取要用於區段資格的設定檔合併規則。 |
| **[!UICONTROL Status]** | 啟動或停用區段（預設為啟動）。 |
| **資料夾儲存空間** | 決定區段所屬的儲存資料夾。 |

## [!UICONTROL Segment Builder] 控制項： [!UICONTROL Traits] 章節 {#segment-builder-controls-traits}

在 [!UICONTROL Segment Builder]，則 [!UICONTROL Traits] 區段可讓您管理 [!UICONTROL traits] 在 [!UICONTROL segment]，建立 [!UICONTROL trait] 群組，並設定資格條件。 若要新增 [!UICONTROL trait] 至 [!UICONTROL segment]，輸入 [!UICONTROL trait] 名稱，然後按一下 [!UICONTROL Add Trait]. 儲存 [!UICONTROL trait] （若已完成）或繼續前往 [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**先決條件：** 填妥以下欄位中的必填欄位： [!UICONTROL Basic Information] 區段。

| 字段 | 描述 |
|--- |--- |
| **[!UICONTROL Basic View]** | 本節提供視覺控制項，可讓您： <ul><li>建置新專案及管理現有專案 [!UICONTROL segments].</li><li>移除 [!UICONTROL traits] 從 [!UICONTROL segment].</li><li>最多新增50個（最大值） [!UICONTROL traits] 至 [!UICONTROL segment].</li><li>拖放 [!UICONTROL traits] 以建立新群組。</li><li>檢視 [!UICONTROL traits] 和 [!UICONTROL trait] 群組 [!UICONTROL segment].</li><li>使用布林運算式、比較運運算元和時近/頻率設定來設定資格條件。</li></ul> |
| **[!UICONTROL Code View]** | 開啟開發環境，讓您建立和管理 [!UICONTROL traits]、群組和資格要求，改用程式碼而非視覺化介面。 程式碼檢視在以下情況下相當實用： [!UICONTROL segments]： <ul><li>包含超過50個 [!UICONTROL traits] 在個人中 [!UICONTROL segment]. 注意： [!UICONTROL Segments] 限製為5000個 [!UICONTROL traits] （最大值）。</li><li>包含多個 [!UICONTROL trait] 群組。</li><li>具有複雜的資格需求。</li></ul> |
| 搜索 | 協助您尋找 [!UICONTROL traits] 新增至 [!UICONTROL segment]. |
| 推荐 | 取得類似專案的即時建議 [!UICONTROL traits]，來自您的第一方 [!UICONTROL traits] 和 [!UICONTROL Audience Marketplace] 您所訂閱的資料摘要。 將這些建議新增至 [!UICONTROL segment] 規則來擴展您的對象。 詳細內容： [特徵Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | 取得類似專案的即時建議 [!UICONTROL traits]，從 [!UICONTROL Audience Marketplace] 您尚未訂閱的資料摘要。 詳細內容： [特徵Recommendations](trait-recommendations.md). |
| 實際與預估 [!UICONTROL Segment] 大小資料 | 请参阅[区段生成器中的特征和区段人口数据](segment-builder-data.md)。 |

## 移除 [!UICONTROL Traits] 從 [!UICONTROL Segment] {#remove-traits}

管理 [!UICONTROL traits] 在您的 [!UICONTROL segments] 是儲存的重要部分 [!UICONTROL segments] 可行。 如果您需要移除，請依照下列步驟操作 [!UICONTROL traits] 從 [!UICONTROL segment].

移除 [!UICONTROL traits] 從 [!UICONTROL segment]：

1. 前往 **[!UICONTROL Audience Data > Segments]**. 捲動清單或使用搜尋功能尋找 [!UICONTROL segment] 您想要搭配使用。
2. 按一下 [!UICONTROL segment] 名稱以開啟 [!UICONTROL segment] 詳細資訊畫面。
3. 按一下 **編輯** 以開啟 [!UICONTROL Segment Builder] 然後按一下 **特徵** 以開啟 [!UICONTROL traits] 面板。
4. 將游標暫留在 [!UICONTROL trait] 您要刪除，然後按一下X。此動作會立即移除 [!UICONTROL trait] 從您的 [!UICONTROL segment].

## [!UICONTROL Segment Builder] 控制項： [!UICONTROL Destinations Mappings] 章節 {#segment-builder-controls-destinations}

在 [!UICONTROL Segment Builder]，選填 [!UICONTROL Destinations Mapping] 區段可讓您傳送 [!UICONTROL segment] 資料給協力廠商 [!DNL cookie]， [!DNL URL]，或 [!UICONTROL server-to-server destination]. 若要新增 [!UICONTROL destination]，搜尋（或瀏覽） [!UICONTROL destination]，提供 [!UICONTROL destination] 特定資訊，然後按一下 **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### 先决条件

填妥以下欄位中的必填欄位： [!UICONTROL Basic Information] 和 [!UICONTROL Traits] 區段。 此外，目的地必須已存在。

### [!UICONTROL Destination Mappings] 搜尋工具

此 **[!UICONTROL Destination Mappings]** 面板包含搜尋工具，如下表所述。

| 搜索类型 | 描述 |
|---|---|
| **[!UICONTROL Search by Destination Name]** | 可讓您搜尋特定 [!UICONTROL destination] 依名稱。 若要搜尋，請開始輸入。 欄位將根據您的搜尋字詞自動完成。 按一下 **[!UICONTROL Add Destination]** 完成時。 |
| **[!UICONTROL Browse All Destinations]** | 瀏覽清單 *全部* [!UICONTROL destinations] 可供您使用。 選取並新增 [!UICONTROL destinations] 至您的 [!UICONTROL segment] 從快顯清單。 |

## 中的欄位 [!UICONTROL Destination Mappings] 快顯視窗 {#fields-in-dest-mappings}

在 [!UICONTROL Segment Builder]，則 [!UICONTROL Add Destination] 對話方塊會在您選取 [!UICONTROL destination]. 此視窗顯示有關下列專案的靜態資訊 [!UICONTROL destination] 和欄位視 [!UICONTROL destination] 型別。 在空白欄位中提供必要資訊，以設定 [!UICONTROL destination mapping].

>[!NOTE]
>
>發佈日期為選用。 當空白時，目的地會變成使用中且永不過期。

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] 字段

在 [!UICONTROL Destination Mapping] 欄位中，指定用來將資料傳送至 [!UICONTROL destination]. 在第一個欄位中輸入索引鍵，並在第二個欄位中輸入值。 您的 [!UICONTROL cookie destination] pop看起來可能類似這樣：

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] 字段

在 [!UICONTROL URL] 和 [!UICONTROL Secure URL] 欄位，指定用來傳送資料給的完整標準或安全位址 [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] 字段

在 [!UICONTROL Destination Value] 欄位指定用來將資料傳送至的值（機碼 — 值組的一部分） [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [建立Cookie目的地](../../features/destinations/create-cookie-destination.md)
>* [建立URL目的地](../../features/destinations/create-url-destination.md)

