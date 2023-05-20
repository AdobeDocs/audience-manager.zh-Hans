---
description: 將「對象管理模組」新增至Adobe Analytics AppMeasurement，將Analytics資料轉送至Audience Manager，而非讓Audience ManagerData Integration Library(DIL)代碼從頁面傳送畫素。
keywords: audience analytics； analytics； ssf；伺服器端轉送
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: 實作對象管理模組
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# 如何從轉送資料 [!DNL Adobe Analytics] 至 [!DNL Audience Manager] {#implement-the-audience-management-module}

請依照本教學課程中的步驟來轉寄 [!DNL Analytics] 資料目標 [!DNL Audience Manager] ，而非 [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL])程式碼會從頁面傳送畫素。

>[!TIP]
>
>我們建議您使用 [!DNL Adobe Experience Platform Tags] 轉寄 [!UICONTROL Analytics] 資料匯入 [!DNL Audience Manager]. 透過使用 [!UICONTROL Tags]，您不必手動將程式碼複製到 [!DNL AppMeasurement]，如本頁所示。

## 先决条件 {#prereqs}

除了啟用擴充功能或實作本檔案所述的程式碼外，您還必須：

* 實作 [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* 啟用 [伺服器端轉送](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) 中的報表套裝 [!UICONTROL Adobe Analytics Admin Console].

## 实施 {#implementation}

實作資料轉送的方法有兩種 [!DNL Adobe Analytics] 至 [!DNL Audience Manager]，視您使用的標籤管理解決方案而定。

### 實作，使用 [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] 建議您使用 [標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) 樂器延伸 [!DNL Adobe Analytics] 和 [!DNL Audience Manager] 在您的屬性上。 在這種情況下，您不需要手動複製任何程式碼。 反之，您必須在以下位置啟用資料分享： [!DNL Analytics] 副檔名，如下圖所示。 另請參閱 [Adobe Analytics擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager) 說明檔案。

>[!TIP]
>
>如果您安裝 [!DNL Adobe Analytics] 擴充功能， *不要* 同時安裝 [!DNL Audience Manager] 副檔名。 從轉送資料 [!DNL Analytics] 擴充功能會取代 [!DNL Audience Manager] 擴充功能。

![如何從Adobe Analytics擴充功能啟用資料共用至Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## 定義的程式碼元素 {#code-elements-defined}

下表定義程式碼範例中的重要變數。

| 参数 | 描述 |
|--- |--- |
| `partner` | 必需。這是由指派給您的合作夥伴名稱 [!DNL Adobe]. 有時稱為 [!UICONTROL partner ID] 或合作夥伴子網域。  聯絡您的 [!DNL Adobe] 顧問或 [客戶服務](https://helpx.adobe.com/cn/marketing-cloud/contact-support.html) 如果您不知道您的合作夥伴名稱。 |
| `containerNSID` | 必需。大部分客戶只需設定  `"containerNSID":0` . 不過，如果您的公司需要自訂使用不同容器的ID同步，您可以在此處指定該容器ID。 |
| `uuidCookie` | 可选。此設定可讓您設定 [!DNL Adobe] 第一方網域中的cookie。 此 [!DNL cookie] 包含 [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | 必需。此 `namespace` 若您使用 [!DNL AudienceManagement] 模組搭配 [!UICONTROL AppMeasurement] 版本2.10或更新版本。 此 [!UICONTROL AudienceManagement] 模組需要您使用 [!UICONTROL Adobe Experience Platform Identity Service] 3.3或更新版本。 <br><br>此 [!UICONTROL Experience Cloud Organization ID] 是公司註冊時提供的ID。 [!UICONTROL Experience Cloud]. 瞭解您公司的組織ID，請參閱 [組織和帳戶連結](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## 結果：資料轉送至 [!DNL Audience Manager] {#results-data-forwarding}

您的 [!DNL Analytics] 實作會將資料傳送至 [!DNL Audience Manager] 在您擁有以下專案後：

* 已啟用 [!UICONTROL Server-Side Forwarding] （請洽詢您的顧問以瞭解此功能）；
* 已實作 [!DNL Adobe Experience Platform Identity Service]；
* 已按照本教學課程中的實作步驟進行。

此程式會將資料傳送至 [!DNL Audience Manager]：

* 在頁面檢視呼叫上；
* 從追蹤的連結；
* 從視訊里程碑和心率視訊檢視。

>[!NOTE]
>
>傳送至的變數 [!DNL Audience Manager] 從 [!DNL Analytics] 使用特殊字首。 建立時，您需要瞭解並考慮這些字首 [!DNL Audience Manager] 特徵。 如需這些字首的詳細資訊，請參閱 [關鍵變數的前置詞要求](../../features/traits/trait-variable-prefixes.md).
