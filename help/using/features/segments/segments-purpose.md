---
description: 說明區段及其組成部分，以及使用「區段產生器」建立規則。
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: 區段用途、構成和規則
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 3%

---

# 区段：目的、构成和规则 {#segments-purpose-composition-and-rules}

說明 [!UICONTROL segments]、其組成部分，以及規則建立工具 [!UICONTROL Segment Builder].

## 用途 [!UICONTROL Segments]

A *`segment`* (或 *`audience`*)是共用共同屬性的一組使用者。 在Audience Manager中，您建立 [!UICONTROL segments] 與伺服器端規則搭配使用。 這些規則可讓您根據網站訪客屬性來建立對象群組，例如：

* 行为;
* 人口統計（年齡、性別、收入等）；
* 您可在使用者介面中定義的其他特性。

## [!UICONTROL Segment] 組合

Audience Manager [!UICONTROL segment] 是伺服器端規則，包含個人或一組特徵。 特徵是由稱為機碼值組的資料元素所組成。 以及您在 [!UICONTROL segment] 層級，這些機碼值組包含判斷訪客是否符合特徵與資格的條件 [!UICONTROL segment] 會籍。

## 注意事項 [!UICONTROL Adobe Analytics] [!UICONTROL Segment] 對應

對應Adobe Analytics時 [!UICONTROL segments] 或報告套裝至您的Experience Cloud組織，Audience Manager會自動建立新的、對應的、唯讀 [!UICONTROL segments] 和特徵。 您無法編輯或變更這些專案的儲存位置 [!UICONTROL segments] 從Audience Manager。 不過，您在對應的Adobe Analytics上執行的任何變更 [!UICONTROL segments] 或報表套裝反映在Audience Manager中。

>[!TIP]
>
>Audience Manager [!UICONTROL segments] 與 [!DNL Adobe Analytics] [!UICONTROL segments]. 讀取 [瞭解Analytics和Audience Manager中的區段](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) 以取得差異的深入說明。

## 建立規則型 [!UICONTROL Segments] 替換為 [!UICONTROL Segment Builder]

有別於傳統畫素，傳統畫素會根據簡單的是/否條件引發， [!UICONTROL Segment Builder] 可讓您建立複雜專案 [!UICONTROL segment] 需求。 按讚 [!UICONTROL traits]， [!UICONTROL segments] 評估資料，使用 [!DNL Boolean] 運算式([!DNL AND]， [!DNL OR]， [!DNL NOT])、比較運運算元（大於、小於、等於等）和造訪間隔/頻率條件。 這些功能有助於建立重點對象 [!UICONTROL segments] 與您的業務需求相關。

## 优点

[!UICONTROL Segments] 改善標準畫素式對象建立/細分程式，因為這些程式可讓您：

* 建置相關、有用 [!UICONTROL segments] 與第一方和第三方特徵。
* 使用布林運運算元、比較運算式和造訪間隔/頻率條件，建立複雜複雜的分段規則。
* 傳送 [!UICONTROL segment] 將資料傳送至目的地合作夥伴。
* 使用Audience Manager報告監控效能。

>[!MORELIKETHIS]
>
>* [信号、特征和区段](../../reference/signal-trait-segment.md)

