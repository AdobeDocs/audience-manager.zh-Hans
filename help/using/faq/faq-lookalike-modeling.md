---
description: 相似建模可協助您透過自動化資料分析，探索新的不重複受眾。 本文提供常見問題的解答。
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: 相似建模常見問題集
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
source-git-commit: 37823ae54e106e32aa195a6b69e0f1ebfc322f09
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# 相似建模常見問題集

## 概述 {#overview}

本文將針對以下各項提供常見問題的解答： [!UICONTROL Look-Alike Modeling].

## 問題 {#questions}

**為什麼我會持平 [!UICONTROL Accuracy & Reach] 圖表？**

平坦 [!UICONTROL Accuracy & Reach] 圖表表示幾乎所有使用者在模型中都會獲得相同的分數。 當您在執行模型的資料來源中包含網站訪客特徵時，可能會發生此情況。 為避免此問題，請在模型建立步驟期間，使用 [!UICONTROL Exclusions] 欄位。

 

**為什麼我的一些最具影響力特徵只有很小的受眾？**

演演算法會選取與基線特徵高度關聯的特徵。 例如，如果指定特徵與基線特徵有100%的重疊，則其權重會很高，即使該特徵中的使用者人數很少亦然。

 

**為什麼我的模型沒有執行/重新執行？**

只有在您已建立至少一個使用中的演演算法特徵並將其對應至使用中的區段和目的地時，產生結果的模型才會繼續執行。

 

**為什麼我的模型沒有產生任何結果？**

這通常是因為在選取的資料來源中，基準母體與母體之間沒有顯著的特徵重疊所導致。

 

**對於基準特徵或區段大小是否有任何建議？**

由於基準母體與所選資料來源中的母體之間存在重大特徵重疊，因此只有數千名使用者才足以執行模型。 [!UICONTROL Look-Alike Modeling] 產生更精確的結果，基線會越大。

 

**我應該為我的模型選擇哪些協力廠商資料來源？**

使用至少與基線特徵/區段有部分重疊，但同時引進其他使用者的資料來源。 您也應該考慮與每個資料摘要相關的成本。 成本與定價模型因資料提供者而異，例如： [!UICONTROL Audience Marketplace].

 

**使用協力廠商資料來建立模型是否需要費用？**

這取決於所選資料摘要的定價模型。 有些摘要會免費提供模型製作，有些則會向您收費。 另請參閱 [資料摘要購買者的計費方式](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md) 以取得詳細資訊。

 

**我可以建立多少模型/特徵？**

目前，您最多可以建立20個演演算法模型和50個演演算法特徵。

 

**模型訓練和演演算法特徵母體的重新整理頻率為何？**

模型每8天會重新訓練一次，並會重新整理演演算法特徵母體。
