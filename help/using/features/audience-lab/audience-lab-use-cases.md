---
description: Audience Lab可讓您使用基準區段來建立測試群組，進而啟用多個使用案例。 您可以將測試群組劃分為數個互斥的測試區段，將這些區段對應至不同的目的地，然後判斷哪些區段在推動轉換方面最有效。
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Audience Lab 用例
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 1%

---

# Audience Lab 用例 {#audience-lab-use-cases}

[!UICONTROL Audience Lab] 可讓您使用基準線區段來建立測試群組，以啟用數個使用案例。 您可以將測試群組劃分為數個互斥的測試區段，將這些區段對應至不同的目的地，然後判斷哪些區段在推動轉換方面最有效。

## 在Audience Lab中比較模型 {#compare-models}

您可以在中使用幾種不同型別的模型和模型來源 [!DNL Audience Manager]. [!UICONTROL Audience Lab] 讓您輕鬆比較使用中模式中客戶的轉換率。

<!-- audience-lab-compare-models.xml -->

在此使用案例中，您會比較不同的模型。 您可以使用透過內部資料倉儲建立的模型，並將其匯入 [!DNL Audience Manager] 作為 [已上線的特徵](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 或者，您可以使用 [演演算法模型](../../features/algorithmic-models/understanding-models.md) 中的功能 [!DNL Audience Manager].

1. 在「 」中建立兩個模型 [模型產生器](../../features/algorithmic-models/create-model.md)，或透過外部平台。
1. 建立 [演演算法特徵](../../features/traits/create-algorithmic-traits.md) 從演演算法模型匯入，或將您自己的模型匯入為已上線的特徵。
1. 建立互斥區段，使兩個模型中的使用者不會重疊：

   * 建立 *模型1區段* 和 *模型2區段*.
   * 擁有以下專案的區段規則： *模型1區段* 是模型1特徵 [!DNL AND NOT] 模型2特徵，反之亦然 *模型2區段*.

1. [建立兩個區段測試群組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 在 [!UICONTROL Audience Lab]，其中一個具有 *模型1區段* 作為基準線，另一個則使用 *模型2區段* 作為基準線。

   * 讓兩個測試群組的變數相同：相同的目的地、創意、轉換特徵。
   * 確保測試區段具有相似的使用者人數（例如160萬和180萬正確，160萬和1600萬不正確）。
   * 在每個測試區段測試群組中保留控制區段。 如此一來，您可以預留每個區段的一小部分，而不會在測試中明確鎖定這些區段。

1. 檢查結果：

   * 此 [Audience Lab報表檢視](../../features/audience-lab/audience-lab-reporting-view.md) 將顯示每個模型正在推動的轉換次數。 對於轉換型行銷活動，推動最多轉換的測試區段將表示績效最佳的模式。
   * 由於您有控制區段，因此也可以根據「標準目標定位」評估模型的表現。 您不僅要測試一種模型而非另一種模型，還要測試「此模型是否比一般實務做得更好？」的問題。

## 測試多個目的地的創意內容 {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

使用 [!UICONTROL Audience Lab] 測量創意內容在不同目的地帶來的轉換次數。 此使用案例也可讓您根據自然發生的轉換來測量創意的轉換。

1. [建立區段測試群組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)，選取您要用來測試創意作為基準區段的區段。
1. 將基準線區段分割為測試區段和控制區段。
1. 將測試區段對應至您要測試的不同目的地。
1. 控制區段可以保留，並且不會對應到任何目的地。 測試創意不應將控制區段設為目標，以設定自然發生轉換的結果基準。
1. 指定測試的開始日期和結束日期。
1. 在目的地中設定區段和創意。
1. 此 [Audience Lab報表檢視](../../features/audience-lab/audience-lab-reporting-view.md) 將顯示創意內容在目的地的轉換次數。
1. 由於您建立了控制區段，因此也可以根據自然發生的轉換來評估創意表現。 您正在測試問題：「此創意內容產生的轉換率是否高於正常作法？」
