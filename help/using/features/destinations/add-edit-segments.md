---
description: 「資料匯出標籤」可搭配您在資料來源上設定的「匯出控制」使用。 「資料匯出標籤」可防止您將受限制的特徵新增至區段，以及防止將區段資料傳送至目的地。 您可以將多個匯出標籤設定為新的或現有的Cookie或URL目的地。
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: 添加或编辑服务器到服务器目标的区段
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 7%

---

# 添加或编辑服务器到服务器目标的区段 {#add-edit-segments}

您只能新增或編輯伺服器對伺服器的區段([!DNL S2S])目的地。 您無法建立 [!DNL S2S] 目的地和 [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). 請聯絡您的顧問以進行設定 [!DNL S2S] 目的地。 依照下列指示，為新增或編輯區段 [!DNL S2S] 目的地。

<!-- destination-s2s-edit.xml -->

若要新增或編輯的區段對應 [!DNL S2S] 目的地：

1. 前往 **[!UICONTROL Audience Data > Destinations]**. 選取 **整合平台>以裝置為基礎** 並找到 [!DNL S2S] 您要使用的目的地。
2. 在 [!UICONTROL Action] 欄中，按一下鉛筆圖示即可編輯目的地。
   * 在 **[!UICONTROL Search and Add Segments]** 方塊中，開始輸入區段名稱或按一下 **[!UICONTROL Browse All Segments]** 瀏覽可用區段的清單。
   * 按一下 **[!UICONTROL Add Selected Segments]** 當您找到要使用的區段時。 新增區段會開啟 [!UICONTROL Edit Mapping] 視窗。
   * 在 [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**：設定 [機碼值組](../../features/destinations/key-value-pairs.md) 供此目的地使用。
      * **[!UICONTROL Start Date]** 和 **[!UICONTROL End Date]**：選擇目的地的開始和結束日期。 如果結束日期為空白，目的地永遠不會過期。
3. 按一下 **[!UICONTROL Save]** 然後按一下 **[!UICONTROL Done]**.
