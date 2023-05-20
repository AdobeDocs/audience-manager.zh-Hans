---
description: 此程式會逐步引導您完成在Audience Lab中建立、編輯或刪除測試群組所需的步驟
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: 管理测试组
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 1%

---

# 管理测试组 {#manage-test-groups}

此程式會逐步引導您完成在中建立、編輯或刪除測試群組所需的步驟 [!UICONTROL Audience Lab].

## 建立區段測試群組 {#create-test-groups}

### 先决条件

<!-- create-test-group.xml -->

* 您至少需要一個 **轉換特徵** 設定。 您可以在中設定轉換特徵 [特徵產生器](../../features/traits/create-onboarded-rule-based-traits.md)，只要選取 **轉換** 做為事件型別。 如需轉換特徵及設定方式的詳細資訊，我們準備了 [視訊](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) 敬請參考使用。

   >[!IMPORTANT]
   >
   >[資料夾特徵](../../features/traits/about-folder-traits.md) 是 **不支援** 作者： [!UICONTROL Audience Lab]. 設定 [事件型別](../../features/traits/create-onboarded-rule-based-traits.md) 的資料夾特徵 **轉換** 不會在中產生任何資料 [!UICONTROL Audience Lab] 該特定資料夾特徵的。

* 針對使用 [角色型存取控制](../../features/administration/administration-overview.md)：指派 [!UICONTROL Audience Lab] [萬用字元許可權](../../features/administration/administration-overview.md#wild-card-permissions) 至 **[!UICONTROL User Groups]** 以提供存取權。 此許可權可讓使用者建立和檢視測試結果。 使用者將只能使用來自其資料來源的區段 **讀取** 和 **對應到目的地** 許可權。 使用者將只能使用來自其所擁有之資料來源的轉換特徵 **&quot;read&quot;** 許可權。 使用者也只能檢視他們有權存取的目的地。 因此，在新增 [!DNL Audience Lab] 群組的萬用字元許可權，請確定群組具有：
   * 存取權以讀取相關的轉換特徵；
   * 存取讀取和對應測試相關區段的許可權；
   * 相關目的地的存取權。

若要建立新的 [!UICONTROL Segment Test Group]：

1. 選取 **[!UICONTROL Create New Test Group]** 在 [!UICONTROL Audience Lab] 儀表板以啟動精靈。
1. **[!UICONTROL Basic Info & Choose Segment]**

   * 填入 **[!UICONTROL Test Group Name]** 和 **[!UICONTROL Description]**.
   * 選擇 **[!UICONTROL Base Segment]** 在檔案瀏覽器中導覽或是在搜尋列中輸入內容，然後按一下以確認 **[!UICONTROL Choose Segment.]**
   * 您可以將測試群組另存為草稿，稍後再繼續處理。
   * 如果您選取的基本區段已用於其他測試群組，則會顯示警報。 兩次使用基礎區段可能會扭曲兩個測試的轉換結果。

1. **[!UICONTROL Allocate Test Segments]**

   * 您可以建立 **最多15個測試區段** 並依需要分配裝置的百分比。
   * 您可以按一下測試區段來編輯其名稱。
   * 分配新測試區段時，百分比會自動平均分配為100%。 然後，您可以手動編輯百分比。 編輯百分比後按一下核取方塊，並確認百分比加起來為100%，否則您無法繼續下一個步驟。

1. **[!UICONTROL Set a Control Segment]**

   * 如果要將區段的某些部分保留下來作為控制組，請選取控制區段。 控制組可讓您檢視您所建立的測試區段與基準比較所產生的影響。
   * 您可以在下拉式清單中選取測試區段作為控制區段，也可以選擇 **[!UICONTROL None]** 無控制項。
   * 按一下 **[!UICONTROL Next]** 完成時。

1. **[!UICONTROL Select Conversion Traits]**

   * 在轉換特徵視窗中輸入，即可新增轉換特徵。 這是 **強制** ，而且除非您新增至少一個轉換特徵，否則無法繼續下一個步驟。
   * 您最多可以新增5個轉換特徵（如有需要）。
   * 如果您選取的轉換特徵已用於其他測試群組，則會顯示警報。
   * 請注意，Audience Manager不支援使用 [資料夾特徵](/help/using/features/traits/about-folder-traits.md) 作為轉換特徵。 將資料夾特徵選取為轉換特徵會導致0個彙總和趨勢報表顯示在測試中。

1. **[!UICONTROL Choose Destinations & Dates]**

   * 在搜尋欄位中輸入所需的目的地，或使用下拉式箭頭。 [!UICONTROL Audience Lab] 測試區段可以傳送至URL、Cookie或伺服器對伺服器目的地。
   * 將區段拖放至目的地。
   * 將區段拖曳至目的地後，請填入 **[!UICONTROL Destination Mapping Value]** 在盲人中。
   * 您可以將相同的測試區段傳送至多個目的地，也可以將多個測試區段新增至單一目的地。
   * 如果根據的特定測試區段無法使用目的地，則會以灰色顯示 [資料匯出控制](../../features/data-export-controls.md).
   * 使用者只能根據以下專案檢視他們有權存取的目的地 [rbac使用者群組](../../features/administration/administration-overview.md) 它們屬於。
   * 最後，您必須為測試群組選取開始日期。 此日期會標籤測試群組發佈至目的地期間的開始。 選取 **無結束日期** 進行無限期測試區段比較。

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] 具有已驗證的設定檔時，僅支援即時目的地。 如果具有該設定的設定檔合併規則的測試區段傳送至檔案式伺服器對伺服器目的地，則對象可能不會填入。

   按一下 **[!UICONTROL Next]** 以檢閱並完成您的測試群組。

1. **[!UICONTROL Summary & Finalize]**

   * 檢閱您在先前步驟中新增的資訊，並選取 **[!UICONTROL Finalize Group]**.
   * 請記住，完成測試群組後，可以複製或刪除該群組，但不能進行編輯。

   >[!NOTE]
   >* 您可以在建立過程中的任何時候儲存測試群組，並稍後返回精靈。 測試群組狀態將會是 **[!UICONTROL Draft]** 而且在您完成區段測試群組之前，測試群組不會傳送任何資料至目的地。
   >* 對於草稿測試，您可以返回並按一下以編輯測試群組 **[!UICONTROL Edit]** 在測試群組卡中 [!UICONTROL Audience Lab] 檢視。


## 編輯區段測試群組 {#edit-test-groups}

在 [!UICONTROL Audience Lab]，您只能編輯草稿測試群組。 在 [!UICONTROL Create Segment Test Group] 精靈，您可以將測試群組儲存為草稿，稍後再繼續處理。

1. 導覽至 [!UICONTROL Audience Lab] 主檢視。
1. 搜尋您的草稿測試群組並選取 **[!UICONTROL Edit]** 控制測試群組卡片。
1. 繼續 [建立區段測試群組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 精靈並選取 **[!UICONTROL Finalize Group]** 完成時。

## 刪除區段測試群組 {#delete-test-groups}

1. 導覽至 [!UICONTROL Audience Lab] 主檢視。
1. 尋找您要刪除的測試群組。 您可以:

   * 按下 **[!UICONTROL Delete]** 控制測試群組卡，或
   * 按測試群組卡片中的測試群組標題，前往 [測試群組資訊](../../features/audience-lab/audience-lab-information-view.md) 檢視並按下 **[!UICONTROL Delete]** 標題列中的控制項。

1. 對象 [已完成的測試區段](../../features/audience-lab/audience-lab.md#status)，系統會顯示警報，提示您下載CSV檔案以儲存報表（如有需要）。
