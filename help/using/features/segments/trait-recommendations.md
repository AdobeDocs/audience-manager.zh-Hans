---
description: 使用“特征推荐”，在区段生成器中构建或编辑区段时，您能够获得可包含的其他推荐特征（与区段规则中的特征类似）。将推荐的特征添加到区段中，可增加目标受众。
seo-description: Get live trait recommendations as you build your segments.
seo-title: Trait Recommendations
solution: Audience Manager
title: 特征推荐
feature: Segments
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1562'
ht-degree: 8%

---

# 特征推荐

在建立區段時，從您自己的第一方特徵取得即時特徵建議，並且 [!UICONTROL Audience Marketplace] 資料摘要。

## 影片示範

從觀看 [!UICONTROL Trait Recommendations] 下列影片，然後閱讀以瞭解詳細資訊。 影片示範會示範如何使用來自您第一方特徵的建議，以及來自的特徵建議 [!UICONTROL Audience Marketplace] 資料摘要， *您已訂閱*.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

下一段影片會概述的工作流程 [!UICONTROL Marketplace Recommendations]，說明如何根據中的資料摘要建議，將特徵新增至區段 [!UICONTROL Audience Marketplace]. 這些建議所根據的資料摘要具有 *您尚未訂閱*.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## 概述

[!UICONTROL Trait Recommendations]，提供者 [!DNL Adobe Sensei]，可將資料科學帶入您的Audience Manager日常工作流程。
替換為 [!UICONTROL Trait Recommendations]，當您在中建立或編輯區段時 [區段產生器](segment-builder.md)，您會得到可包含的其他特徵建議，這些特徵與區段規則中的特徵類似。

Audience Manager會向您顯示來自第一方特徵的特徵建議，位於 **[!UICONTROL Recommendations]** 區域，以及從 **[!UICONTROL Audience Marketplace]**，在 **[!UICONTROL Recommendations from Marketplace]** 區段。

将推荐的特征添加到区段中，可增加目标受众。

![特徵Recommendations概觀](assets/trait-recommendations-overview-full.png)

**簡而言之：**

* Audience Manager會在「 」中顯示第一方特徵 [!UICONTROL Recommendations] 區段。 您未訂閱的公開和私人摘要中的Marketplace建議會顯示在 [!UICONTROL Recommendations from Marketplace] 區段。 按一下摘要名稱以前往 [!UICONTROL Audience Marketplace] 並訂閱。
* Audience Manager最多可顯示50個與區段規則中的特徵類似的特徵。
* 您可以篩選掉不想看到任何建議的資料來源。
* 計算相似性時，Audience Manager會考慮 [UUID](../../reference/ids-in-aam.md) 過去30天內符合特徵的。
* 如果您看到錯誤訊息「找不到類似的特徵。 特徵可能太新。」，這表示在過去30天內沒有該特徵的活動，或Audience Manager尚未更新該特徵的建議。 請24小時後再試一次。

## 用例

替換為 [!UICONTROL Trait Recommendations]，您可以根據您使用Audience Manager的方式，改善工作流程：

* 行銷人員可透過類似特徵快速找到對互補產品感興趣的對象，進而擴大您的觸角。
* 如果您使用Audience Manager作為發行者，請 [!UICONTROL Trait Recommendations]，您可以瞭解對象行為，並建立更佳的區段以用於廣告銷售或使用者贏取。
* 作為 [!UICONTROL Audience Marketplace] 資料購買者，我想要探索相關的第三方資料，而不需瀏覽大量摘要。
* 作為 [!UICONTROL Audience Marketplace] 資料提供者，我想要向買家建議相關資料，以便我從最佳和相關訂閱中受益。

## 特徵Recommendations和演演算法模型之間的差異

### 算法模型

[!UICONTROL Algorithmic Models] 不僅可找出最具影響力的特徵，還會根據這些特徵對使用者進行評分，並為每位使用者指派個別的分數。 然后，便可以通过创建算法特征来定位用户。精準度與觸及率控制於 [!UICONTROL Trait Builder]，您可以指定想要鎖定具有影響力之特徵的所有使用者中的哪些使用者。

