---
description: 本文說明如何為新整合和現有整合設定Twitter自訂對象。
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: 將Twitter自訂對象設定為自助服務以裝置為基礎的目的地
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 1%

---

# 設定 [!DNL Twitter Custom Audiences] 以裝置為基礎的自助服務目的地 {#configure-twitter}

本文說明如何透過設定整合 [twitter自訂對象](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## 先决条件 {#prerequisites}

設定前 [!DNL Twitter Custom Audiences] 目的地，請確定您符合下列必要條件。

* 您的 [!DNL Twitter Ads] 帳戶必須符合廣告資格。 新增 [!DNL Twitter Ads] 帳戶在建立後的前2週內不符合廣告資格。
* 您的 [!DNL Twitter] 您在Audience Manager中授權存取的使用者帳戶必須具有 [合作夥伴Audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 許可權已啟用。
* 建立第一個 [!DNL Twitter Custom Audiences] 目的地(在您的Audience Manager執行個體中)，請聯絡Adobe諮詢或客戶服務以啟用 [!DNL Twitter] 您的帳戶的ID同步（資料來源ID = 1123）。 這是Audience Manager和之間正確同步的必要條件 [!DNL Twitter].

## 新增 [!DNL Twitter Custom Audiences] 目的地 {#add-new-twitter-destination}

本節說明在設定以裝置為基礎的新目的地時，必須遵循的步驟。 [!DNL Twitter Custom Audiences]. 此情境假設您沒有現有的 [!DNL Twitter Custom Audiences] 透過您的Adobe顧問或客戶服務設定的目的地。

### 步骤 1. 驗證方式 [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

在新增以裝置為基礎的目的地之前，您需要連結Audience Manager和 [!DNL Twitter Custom Audiences] 帳戶。 以下是其操作方式：

1. 登入您的Audience Manager帳戶並前往 **[!DNL Administration > Integrated Accounts]**. 如果您先前設定好與目的地平台的整合，您應會看到此頁面中列出的整合。 否則，頁面會是空的。
1. 单击 **[!DNL Add Account]**.
1. 選取 [!DNL Twitter Custom Audiences] 並按一下 **[!DNL Confirm]** 重新導向至「驗證」頁面。

   ![整合平台](assets/dbd-integrated-platforms.png)

1. 驗證之後，系統會將您重新導向至Audience Manager，您應可在其中檢視關聯的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下 **[!DNL Confirm]**.

### 步骤 2. 建立以裝置為基礎的新目的地 {#step2-create-new-destination}

連結Audience Manager和 [!DNL Twitter Custom Audiences]，即可建立新目的地。 以下是其操作方式：

>[!NOTE]
>
>您無法變更現有以裝置為基礎的目的地的名稱。 請務必提供有助於您正確識別目的地的名稱。

1. 登入您的Audience Manager帳戶，前往 **[!DNL Audience Data > Destinations]**，然後按一下 **[!DNL Create Destination]**.
1. 在 **[!DNL Basic Information]** 區段，輸入 **[!DNL Name]** 和 **[!DNL Description]** ，並使用下列設定： ![設定](assets/dbd-new-basic.png)
1. 单击 **[!DNL Next]**.
1. 選擇 [資料匯出標籤](/help/using/features/data-export-controls.md#controls-labels) 要為此目的地設定的值。
1. 单击 **[!DNL Save]**.
1. 在 **[!DNL Segment Mappings]** 區段，選取您要傳送至此目的地的對象區段。
1. 儲存目的地。

## 區段對應考量事項 {#segment-mapping-considerations}

將受眾區段對應至時 [!UICONTROL Twitter]，確定符合下列區段命名需求：

* 提供人類看得懂的區段對應名稱。 建議您使用與Audience Manager區段相同的名稱。
* 請勿使用特殊字元(`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`)中。 如果您的Audience Manager區段名稱包含這些字元，請先移除這些字元，然後再將區段對應至 [!UICONTROL Twitter] 目的地。

### 示例

* 正確的區段或對應名稱：「美國和歐洲購物者」；
* 不正確的區段或對應名稱：「US， European 5h0pP3rs」。

>[!IMPORTANT]
>
>您無法變更已對應區段的名稱。 Audience Manager會使用區段名稱來正確識別整合中的區段。

## 匹配率考量事項 {#match-rates-considerations}

* Audience Manager與之間的整合 [!UICONTROL Twitter Custom Audiences] 支援歷史受眾回填。 所有區段資格皆會傳送至 [!UICONTROL Twitter] 建立目的地時。

## 故障排除 {#troubleshooting}

設定或傳送資料至Twitter自訂對象目的地時，您可能會遇到下列錯誤。 本節說明可能導致錯誤的原因以及如何修正錯誤。

| 錯誤訊息 | 發生次數/原因 | 解决方法 |
|---|---|---|
| `Internal server error` | 嘗試新增時，Audience ManagerUI中會顯示此錯誤訊息 [!DNL Twitter] 使用過時版本Twitter API的帳戶。 | 联系 Adobe 客户关怀. |
| `Twitter Error: This request is not properly authenticated` | 嘗試將不支援的區段名稱對應至目的地時，Audience ManagerUI中會顯示此錯誤訊息。 | 檢閱對應的區段名稱，確認不含不支援的字元。 另請參閱 [區段對應考量事項](#segment-mapping-considerations) 不支援的字元清單。 |
| `Twitter Error: Account XXXXXXXXX was not found` | 當為目的地設定的認證未獲授權存取對應的Twitter Ads帳戶時，此錯誤訊息會顯示在Audience ManagerUI中。 | <ul><li>請確定您使用的帳戶認證符合 [必備條件](#prerequisites).</li><li>使用相同的認證導覽至Twitter Ads UI，並檢查對應的下方是否顯示正確的對象 `XXXXXXXXX` 帳戶。 </li></ul> |