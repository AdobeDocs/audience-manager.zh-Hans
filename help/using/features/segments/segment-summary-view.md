---
description: 區段摘要頁面會顯示名稱、區段特徵、規則、效能資料和目的地對應資訊等詳細資訊。
seo-description: The segment summary page displays details such as name, traits in the segment, rules, performance data, and destination mapping information.
seo-title: Segment Details Page
solution: Audience Manager
title: 區段詳細資訊頁面
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: 身分型別劃分、身分劃分、對象身分報告、跨裝置、跨裝置ID、裝置ID
feature: Segments
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# 區段詳細資訊頁面 {#segment-summary-view}

個別區段的詳細資訊頁面提供區段詳細資訊的概觀，例如區段名稱、ID、績效量度、定義區段的規則以及目的地對應。 若要檢視這些詳細資訊，請前往 **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** ，然後按一下您要使用的區段名稱。

## 區段管理工具 {#segment-management-tools}

區段詳細資訊頁面頂端會託管可用來管理區段的工具：

1. **[!UICONTROL Add New]**：使用此選項啟動 [!UICONTROL Segment Builder] 和建立新區段。
2. **[!UICONTROL Edit]**：使用此選項可變更目前區段的設定。
3. **[!UICONTROL Duplicate]**：使用此選項可建立目前區段的復本。
4. **[!UICONTROL Delete]**：使用此選項可從Audience Manager帳戶中移除目前區段。
5. **[!UICONTROL Marketplace Recommendations]**：此選項會從尋找與您正在檢視的區段類似的區段 [!UICONTROL Audience Marketplace] 您尚未訂閱的資料摘要。 另請參閱 [適用於資料購買者的Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) 以瞭解如何導覽至市場並尋找類似區段。

![basic-segment-info](assets/basic-segment-information.png)

## 區段資訊 {#basics}

在區段管理工具下方，您可以找到下列區段資訊：

1. **[!UICONTROL Basic Information]：** 顯示建立區段時指定的必要和選用詳細資訊。 另請參閱 [區段產生器](segment-builder.md) 以取得這些欄位含義的詳細概觀。
2. **[!UICONTROL Segment Graph]：** 以圖形方式顯示效能資料，固定為1、7、14、30、60和90天間隔。 我們在「 」中說明區段母體數字 [單獨文章](../../features/segments/segment-builder-data.md).

   ![區段 — 圖表](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]：** 此報表會計算連結至符合區段資格之裝置的跨裝置ID及/或外部裝置圖表ID數量，顯示符合區段資格之使用者或家庭人數(顯示在 [!UICONTROL Total Segment Population])。 此報表中顯示的跨裝置ID和外部裝置圖表ID，可用來將設定檔與區段正在使用的設定檔合併規則合併。 只有在區段使用的設定檔合併規則中選取了跨裝置資料來源或外部裝置圖表時，才會顯示此報表。

   ![區段 — 圖表](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager只會顯示 [!UICONTROL Identity Type Breakdown] 報告是否有符合區段資格的跨裝置ID。

   觀看以下影片，概略瞭解 [!UICONTROL Identity Type Breakdown].
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]：** 列出區段中的特徵以及資格規則。
5. **[!UICONTROL Destination Mappings]：** 列出區段的目的地對應。
6. **[!UICONTROL Management Tools]：** 可讓您建立、編輯、複製和刪除區段的控制項。