[!UICONTROL Algorithmic Models] 可讓您選取不同精確度等級的使用者，並在下列位置進行測試： [!UICONTROL Audience Lab] 哪一組使用者轉換率較高。 有关详细用例，请参阅[在 Audience Lab 中比较模型](../../features/audience-lab/audience-lab-use-cases.md#compare-models)。

在 [!UICONTROL Algorithmic Models]，模型每8天執行一次，並會重新整理符合演演算法特徵的使用者。

### 特征推荐

[!UICONTROL Trait Recommendations] 是快速深入分析其他與您在區段中所使用特徵相似的特徵的方法。

您應使用 [!UICONTROL Trait Recommendations] 時間：

* 构建区段时需要快速获取信息；
* 要将区段用于短期促销活动，或者希望快速抑制转化的受众；
* 想要最大化范围。

## 工作流

在中建立或編輯區段時 [區段產生器](segment-builder.md)中，您可以探索與區段規則中的特徵相似的特徵。 此 [區段產生器](segment-builder.md) 新區段和現有區段的工作流程非常類似：

### 新區段

1. 前往 **受眾資料>區段**，然後按一下 **新增**.
1. 在 **特徵** 下拉式方塊中，至少新增一個特徵至區段規則。
1. 您可以看到第一方建議特徵和 [!UICONTROL Audience Marketplace] 特徵建議來自您所訂閱的摘要，位於 **[!UICONTROL Recommendations]** 區段。 此 **[!UICONTROL Recommendations from Marketplace]** 區段會顯示您未訂閱之摘要的特徵建議。 所有這些建議都與新增至區段規則的特徵類似。 向下捲動以檢視所有建議的特徵。
1. （選用）若要從特定資料來源排除建議的第一方特徵，請按一下 **X** 要排除的資料來源符號。

   >[!NOTE]
   >
   >排除的資料來源會顯示在建議特徵清單的正上方。 按一下 **X** 以移除排除專案，並再次檢視個別資料來源的結果。
1. 若要將建議特徵新增至區段規則，請按一下 **+** 符號。

>[!IMPORTANT]
>
>新增時 [!UICONTROL Marketplace] 特徵對應至區段，特徵僅用於區段估計，直到您訂閱相對應的資料摘要為止。 來自您未訂閱之資料摘要的特徵，會在特徵清單中標示購物車圖示。 按一下特徵名稱，即可前往資料摘要頁面並訂閱。
>
>![marketplace-not-subscribed](assets/trait-recommendations-marketplace.png)
>
>您必須先訂閱對應的資料摘要，才能儲存具有第三方特徵的區段。

### 現有區段

1. 前往 **[!UICONTROL Audience Data]>[!UICONTROL Segments]**，選取您要編輯的區段並按一下 ![編輯](assets/edit-button.png).
1. 向下捲動至 [!UICONTROL Traits] 下拉式方塊。
1. 您可以看到建議的特徵，這些特徵與區段規則中已存在的特徵類似。 向下捲動以檢視所有建議的特徵。
1. （選用）若要從特定資料來源排除建議的特徵，請按一下 **X** 要排除的資料來源符號。

   >[!NOTE]
   >
   >排除的資料來源會顯示在建議特徵清單的正上方。 按一下 **X** 以移除排除專案，並再次檢視個別資料來源的結果。
1. 若要將建議特徵新增至區段規則，請按一下 **+** 符號。

當您建立或編輯區段並將特徵新增至區段規則時，最多會看到50個建議特徵，與您新增的特徵類似。 如果區段規則包含多個特徵，Audience Manager會使用循環配置圖方法來顯示每個特徵的最佳相符專案，然後是每個特徵的第二個最佳相符專案，依此類推，以便區段規則中依母體區分的最大50個特徵。

![三個基本特徵](assets/three-base-traits.png)

例如，區段規則中有三個特徵時（如下所示），建議使用的特徵為：

1. 特徵3 （人口最多的特徵）的最佳配對；
1. 特徵1的最佳相符專案；
1. 特徵2的最佳相符專案；
1. 特徵3的次佳匹配；
1. 第二個最符合特徵1，以此類推，直到您得到50個特徵。

若要取得特定特徵的建議，您可以在區段規則(1)或建議的特徵檢視(2)中按一下特徵。

![base-traits-example](assets/three-base-traits-numbered.png)

按一下第一方特徵會開啟快顯視窗，如下圖所示。 如果推薦的特徵不是區段的一部分，您可以按一下「 」，將其新增至區段 **+**.

![附加至區段](assets/add_to_segments.png)

>[!TIP]
>
>在特徵資訊彈出式視窗中產生建議時，會考慮從首頁面排除的資料來源。 此外，如果您在此檢視中排除資料來源，排除專案會套用至首頁面。

>[!NOTE]
>
>推薦的特徵可以是您訂閱之資料摘要中的第一方特徵或第三方特徵 [!UICONTROL Audience Marketplace].

## 工作原理

若要產生特徵建議，Audience Manager會計算 [Jaccard相似度](https://en.wikipedia.org/wiki/Jaccard_index) 介於目標特徵與您的帳戶可存取的所有其他特徵之間，包括協力廠商資料。 Audience Manager接著會顯示最多50個具有最高相似度的特徵。

## 特徵相似度分數 {#trait-similarity-score}

Audience Manager計算 [!UICONTROL Trait Similarity Score] 計算兩個特徵之間的交集和並集，計算兩個特徵的 [!UICONTROL UUID]s然後除以這兩者。 針對兩個特徵A和B，計算方式如下：

![jaccard-similarity](assets/jaccard_similarity.png)

另請參閱下列兩個範例。

### 範例1 — 低特徵相似度分數

假設兩個特徵A和B各有1,000,000個母體 [!UICONTROL UUID]s， 25,000 [!UICONTROL UUID]符合兩個特徵的。
使用上述公式，這會產生：25,000 / 1,975,000 = 0.012。這是低品質 [!UICONTROL Trait Similarity Score]，這兩個特徵非常相異。

![特徵 — 建議 — 低重疊](assets/Trait-Recommendations-Low-overlap.png)

### 範例2 — 特徵相似度分數

如果相同特徵A和B有400,000個 [!UICONTROL UUID]同時符合兩個特徵的 [!UICONTROL Trait Similarity Score] 高得多：400,000 / 1,600,000 = 0.25

![特徵 — 建議 — 高重疊](assets/Trait-Recommendations-High-overlap.png)

### 如何解讀特徵相似度分數

使用下表作為特徵相似度的粗略指南。 本指南是根據大多數特徵中觀察到的相似性分數。

| [!UICONTROL Trait Similarity Score] | 重要性 |
|---------|----------|
| 0.1及更高版本 | 特徵之間的高相似性 |
| 0.03 - 0.1 | 特徵之間的中等相似度 |
| 0.01 - 0.03 | 特徵之間的低相似性 |
| 0 - 0.01 | 特徵之間的相似度很低 |

## 角色型存取控制(RBAC)

針對使用 [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC])，您需要有建立和編輯區段的許可權，才能檢視建議的特徵。 您看到的特徵建議只有您透過存取之資料來源的特徵建議 [!UICONTROL RBAC].

>[!IMPORTANT]
>
>若要新增 [!UICONTROL Marketplace Recommendations] 對於區段，使用者必須先訂閱對應的資料摘要。 只有具有管理員許可權的使用者才能訂閱 [!UICONTROL Audience Marketplace] 資料摘要。

深入瞭解 [!UICONTROL RBAC] 控制項 [此處](../administration/administration-overview.md).

## 限制

* 目前，Audience Manager不會將資料夾特徵顯示為建議的特徵。 深入瞭解資料夾特徵 [此處](../traits/manage-folder-traits.md).
* 顯示特徵Recommendations時，Audience Manager未考慮 [!DNL Boolean] 運運算元([!DNL AND]， [!DNL OR]， [!DNL NOT])區段規則中的。
