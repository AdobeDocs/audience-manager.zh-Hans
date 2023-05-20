---
description: 定址對象功能與使用案例的概觀。
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: 可寻址受众
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1813'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

功能和用例概述 [!UICONTROL Addressable Audience] 。

## 什么是 [!UICONTROL Addressable Audience]? {#addressable-audience-description}

此 [!UICONTROL Addressable Audiences] 功能會顯示您所看到的所有屬性對象之間的重疊，其中 [!DNL Audience Manager] 收集資料和您選取的目的地。 為協助您瞭解此概念，請參閱下圖。 每個圓圈之間的重疊代表不同型別的可定址對象。

![](assets/addressableAudienceVenn.png)


| 量度 | 描述 |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] 對於 [!UICONTROL Destination] | 與所有裝置互動的所有裝置計數 [!DNL Audience Manager] 在報表回顧期間處於平台層級的客戶，且可與您選取的相符 [!UICONTROL destination]. <br><br>此量度非常有用，因為它會顯示以下內容： <ul><li>總計大小 [!UICONTROL addressable audience] 該 [!DNL Audience Manager] 可以觸及特定目標 [!UICONTROL destination].</li><li>有多大 [!DNL Audience Manager] 設定檔集區適用於目標平台及其對象的大小。</li></ul> |
| [!UICONTROL Customer Total Audience] | 已實現a的裝置計數 [!UICONTROL rule-based trait] 在您的屬性上或 [!UICONTROL onboarded trait] 在回顧期間從離線檔案中移除。 |
| [!UICONTROL Customer Addressable Audience] | 在 &quot;查看&quot; 窗口中已实现 [!UICONTROL rule-based trait] 或出现 [!UICONTROL onboarded trait] 的设备的重叠次数，设备，无论同步时间如何，您都可以选择 [!UICONTROL destination] ID 同步。<br><br>此量度表示设备：<ul><li>已在 &quot;查看&quot; 窗口中意识到 [!UICONTROL rule-based] [!UICONTROL onboarded trait]`AND`</li><li>具有所选 [!UICONTROL destination] ID 的同步，而不管同步时间。</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] 以百分比表示的÷ [!UICONTROL Customer Total Audience] 。 |
| [!UICONTROL Total Segment Population] | 屬於您的成員的所有裝置計數 [!UICONTROL segment] 在報表回顧期間。 |
| [!UICONTROL Segment Addressable Audience] | 屬於以下專案的使用者人數： [!UICONTROL segment] 在報表回顧期間執行，並在您的網站上進行作用中ID同步。 [!UICONTROL Segments] 可以包含您自己的第一方資料，以及第二方和第三方資料，透過 [!UICONTROL traits] 取得於 [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>提示：搭配1天回顧期間使用時，此量度可協助您瞭解您目前的狀態 [!UICONTROL segments]. 這是因為 [!UICONTROL Segment Addressable Audience] 量度代表保留在中的使用者 [!UICONTROL segment] 整個前一天。 結合以下事實 [!DNL Audience Manager] 重新整理 [!UICONTROL Addressable Audiences] 每日，結合此量度和回顧期間，可提供您的最新快照 [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 以百分比表示。 |

## [!UICONTROL Addressable Audiences] 界面 {#addressable-audience-interface}

此 [!UICONTROL Addressable Audience] 功能可將此抽象概念轉換為可量化的資料。 在 [!DNL Audience Manager]，這項功能會顯示與資料視覺效果重疊的受眾，這些視覺效果會提供一目瞭然的資訊，並以表格形式呈現數值資料。

[!UICONTROL Addressable Audiences] 位於 **[!UICONTROL Audience Data > Destinations]**. 選取 **[!UICONTROL Integrated Platforms > Device-Based]** 若要檢視可定址對象量度。

![](assets/addressable-audiences-landing.png)

您可在上看到的三個量度 [!UICONTROL Addressable Audiences] 登陸頁面代表：

| 量度 | 描述 |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | 此量度代表 [!UICONTROL Customer Addressable Audience] （如上表所述） *過去30天。* |
| **[!UICONTROL Match Rate]** | 此量度代表 [!UICONTROL Addressable Audience Match Rate] （如上表所述） *過去30天*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | 與所有裝置互動的所有裝置計數 [!DNL Audience Manager] 在報表回顧期間處於平台層級的客戶，且符合以下條件： [!UICONTROL destination]. 另請參閱 [平台層級量度](/help/using/features/addressable-audiences.md#platform-level-metrics) 以取得詳細資訊。 |

按一下的名稱 [!UICONTROL server-to-server destination] 以檢視可定址對象資料。 請注意，此功能會傳回以下專案的資料： [!UICONTROL server-to-server destinations] 只有和存取需要管理員許可權。

![](assets/addressableAudiences.png)

檢閱此資料可協助您：

* **預測與計畫：** [!UICONTROL Segment Addressable Audience] 資料可讓您對您計畫傳送至目的地以進行對象定位和啟用的區段進行更精細的劃分。

* **績效檢閱：** 此 [!UICONTROL Addressable Audiences] 特徵也是疑難排解工具。 它可讓您檢閱行銷活動績效、瞭解行銷活動觸及率，以及讓您在沒有看到預期結果時與鎖定目標/啟用合作夥伴進行交叉檢查。

### 使用協力廠商資料進行勘探，以及對匹配率的影響

在購買第三方資料以取得對象之前，客戶可以驗證與其他資料提供者的重疊。 這可協助您在購買新資料之前做出明智的決定。 所購買協力廠商資料的ID同步不僅仰賴您的資料重疊，也仰賴協力廠商提供者與所有其他提供者的足跡 [!DNL Audience Manager] 客戶。 您的 [!DNL Adobe] 顧問可協助您識別其他相關資料來源，以最佳化潛在客戶活動。

### 移动用户和匹配率

尝试连接 [!DNL Safari] 的或移动应用程序用户在没有第三方 [!DNL cookies] 的情况下，不存在间隔。 这使得很难同步使用某些合作伙伴的用户，因为在媒体投放日志中仅 [!DNL Adobe] 提供同步第三方 [!DNL cookies] 的 id。 这是您可能看到 [ 低匹配率 ](../features/addressable-audiences.md#low-match-rates) 的 [!UICONTROL destinations] 原因。

## 日期范围 in [!UICONTROL Addressable Audiences] 和 [!UICONTROL Destinations] {#date-ranges}

请阅读以下章节以了解可用日期范围以及或 [!UICONTROL Destination] 的报表 [!UICONTROL Addressable Audience] 中每个时间间隔的数据访问量。

## 可用的日期範圍和時區 {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

您的報表 [!UICONTROL Addressable Audiences] 和 [目的地](../features/destinations/destinations.md) 使用相同的日期範圍間隔。 日期範圍選項包括：

* [!UICONTROL Last 1 Day] (此間隔會從前24小時的午夜執行到午夜。 它不是即時或目前的量度。)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

所有日期和日期範圍都設定在 [!DNL UTC] 時區。 另請參閱 [Audience Manager中的時區](../reference/aam-time-zones.md).

## 日期範圍間隔中的資料 {#date-range-intervals}

此 [!UICONTROL Addressable Audience] 和 [!UICONTROL Destination] 量度會傳回所選時間間隔內不重複使用者的計數。 例如，訪客只會計算一次，即使他們多次造訪您的網站亦然。 首次造訪是不重複造訪，且會加以記錄。 後續的造訪會為回訪，且不計入，因為這些造訪不是唯一的。

日期範圍包含所選時間間隔或更早時間的資料。 而且，資料會隨著時間流逝而在每個報告間隔內過期。 例如，假設您在選擇 [!UICONTROL Last 30 Days] 選項。 在報表中，這些訪客：

* *將為* 包含在較長的時間間隔（60天、90天和存留期）傳回的結果中。
* *将不会* 包含在选项（&quot;当前&quot;、&quot;7 天&quot; 和 &quot;14 天&quot;）之前 [!UICONTROL Last 30 Day] 的较短时间内。

而且，在第31天，这些访客仅在60天、90天和 [!UICONTROL Lifetime] 结果中显示。 他们已在30天内过期。 访客不会超出 [!UICONTROL Lifetime] 时间间隔。

## [!UICONTROL Addressable Audiences] 量度 {#addressable-audience-metrics}

本節說明以下專案所提供的度量型別： [!UICONTROL Addressable Audiences].

### 客戶層級量度 {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

這些量度會傳回訪客造訪您的網站或您將傳入資料檔案傳送至時所實現之特徵的資料 [!DNL Audience Manager]. 這些量度可全面檢視您帳戶的對象規模。

| 量度 | 描述 |
|---|---|
| [!UICONTROL Customer Addressable Audience] | 已實現以下任一情況的裝置重疊計數： [!UICONTROL rule-based trait] 或 [!UICONTROL onboarded trait] 在回顧視窗和裝置期間，無論同步時間為何，我們都有ID與所選目的地同步。<br><br>此量度代表具備下列條件的裝置：<ul><li>已實現 [!UICONTROL rule-based] 或 [!UICONTROL onboarded trait] 在回顧期間 `AND`</li><li>具有與所選專案同步的ID [!UICONTROL destination] 無論同步時間為何。</li></ul> |
| [!UICONTROL Customer Total Audience] | 已實現a的裝置計數 [!UICONTROL rule-based trait] 在您的屬性上或 [!UICONTROL onboarded trait] 在回顧期間從離線檔案中移除。 |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] 以百分比表示。 |

### 区段级别匹配量度 {#segment-level-metrics}

这些量度会在会员资格上 [!UICONTROL segment] 返回数据。 它们有助于为您 [!UICONTROL segments] 的每个视图提供更精细、更准确的受众大小。

>[!NOTE]
>
>在级别应用 [!UICONTROL segment] 的 &quot;返回&quot; 窗口的方式不同于 &quot;客户级别&quot; 中的外观。 访客可以进入网站并实现 [!UICONTROL trait] 10 天前，他们可以在2天前从一 [!UICONTROL segment] 开始就放弃 [!UICONTROL segment] 。 在应用7天的外观后，这些访客将计入 [!UICONTROL segment] 级别，而不是在客户级别。

| 量度 | 描述 |
|---|---|
| [!UICONTROL Segment Addressable Audience] | 屬於以下專案的使用者人數： [!UICONTROL segment] 在報表回顧期間執行，並在您的網站上進行作用中ID同步。 區段可以包含您自己的第一方資料、第二方資料和第三方資料，透過 [!UICONTROL traits] 取得於 [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>提示：搭配1天回顧期間使用時，此量度可協助您瞭解您目前的狀態 [!UICONTROL segments]. 這是因為 [!UICONTROL Segment Addressable Audience] 量度代表保留在中的使用者 [!UICONTROL segment] 整個前一天。 結合以下事實 [!DNL Audience Manager] 重新整理 [!UICONTROL Addressable Audiences] 每日，結合此量度和回顧期間，可提供您的最新快照 [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | 屬於您的成員的所有裝置計數 [!UICONTROL segment] 在報表回顧期間。 |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] 以百分比表示。 |

### 平台層級量度 {#platform-level-metrics}

此量度會傳回所有收集之活動的資料 [!DNL Audience Manager] 客戶。 相較於彙總，它們可提供客戶受眾的更廣泛檢視 [!DNL Audience Manager] 客戶。

| 量度 | 描述 |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | 與所有裝置互動的所有裝置計數 [!DNL Audience Manager] 在報表回顧期間處於平台層級的客戶，且可與您選取的相符 [!UICONTROL destination]. <br><br>此量度非常有用，因為它會顯示以下內容：<ul><li>的大小 [!UICONTROL total addressable audience] 該 [!DNL Audience Manager] 可以到達特定的目標定位目的地。</li><li>有多大 [!DNL Audience Manager] 設定檔集區適用於目標平台及其對象的大小。</li></ul> |

## 比較 [!UICONTROL Customer] 和 [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

請勿比較 [!UICONTROL Customer Addressable Audience] 和 [!UICONTROL Segment Addressable Audience] 量度，用來判斷一個量度是否比另一個量度重要。 這些量度是不同的、不同的和獨立的量度。 如上述定義所述，這些資料都衍生自不同的資料集。 有鑑於此，如果某個量度大於另一個量度，則應避免得出任何結論。 比較這些內容時，您只能說：

* [!UICONTROL Customer Addressable Audiences] 根據 [!UICONTROL trait] 實現 *用於您自己的第一方資料*. 此量度提供您與資料合作夥伴整合的廣泛、完整檢視。

* [!UICONTROL Segment Addressable Audiences] 是根據區段資格而定 *用於您自己的第一方資料，加上第二方和第三方資料*. 此量度可讓您更精細、準確地檢視 [!UICONTROL addressable audiences] 在目標定位平台中。

## 以下專案低符合率的原因： [!UICONTROL Addressable Audiences] {#low-match-rates}

造成偏低的常見元素 [!UICONTROL Addressable Audience] 匹配率或報告數字中的差異。

| 原因 | 描述 |
|---|---|
| 行動流量 | 最多 [!UICONTROL server-to-server] 整合需要協力廠商協助的同步流程 [!DNL cookies]. 不過，行動環境不使用協力廠商 [!DNL cookies]. 因此，您的 [!UICONTROL Addressable Audiences] 相較於 [!UICONTROL segment] 大小。 <br><br>自2018年1月起，您便可以在相同位置啟用行動對象 [!DNL Google] 和 [!DNL Adobe Advertising Cloud] 為設定的目的地 [!UICONTROL cookie-based] 對象。 這表示您可以傳送 [!UICONTROL segments] 合併的 [!DNL cookie] 以及您的行動ID會籍 [!DNL Google] 和 [!DNL Advertising Cloud] 目的地，請記住 [!UICONTROL Addressable Audiences] 只顯示下列專案之間的重疊： [!DNL cookie] ID和目的地。 [!DNL Audience Manager] 將100%的行動對象傳送至 [!UICONTROL destinations]，但行動對象不會由 [!UICONTROL Addressable Audience] 量度。 <br><br>**注意**：例如，以 [!UICONTROL segment] 擁有1,000,000人。 如果您對應 [!UICONTROL segment] 至 [!DNL Google] 或 [!DNL Adobe Advertising Cloud] 目的地，您可能會看到 [!UICONTROL Addressable Audience] 700,000部裝置和 [!UICONTROL Match Rate] 70%。 70萬名會員包括 [!DNL cookie] ID已與同步的ID [!UICONTROL destination]. 您的 [!UICONTROL Addressable Audience] 事實上，可能會高得多，因為可定址行動ID不會出現在此量度中。 |
| [!DNL Safari] 流量 | [!DNL Safari] 封鎖協力廠商 [!DNL cookies]. 這可防止 [!DNL Audience Manager] 將ID與同步 [!UICONTROL destination]. 透過以下主題介紹 [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)，您可以預期 [!UICONTROL addressable audiences] 不包括 [!DNL Safari] 使用者。 |
| 已追蹤的媒體曝光次數 | 由於廣告伺服器最佳實務，系統不會在廣告標籤中進行ID同步。 進行大量站外廣告的客戶不會將使用者同步到這些環境中的第三方整合。 此外，大量收集的媒體曝光資料可能會減少 [!UICONTROL addressable audience] 數字。 |

## 疑難排解 [!UICONTROL Addressable Audiences] {#troubleshooting}

除了曲面化符合率之外，您也可以使用 [!UICONTROL Addressable Audiences] 作為疑難排解工具。

例如，假設您將區段傳送至 [!UICONTROL destination] 以及 [!UICONTROL destination] 顯示低報告數字。 [!UICONTROL Addressable Audience]检查结果将显示这是技术故障，还是只是低匹配率的情况。低符合率會顯示您的 [!UICONTROL destination] 對您選取的區段來說，並非都那麼好。 但是，介于和 [!UICONTROL destination] 之间 [!DNL Audience Manager] 的数字差异 [!UICONTROL total addressable audience] 表示集成、同步或其他技术故障。在这些情况下，请联系您的客户经理。
