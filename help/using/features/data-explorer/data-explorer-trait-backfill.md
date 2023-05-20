---
description: 回填特徵實現以擷取歷史對象，並避免在特徵建立日期之前遺失相關資料。
seo-description: Backfill trait realizations to capture historical audiences and avoid loss of relevant data prior to a trait creation date.
seo-title: Backfill Trait Realizations
title: 回填特征实现
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 1%

---

# 回填特征实现 {#backfill-trait-realizations}

回填特徵實現以擷取歷史對象，並避免在特徵建立日期之前遺失相關資料。

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] 是一項進階功能，可透過解鎖其他使用案例來增強Audience Manager體驗。 回填需要額外的處理能力，所有Audience Manager客戶都可透過此方式取得回填，但需支付額外費用。 如需其他詳細資訊，請聯絡您的Adobe銷售代表。

從未使用的訊號建立特徵時，您可以選擇在特定時段內回填特徵實現。 [!DNL Audience Manager] 擷取符合新特徵資格受眾的歷史資料，並將其儲存在對應的設定檔上。 您可以看到 **[!UICONTROL Backfill Options]** 在 [!UICONTROL Trait Expression] 部分 **[特徵產生器](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>您可以針對規則型和已上線的特徵，回填特徵實現。

以下說明如何回填特徵實現：

1. 前往 [!UICONTROL Audience Data > Signals > Search] amd執行訊號搜尋或使用 [訊號控制面板](../../features/data-explorer/data-explorer-signals-dashboard.md) 識別要用於新特徵中的訊號。
1. 根據所需的訊號建立新特徵。
1. 使用 **[!UICONTROL Backfill Options]** 在 **[!UICONTROL Trait Expression]** 區段來選取您要回填特徵實現的時間間隔。 預先定義的回填間隔包括1、7、14和30天。 您也可以選擇最長30天的自訂日期範圍。

   ![特徵回填](assets/signals-trait-backfill.png)

1. （可選）按一下 **[!UICONTROL Estimate Realizations]** 在 **[!UICONTROL Estimated Trait Realizations]** 區段以檢視預估值 [!UICONTROL Unique Trait Realizations] 和 [!UICONTROL Total Trait Population] 過去7天回填特徵的值。

   ![預估特徵實現](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >使用下列運運算元的運算式無法使用特徵回填和預估：
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 建立特徵。

完成特徵建立後，您會看到其回填的實現專案包含在實現統計資料中。

觀看以下影片，瞭解如何回填特徵的影片逐步解說。

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## 特徵回填延遲 {#trait-backfilling-latency}

新建立的特徵會在建立兩到三個小時後開始擷取對象。 然而，由於大量的資料會 [!DNL Audience Manager] 每日執行，回填的母體不會立即反映在 [!UICONTROL Unique Trait Realizations] 和 [!UICONTROL Total Trait Population] 圖表。

Audience Manager更新 [!UICONTROL Trait Graph] 在特徵建立後48小時內使用回填母體。

## 特徵回填限制 {#trait-backfilling-limit}

[!UICONTROL Data Explorer] 可讓您每月回填最多50個特徵，且回填計數器會在每月的1日重設。

>[!NOTE]
>
>特徵回填配額不會從前幾個月延續。 例如，如果您在本月回填30個特徵，下個月的特徵回填配額會重設為50，而不是70。

## 對報表的影響 {#reporting-impact}

回填的特徵實現會反映在 [!UICONTROL Unique Trait Realizations] 和 [!UICONTROL Total Trait Population] 量度，作為 [!DNL Audience Manager] 將歷史訊號轉換為特徵實現。

不過， [!UICONTROL Trait Graph]， [!UICONTROL General Reports]、和 [!UICONTROL Trend Reports] 不會在特徵建立日期之前回填歷史量度，以回溯更新。
