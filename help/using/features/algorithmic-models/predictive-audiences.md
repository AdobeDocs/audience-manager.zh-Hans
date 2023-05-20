---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Overview
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1485'
ht-degree: 7%

---

# [!UICONTROL Predictive Audiences] 概述 {#predictive-audiences}

[!UICONTROL Predictive Audiences] 可協助您使用進階資料科學技術，即時將未知的受眾分類為不重複角色。

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 本文不包含任何法律建議。 請諮詢您自己的法律顧問，以獲得法律指引。

在营销环境中，角色是指由具有一系列相同特征（例如人口统计特征、浏览习惯、购物历史记录等）的访客、用户或潜在购买者构成的一个受众区段。

[!UICONTROL Predictive Audiences] 模型进一步扩展了角色这一概念的应用，允许您使用 Audience Manager 的机器学习功能将未知受众分类为不同的角色。Audience Manager 可以计算未知的第一方受众与一组已知的第一方受众之间的相似性，从而帮助您做到这一点。

當您建立 [!UICONTROL Predictive Audiences] 模型，第一步是選擇基線特徵或區段，讓您的目標受眾依這些特徵或區段進行分類。 這些特徵或區段將定義您的角色。

在評估階段，模型會建立新的 [!UICONTROL Predictive Audiences] 定義為基準線的每個特徵或區段的區段。 下次Audience Manager看到目標受眾中未被分類為角色訪客（不符合任何基線特徵或區段的資格）時， [!UICONTROL Predictive Audiences] 模型會判斷訪客應屬於哪些預測區段，並將訪客新增至該區段。

您可以在下列位置識別模型建立的預測區段： [!UICONTROL Segments] 頁面。 每個 [!UICONTROL Predictive Audiences] 模型在 [!UICONTROL Predictive Audiences] 資料夾，按一下模型資料夾即可看到每個模型的區段。

![預測受眾 — 區段](assets/predictive-audiences-segments.png)

## 用例 {#use-cases}

協助您更清楚瞭解您何時可以如何使用 [!UICONTROL Predictive Audiences]，以下是Audience Manager客戶可以使用此功能解決的一些使用案例。

### 使用案例#1

身為電子商務公司的行銷人員，我想將所有網頁和行動訪客分類為各種品牌相關性類別，以便個人化其使用者體驗。

### 使用案例#2

身為一家媒體公司的行銷人員，我想要依我最愛的流派將我未經驗證的網頁和行動訪客分類，以便我可以跨所有管道為他們建議個人化內容。

### 使用案例#3

作為一家航空公司的廣告商，我想要確保我根據受眾對旅遊目的地的興趣來分類受眾，這樣我就能在短短的重新定位時段內即時向他們做廣告。

### 使用案例#4

作為廣告商，我想即時分類第一方對象，以便對趨勢新聞做出快速反應。

### 使用案例#5

作為行銷人員，我想預測我的網站訪客處於哪個客戶歷程階段，例如探索、參與、購買或保留，以便我可以據此鎖定他們。

### 使用案例#6

身為一家媒體公司，我想將對象分類，以便以高價銷售廣告空間，同時為訪客提供相關的廣告。

## 如何 [!UICONTROL Predictive Audiences] 模型有效 {#how-predictive-audiences-models-work}

當您建立 [!UICONTROL Predictive Audiences] 模型，請進行三個步驟：

1. 首先，您至少選取兩個特徵或兩個區段，以定義您的角色。
1. 然後，您可以選擇特徵或區段，定義您要分類的目標對象。
1. 最後，您需選擇模型的名稱、儲存預測區段的資料來源，以及 [!UICONTROL Profile Merge Rule] 用於模型。

### 角色選擇條件 {#selection-personas}

您可以選擇任何第一方特徵或區段來定義您的角色。 不過，為獲得最佳結果，以下是建議的一組最佳實務：

* 選擇您的角色特徵或區段，讓每個角色至少擁有幾百個 [裝置ID](../../reference/ids-in-aam.md).
* 如果您的特徵是根據 [跨裝置ID](../../reference/ids-in-aam.md)，您可使用將它們包在區段中 [設定檔合併規則](../profile-merge-rules/merge-rules-overview.md) 使用 [裝置ID](../../reference/ids-in-aam.md)，例如 [!UICONTROL Device Graph]. 這將確保有足夠的資源 [裝置ID](../../reference/ids-in-aam.md) 演演算法可從中學到的東西。
* 我們建議您為角色選擇特徵或簡單區段，包含1到3個特徵。
* 選擇重疊程度最低的基線特徵或區段。
* 請務必在數位資產中擷取精細特徵。

### 目標對象的選擇條件 {#selection-audience}

根據您的使用案例，無論您是要即時分類、批次分類還是同時分類，請選擇目標對象([!UICONTROL trait] 或 [!UICONTROL segment])，具有顯著的即時和/或總母體。 與角色選擇類似，我們建議您鎖定目標對象 [!UICONTROL trait] 或 [!UICONTROL segment] 擁有擁有豐富設定檔的使用者(豐富設定檔 [!UICONTROL traits])。

選取目標對象時，請分析您的使用案例，並決定您要分類的ID型別： [!UICONTROL device IDs] 或 [!UICONTROL cross-device IDs]. 此 [!UICONTROL Profile Merge Rule] 建立模型時選取的欄位會定義用來將每個使用者置於預測性中的資料 [!UICONTROL segments].

