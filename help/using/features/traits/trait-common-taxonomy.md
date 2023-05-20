---
description: 本文提供使用通用分類法將特徵分類的一般概觀。
keywords: DIL
seo-description: This article provides general overview about classifying traits with a common taxonomy.
seo-title: Classifying Traits with a Common Taxonomy
solution: Audience Manager
title: 使用通用分类法对特征进行分类
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 3%

---

# 使用通用分类法对特征进行分类 {#classifying-traits-with-a-common-taxonomy}

本文提供使用通用分類法將特徵分類的一般概觀。

## Audience Manager分類法

<!-- c_common_taxonomy_about.xml -->

此 [!DNL Audience Manager] 分類法是一項選擇性功能，可透過統一、邏輯且眾所周知的命名慣例，對特徵進行分類。 它會在平台層級運作，以協助確保整個環境中的命名一致性 [!DNL Audience Manager] 生態系統。 歸根結底，通用分類法的設計目的是讓我們的產品更符合有關消費者隱私權和選擇退出程式的產業標準。

## 特徵分類的優點

讓客戶建立自訂區段和資料模型是 [!DNL Audience Manager] 以及您從我們的平台獲得價值的能力。 然而，我們也需要強大且可擴展的手段，將有關區段的資訊傳達給您的客戶和合作夥伴。 此外，這項通訊要求區段資訊以容易理解和普遍理解的語言分享，同時保護您的專屬特徵和區段名稱。 此 [!DNL Audience Manager] 通用分類法提供此語言和功能。

## 分類法使用產業標準分類類別

通用分類法是根據 [!DNL Interactive Advertising Bureau (IAB)]. 請參閱 [!DNL IAB]的 [網站](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) 以取得網路與交換器品質保證指引的詳細資訊。

## 分類組織

此 [!DNL Audience Manager] 分類法會將資料整理到稱為層的巢狀類別中。 每個類別最多可包含3個不同的資料分類階層。 在最高層級，第1級類別會將資料分組為其最一般的形式（例如地理位置）。 後續層級會為較高層級的一般類別提供更明確的特性(例如， *geography —>美國 — >紐約*)。 不過，並非每個類別都有3個階層，有些僅使用2個。

## 分類資料類別中的特徵

在中建立或編輯特徵時，您可以指派分類法分類 [!UICONTROL Add New Trait Wizard] (位於* **[!UICONTROL Audience Data > Traits]***)。 請參閱 [建立特徵的相關檔案](../../features/traits/create-onboarded-rule-based-traits.md) 以取得詳細資訊。

## 使用分類：其他考量事項

如果您決定根據我們通用的分類法來分類特徵，請務必記住：

* 分類為 *可選*.
* 特徵 *不是* 依預設指派給分類類別（也就是說，特徵不會分類為「未知」或「未分類」等）。
* 特徵可以屬於 *一* 僅限分類類別（不允許多重和跨類別分類）。
