---
description: 從所有訊號建立新特徵，包括已用於特徵的訊號，並擷取在特徵建立後符合資格的未來對象。
seo-description: Create new traits from all signals, including those that are already used in traits, and capture future audiences that qualify after trait creation.
seo-title: Create Traits from Signals
title: 从信号创建特征
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 2%

---

# 从信号创建特征

從所有訊號建立新特徵，包括已用於特徵的訊號，並擷取在特徵建立後符合資格的未來對象。 觀看影片以快速示範，或閱讀以取得詳細資訊：

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## 從Signal儀表板建立特徵 {#create-traits-from-signal-dashboard}

此 [!UICONTROL Signal Dashboard] 可讓您從 [!UICONTROL Top Unused Signals]， [!UICONTROL New Unused Signals]，以及您已儲存的搜尋。

建立新特徵時，會根據訊號型別預先設定特徵型別：

* **[!UICONTROL Rule-based]** 即時訊號的特徵、可操作的記錄檔和 [!DNL Adobe Analytics] 訊號；

* **[!UICONTROL Onboarded]** 已上線訊號的特徵。

若要從建立新特徵 **[!UICONTROL Signal Dashboard]**，識別您要在特徵中使用的訊號，然後按一下對應的 **[!UICONTROL Create Rule-Based Trait]** 或 **[!UICONTROL Create Onboarded Trait]** 連結。

![](assets/signals-create-trait.png)

系統會將您重新導向至 **[特徵產生器](../../features/traits/about-trait-builder.md)** 以建立您的新特徵。

## 從訊號搜尋建立特徵 {#create-traits-from-signal-search}

根據未顯示在「 」中使用或未使用的訊號建立特徵 [!UICONTROL Signal Dashboard].

搜尋特定訊號，並根據結果建立規則型或已上線的特徵。 以下是其操作方式：

1. 前往 **[!UICONTROL Audience Data > Signals > Search]** 並根據您要尋找的索引鍵值配對執行搜尋，或按一下 **[!UICONTROL Search]** 而不輸入任何索引鍵/值配對以顯示所有結果。
2. 在結果清單中識別您要在特徵中使用的訊號。
   * 若要從一個訊號建立特徵，請按一下對應的 **[!UICONTROL Create Rule-Based Trait]** 或 **[!UICONTROL Create Onboarded Trait]** 連結。
   * 若要從多個訊號建立特徵，請按一下每個訊號對應的核取方塊，然後按一下 **[!UICONTROL Create Trait from Multiple Signals]**.

   >[!NOTE]
   >您只能從相同型別的訊號建立特徵。 您無法根據即時訊號與已上線訊號的組合來建立特徵。
   >
   > ![](assets/signals-create-trait-search.png)
   >您也可以從使用的訊號建立特徵。 已用於特徵的訊號，其特徵數量會顯示在 **[!UICONTROL Included in Traits]** 欄。 按一下箭頭，以檢視包含訊號的特徵。
   >
   >![](assets/signals-used-traits.png)

3. 使用 **[特徵產生器](../../features/traits/about-trait-builder.md)** 以建立您的新特徵。