建議您最好選擇 [!UICONTROL Profile Merge Rule] 與您的目標對象具有相同設定的對象 [!UICONTROL Profile Merge Rule]或包含目標對象之設定檔型別（裝置設定檔或已驗證的設定檔）的設定檔。

### [!UICONTROL Predictive Audiences] 模型訓練階段 {#model-training}

演演算法必須先根據您的資料進行自我訓練，才能將第一方對象分類為正確的角色。

對於您定義的每個角色，演演算法都會分析其個別對象，並評估其使用者在過去30天內任何即時和/或已上線特徵活動。
此步驟每24小時執行一次，以說明第一方對象中的變更。

### [!UICONTROL Predictive Audiences] 模型分類階段 {#model-classification}

對於即時和批次對象分類，模型會先檢查使用者是否屬於目標對象。 如果使用者符合目標受眾的資格且不屬於任何角色，則模型會為他們指派角色資格分數。

評估第一方對象並指派分數時，模型會使用預設值 **[!UICONTROL Profile Merge Rule]** 已在您的帳戶中定義。 最後，訪客會分類為獲得最高分數的角色。

![預測受眾 — 圖表](assets/predictive-audiences-graph.png)

## 考量事項和限制 {#considerations}

>[!IMPORTANT]
> 在繼續實作階段之前，請仔細閱讀本節。

設定您的 [!UICONTROL Predictive Audiences] 模型，請謹記以下考量事項和限制：

* 您最多可以创建 10 个 [!UICONTROL Predictive Audiences] 模型。
* 對於每個模型，您最多可以選擇50個基本特徵/區段。
* 目前不支援第二方和第三方資料 [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] 會根據您的第一方特徵，從您的所有第一方資料來源執行對象分類。
* 區段評估 [!UICONTROL Predictive Audiences] 使用 **[!UICONTROL Profile Merge Rule]** 您在建立模型時選擇的引數。 若要深入瞭解 [!UICONTROL Profile Merge Rules] 請參閱專屬的 [檔案](../profile-merge-rules/merge-rules-overview.md).
* 部分特徵和區段不支援作為基線或目標對象。 [!UICONTROL Predictive Audiences] 選擇下列其中一個作為基線或目標對象時，模型將無法儲存：
   * 預測性特徵和使用預測性特徵建立的區段；
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) 特徵或區段；
   * 演演算法特徵；
   * 第二方和第三方特徵。
* [!UICONTROL Predictive Audience] [!UICONTROL segments] 不能用於 [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

預測性區段建立者 [!UICONTROL Predictive Audiences] 模型繼承 [資料匯出控制](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) 資料來源：

1. 您在建立模型時選擇的第一方資料來源。
1. 目標對象的第一方資料來源。 具體而言，下列專案的資料匯出控制項： [!UICONTROL traits] 或 [!UICONTROL segments] 組成目標對象的資訊。
1. 此 [資料匯出控制](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) 的 [!UICONTROL Profile Merge Rule] 您為模型選取的。

新建立的預測性 [!UICONTROL traits] 和 [!UICONTROL segments] 會具有與上述第一方資料來源聯合相同的隱私許可權制。

具有其他限制，但不屬於下列條件的特徵： [!UICONTROL Predictive Audiences] 區段隱私許可權制將從培訓階段排除，且不會對該模型產生影響。

## [!UICONTROL Profile Merge Rules] {#pmr}

所有預測性區段將會被指派 [!UICONTROL Profile Merge Rule] 您在建立模型時選取的專案。 此 [!UICONTROL Profile Merge Rule] 您選擇的專案之所以重要，原因如下：

* 它定義當模型分析具影響力時，應將哪些裝置和/或已驗證的設定檔列入考量 [!UICONTROL traits]，將使用者分類至預測性變數時 [!UICONTROL segment].
* 它控管哪些 [!UICONTROL trait] 型別（裝置層級或跨裝置層級）應在模型訓練步驟中使用，並顯示為具有影響力 [!UICONTROL traits]. 預測性 [!UICONTROL segments] 是目標對象的子集。
   * 如果目標對象是區段，建議您選取相同的 [!UICONTROL Profile Merge Rule] ，作為指派給目標對象的模型，或 [!UICONTROL Profile Merge Rule] 其中包含目標對象的設定檔型別。
   * 如果目標對象是 [!UICONTROL trait]，建議您選取 [!UICONTROL Profile Merge Rule] 可存取與目標受眾特徵相同資料型別的使用者（裝置設定檔資料或跨裝置設定檔資料）。
* [!UICONTROL Profile Merge Rules] 使用 [!UICONTROL Current Authenticated Profiles] 和 [!UICONTROL No Device Profile] 選項僅支援即時對象分類。 如需詳細資訊，請參閱 [定義的設定檔合併規則選項](../profile-merge-rules/merge-rule-definitions.md).

選取 [!UICONTROL Profile Merge Rule] 同時使用裝置資料和跨裝置資料的 [!UICONTROL traits] 可用於模型訓練和使用者分類來預測性 [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

您為角色和受眾分類選擇的特徵和區段會受到Audience Manager限制 [角色型存取控制](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html).

Audience Manager使用者只能選取其擁有之角色和目標對象的特徵或區段 [檢視許可權](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
