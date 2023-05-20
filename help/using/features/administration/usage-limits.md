---
description: Audience Manager會設定您可為帳戶建立的特徵、區段、目的地和演演算法模型數量上限。 限制適用於這些專案，無論是在使用者介面中建立或是透過API方法以程式設計方式建立。 使用量限制有助於保護Audience Manager，避免自動化程式可能試圖危害API或使用者介面。
seo-description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-title: Usage Limits
solution: Audience Manager
title: 使用限制
keywords: ID對應、ID對應、Cookie對應
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 7%

---

# 使用限制 {#usage-limits}

Audience Manager會設定您可為帳戶建立的特徵、區段、目的地和演演算法模型數量上限。 限制適用於這些專案，無論是在使用者介面中建立，或是透過程式設計方式建立 [!DNL API] 方法。 使用量限制有助於保護Audience Manager，避免自動化程式可能危及我們的安全 [!DNL API]或使用者介面。

## ID 映射限制 {#id-mapping-limits}

下表列出 [ID對應](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) 裝置ID的限制。 當ID達到以下任何限制時，Audience Manager會根據FIFO （先入先出）邏輯新增新的ID對應，方法是移除最舊的已儲存ID對應，然後新增新的ID對應。 請參閱 [ID索引](../../reference/ids-in-aam.md) 在Audience Manager中瞭解Audience Manager支援的ID詳細資訊。

| ID對應 | 最大限制 |
|-----------|-------------- |
| 裝置廣告ID ([DAID](../../reference/ids-in-aam.md))重新命名為Cross-device ID ([DPUUID](../../reference/ids-in-aam.md)) | 100個裝置廣告ID ([DAID](../../reference/ids-in-aam.md))至1個跨裝置ID ([DPUUID](../../reference/ids-in-aam.md)) |
| 跨裝置ID ([DPUUID](../../reference/ids-in-aam.md))至裝置廣告ID ([DAID](../../reference/ids-in-aam.md)) | 10個跨裝置ID ([DPUUID](../../reference/ids-in-aam.md))至1個裝置廣告ID ([DAID](../../reference/ids-in-aam.md))，每個 [DPID](../../reference/ids-in-aam.md) |
| Cookie/瀏覽器ID轉換為Cookie/瀏覽器ID | 將1000個Cookie/瀏覽器ID調整為1個Cookie/瀏覽器ID |

## 專案限制 {#item-limits}

表格會依專案型別列出目前的限制。 您無法建立新特徵、區段、目的地或 [!UICONTROL Algorithmic Models] 如果您達到其中一個專案的特定限制。 如果您確實達到限制，則必須先刪除舊專案，才能建立新專案。

### 特徵限制

| 特徵型別 | 最大限制 |
| -------------------------- | ------------------------------------- |
| 特徵總數 | 100,000 |
| 特徵資格總數 | 150,000. 如需特徵資格的相關詳細資訊，請參閱中的特徵資格限制。 [特徵資格參考](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit). |
| 演演算法 | 50 |
| 基於規則 | 100,000 |
| 已上線 | 100,000 |
| 資料夾特徵 | 2,000 |

### 區段限制

| 區段型別 | 最大限制 |
| -------------- | ------------- |
| 區段總數 | 20,000 |

### 目的地限制

| 目的地型別 | 最大限制 |
| ------------------ | ------------- |
| 目的地總數 | 1,000 |
| Cookie | 1,000 |
| URL | 1,000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### 演演算法模型限制

| 项目 | 最大限制 |
| -------- | ----- |
| 活动 [!UICONTROL Look-Alike Models] | 20.僅Audience Manager計數 *作用中* 演演算法模型不受限制。 |
| [!UICONTROL Look-Alike Models] 最大對象人數 | 25,000,000.  請注意，此限制無法增加。 您可以為模型選取較少的資料來源或選取較短的回顧視窗，藉此縮小對象規模。 |
| 「 」的排除特徵數上限 [!UICONTROL Look-Alike Model] | 500。請參閱 [演演算法模型中的特徵排除](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| 最大值 [!UICONTROL Predictive Audiences Models] | 10 |
| 的基線角色最大數量 [!UICONTROL Predictive Audiences Models] | 50 |

### 資料夾限制

| 项目 | 最大限制 |
| ------------- | ------------------ |
| 特徵資料夾 | 2,000.  您的資料夾結構最多可包含5層深。 |

### 衍生訊號限制

| 项目 | 最大限制 |
| --------------- | ------------- |
| 派生的信号 | 50,000. |

### 公司使用者帳戶限制

| 项目 | 最大限制 |
| ----------- | ------------- |
| 公司的使用者帳戶數上限 | 1,000. |

## 監視使用情況 {#monitor-usage}

您可以前往「 」，檢視您帳戶的使用量和限制 **[!UICONTROL Administration > Limits]**. 存取需要管理員許可權。

![使用量限制影像](assets/usage-limits.png)

## 增加專案限制 {#increase-item-limits}

這裡列出的預設限制應該會提供足夠的容量來滿足您的業務需求。 如果您的組織持續達到這些限制，請聯絡您的客戶代表以討論增加事宜。
