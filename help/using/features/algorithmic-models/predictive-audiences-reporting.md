---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Reporting
solution: Audience Manager
title: Predictive Audiences 报表
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---

# Predictive Audiences 报表

在您儲存 [!UICONTROL Predictive Audiences] 模型，Audience Manager會開始訓練。 在數小時內，計算模型將會開始在 [資料收集伺服器](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs). 報告功能將於次日提供。

若要檢視的結果，請 [!UICONTROL Predictive Audiences] 分類，前往 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，然後按一下清單中的模型。

使用左側的篩選選項來搜尋模型名稱或根據模型型別篩選結果。

![預測受眾 — 篩選](assets/predictive-audiences-filter-models.png)

模型表格會顯示下列資訊：

* **[!UICONTROL ID]**：模式ID可唯一識別Audience Manager帳戶中的每個模式；
* **[!UICONTROL Name]**：您在模型建立步驟中提供的名稱；
* **[!UICONTROL Description]**：您在模型建立步驟中提供的說明；
* **[!UICONTROL Model Type]**：每個模型的型別([!UICONTROL Look-Alike Modeling] 或 [!UICONTROL Predictive Audiences])；
* **[!UICONTROL Status]**：每個模型的狀態：
   * **[!UICONTROL Pending]**：模型正在初始化，很快就會開始產生結果；
   * **[!UICONTROL Active]**：模型成功執行並產生結果；
   * **[!UICONTROL Warning]**：由於資料不足（即基線母體低，使用者設定檔不豐富），模型無法產生結果；
   * **[!UICONTROL Error]**：模型無法執行。 請聯絡您的Adobe代表。

## 模型概觀報表{#model-report}

選擇模型後，其報表頁面即會載入。 在頁面頂端，您可以根據1天的即時實現，檢視前5個最大的預測區段，模型已依此將您的目標對象分類。 此 **[!UICONTROL Other]** 類別包含其餘角色，這些角色未包含在前5個最大的預測性區段中。

Audience Manager會同時顯示您專屬的色標環圈圖和時間軸圖表 [!UICONTROL Predictive Audiences].

按一下頁面頂端的角色標籤，可在圖表和圖形中新增或移除角色。

環圈圖以人物為基礎顯示目標對象的劃分，而圖表則顯示過去6天預測區段的1天即時母體趨勢。

如果模型狀態為 [!UICONTROL Pending]， [!UICONTROL Warning]，或 [!UICONTROL Error]，則會顯示模型狀態而非圖形。

![smart-persona-report](assets/predictive-audiences-report.png)

報告表格會顯示每個專案的下列資訊 [!UICONTROL Predictive Audiences] 區段。

1. **[!UICONTROL SEGMENT ID]**：與每個角色相關聯之自動建立的區段的區段ID；
1. **[!UICONTROL NAME]**：角色名稱；
1. **[!UICONTROL STATUS]**：的狀態 [!UICONTROL Predictive Audiences] 區段：
   * **[!UICONTROL Succeeded]**：使用者分類至此區段；
   * **[!UICONTROL Pending]**：區段仍在初始化中；
   * **[!UICONTROL Insufficient Training Data]**：由於資料不足，使用者未分類到此區段。 總基線母體太低，提供的資料不足以供學習。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**：過去24小時內每個角色的區段實現次數。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**：過去24小時內，每個角色在模型母體總數中的區段實現百分比。

## 具影響力的特徵{#influential-traits}

[!UICONTROL Influential Traits] 是以下條件的特徵： [!UICONTROL Predictive Audiences] 演演算法被發現是判斷訪客角色分類的最強預測因子。

其符號表示特徵的存在會增加(+)或減少(-)使用者屬於所選角色的可能性。

若要檢視所有角色具有影響力的特徵，請按一下 [!UICONTROL View All Influential Traits].

此 [!UICONTROL Influential Traits] 視窗會針對所選模型中的每個角色，顯示下列資訊：

![影響特徵](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**：所選角色每個具影響力之特徵的特徵ID；
1. **[!UICONTROL NAME]**：所選角色每個具影響力特徵的名稱；
1. **[!UICONTROL DESCRIPTION]**：所選角色每個具影響力特徵的說明；
1. **[!UICONTROL WEIGHT]**：所選角色每個具影響力特徵的權重。 [!UICONTROL Influential Traits] 預設會依權重降序排序。  權重值表示其預測能力。 此符號會指出特徵的存在會增加(+)還是減少(-)屬於某個角色的可能性。
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**：過去30天內，所選角色每個具影響力之特徵的獨特特徵實現次數。
