---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Managing Predictive Audiences
solution: Audience Manager
title: 开始使用 Predictive Audiences
feature: Algorithmic Models
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 4%

---

# 开始使用 Predictive Audiences {#predictive-audiences-getting-started}

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 本文不包含任何法律建議。 請諮詢您自己的法律顧問，以獲得法律指引。

## 建立預測受眾模型 {#create-predictive-audiences}

建立之前 [!UICONTROL Predictive Audiences] 模型，您必須決定要指派給您的第一方資料來源 [!UICONTROL Predictive Audiences] 的特徵和區段至。 您可以使用現有的第一方資料來源，或建立新的第一方資料來源。 另請參閱 [管理資料來源](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html) 以取得有關如何建立新的第一方資料來源的詳細資訊。

瞭解您要使用的資料來源後，請遵循下列步驟。

1. 前往 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. 在 [!UICONTROL Predictive Audiences] 區段，按一下 **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. 接下來，定義您要依其分類對象的角色。 您可以選取要從中建置角色的特徵或區段來執行此操作。 使用 [!UICONTROL Traits] 和 [!UICONTROL Segments] 索引標籤位於畫面的左上角，可在特徵和區段目錄之間切換。 在識別您要當作角色的特徵或區段後，請按一下對應的 **[!UICONTROL Add]** 圖示於 [!UICONTROL Action] 欄。
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >您必須至少為基線角色選擇兩個特徵或兩個區段。 您無法使用特徵和區段的組合。
1. 按一下 **[!UICONTROL Next]** 在您定義角色之後。
1. 接著，選取您要分類的第一方對象，方法是為此對象選擇第一方特徵或區段。 使用 [!UICONTROL Traits] 和 [!UICONTROL Segments] 索引標籤位於畫面的左上角，可在特徵和區段目錄之間切換。 選取您要用作對象的第一方特徵或區段，以將其新增至模型。
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. 按一下 **[!UICONTROL Next]** 在您選擇對象後。
1. 填寫模型詳細資料：
   * **[!UICONTROL Model Name]**：輸入模型的描述性名稱，以協助您稍後識別。 模型產生的區段名稱將以模型名稱開頭。
   * **[!UICONTROL Description]**：輸入模型的說明，以協助您識別其使用案例。
   * **[!UICONTROL Data Source]**：選取您想要的第一方資料來源 [!UICONTROL Predictive Audiences] 要指派給此模型的區段。
   * **[!UICONTROL Profile Merge Rule]**：選取 [!UICONTROL Profile Merge Rule] 將指派給所有預測性 [!UICONTROL segments] 由此模型建立。 如果您選取的目標對象為 [!UICONTROL segment]，建議您選取相同的 [!UICONTROL Profile Merge Rule] 目標對象的ID。
      ![predictive-audience-save](assets/predictive-audiences-save.png)
1. 单击 **[!UICONTROL Save]**.

## 複製和編輯預測對象模型 {#clone-predictive-audiences}

Audience Manager不支援編輯現有 [!UICONTROL Predictive Audiences] 模型。 若要變更模型的組態，您可以建立現有模型的複製並加以編輯。 以下說明如何執行此操作：

1. 前往 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. 按一下 [!UICONTROL Predictive Audiences] 要複製的模型。
3. 按一下 **[!UICONTROL Clone]** 按鈕。
   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)
4. 複製模型後，您會被帶到 [!DNL Save & Configure] 複製模型的頁面。 您可以在此頁面變更 [!UICONTROL data source] 和已指派的[!UICONTROL Profile Merge Rule] 模型的。 若要編輯角色和複製模型的目標對象，請使用 [!UICONTROL Back] 和 [!UICONTROL Next] 按鈕，在三個標籤之間導覽，或按一下三個標簽名稱

   ![預測受眾 — 複製 — 導覽](assets/predictive-audiences-clone-navigate.png)

5. 編輯完模型後，按一下 **[!UICONTROL Save]**.

## 刪除預測對象 {#delete-predictive-audiences}

若要刪除 [!UICONTROL Predictive Audiences] 模型，前往 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，找到您要刪除的模型，然後按一下 **[!UICONTROL Delete]** 圖示。
