---
description: 說明演演算法特徵建立程式專屬的設定步驟和功能。
seo-description: Describes set up steps and features unique to the algorithmic trait creation process.
seo-title: Create Algorithmic Traits
solution: Audience Manager
title: 创建算法特征
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 4%

---

# 创建算法特征 {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

若要建立演演算法特徵，請前往 [!UICONTROL Traits] 並遵循下列步驟：

1. 按一下 **[!UICONTROL Create New Trait]** 並選取 **[!UICONTROL Algorithmic]** 從下拉式功能表。
1. 在 [基本資訊](../../features/traits/create-onboarded-rule-based-traits.md) 區段
   * 為特徵命名。
   * 選取資料來源。
   * 選擇儲存資料夾。
1. 展開 [!UICONTROL Configuration] 窗格並按一下 **[!UICONTROL Browse All Models]**.
這會開啟一個新視窗，讓您選取要與特徵一起使用的模型。
1. 選取模型並按一下 **[!UICONTROL Add Selected Model to Trait]**.
新增模型會公開觸及範圍和精確度設定。
1. 選取觸及率或準確度作為您的目標，然後從各自的下拉式選單中選擇一個值。 按一下 **[!UICONTROL Save]** 完成時。

## 演演算法特徵的組態設定 {#configure-settings}

在 [!UICONTROL Trait Builder]，則 [!UICONTROL Configuration] 區段可讓您將演演算法模型與特徵建立關聯。 若要完成演演算法特徵建立程式，請選取模型並選擇觸及率或準確度目標。

### 先决条件

<!-- r_algo_trait_config_section.xml -->

* [创建相似人群拓展模型](../../features/algorithmic-models/create-model.md).
* 等候通知電子郵件，通知您模型資料執行已完成。
* 填妥以下欄位中的必填欄位： [基本資訊](../../features/traits/create-onboarded-rule-based-traits.md) 區段。

### 組態欄位與設定

| 介面元素 | 说明 |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | 按一下 **[!UICONTROL Update]** 按鈕以開啟模型視窗。 從視窗中，選取要用來建立特徵的演演算法模型。 |
| **[!UICONTROL Select Goal Accuracy]** | 選取此選項可根據精確度建立特徵。 精確度是已評分的值，可指出潛在使用者與基線之間的距離有多近。 精度刻度的範圍從0 （最不準確）到1 （最準確）。 |
| **[!UICONTROL Reach and Accuracy Data Columns]** | 此區段位於右側，最多可顯示21列數值資料，這些資料顯示模型的精確度和觸及值。 |
| **[!UICONTROL Reach and Accuracy Slider]** | 滑桿位於圖表底部，可讓您設定觸及度或準確度目標的數值。 您可以設定滑桿，然後選擇觸及或準確度目標按鈕來建立特徵。 |

>[!MORELIKETHIS]
>
>* [精度和范围](../../features/traits/trait-accuracy-reach.md)

