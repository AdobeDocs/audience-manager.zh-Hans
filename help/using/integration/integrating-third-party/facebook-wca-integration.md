---
description: 此頁面說明建立Facebook網站自訂對象(WCA)畫素的程式，其目的在於將網頁型Audience Manager對象區段傳送至Facebook，以透過改善透明度進行線上廣告目標定位。
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Facebook WCA 集成
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 8780083474d68717fe3bd4dc632d96da89929122
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 3%

---

# [!DNL Facebook WCA] 集成 {#facebook-wca-integration}

此頁面說明建立流程 [!DNL Facebook Website Custom Audiences] ([!DNL WCA])畫素（用於傳送網頁型檔案） [!DNL Audience Manager] 對象區段至 [!DNL Facebook]，適用於改善透明度的線上廣告目標定位。

## 概述 {#overview}

[facebook網站自訂對象(WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) 可讓您建立瀏覽過特定頁面或在您的網站上採取特定動作的人清單。 [!DNL Audience Manager] 啟用啟用 [!DNL WCA] 使用 [!DNL URL] 目的地，您可以在此處設定自訂的畫素式整合，以將網頁式對象傳送至 [!DNL Facebook] 目標定位。

![Facebook WCA 集成](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 此功能需要您選取 [!UICONTROL Website] 中的社交平台對象選項 [URL目的地](/help/using/features/destinations/create-url-destination.md). 社交平台要求反向連結資訊在傳送至其平台時不得遮罩。 請注意，這表示目的地平台/合作夥伴將能夠檢視反向連結中的資訊 [!DNL URL].

## 先决条件 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] 區段，已準備好指派給您的新區段 [!DNL Facebook] 目的地。 這裡是 [如何建立區段](/help/using/features/segments/segment-builder.md) 在 [!DNL Audience Manager] UI。
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) 4.1.0版或更新版本。 下載最新版本 **[此處](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) 9.0版或更新版本，可下載自 **[此處](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. 或者，如果您使用 [伺服器端轉送(SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) 將資料匯入 [!DNL Audience Manager]，您必須使用AppMeasurement 2.12版或更新版本。 下載 [!DNL AppMeasurement] 使用 [Analytics代碼管理器](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

建議您使用下列步驟3和4安裝或升級程式庫： [Adobe Experience Platform標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## 步驟1 — 建立 [!UICONTROL Facebook Destination] 在 [!DNL Audience Manager] {#step-1-create-facebook-destination}

建立新的 [!UICONTROL URL Destination] 在 [!DNL Audience Manager] 並為其命名 [!DNL Facebook Website Custom Audiences]. 建立目的地時，請使用下列設定。 您也可以參閱 [設定URL目的地](/help/using/features/destinations/create-url-destination.md) 頁面。

### 基本信息

* **[!UICONTROL Category]**: 自定义
* **[!UICONTROL Type]**: [!DNL URL]
* 選取 **[!UICONTROL Auto-fill Destination Mapping]** 核取方塊，然後選取 **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

選取選項 **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> 此匯出標籤可防止區段中包含協力廠商資料和從裝置圖表衍生的資料。

### 配置

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. 透過選取此 [!UICONTROL URL Type] 選項， [!DNL Audience Manager] 不會遮蔽反向連結 [!DNL URL] 引發時的資訊 [!DNL Facebook WCA] 畫素。
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* 在 **[!UICONTROL Base URL]** 和 **[!UICONTROL Secure URL]** 欄位，輸入 [!DNL Facebook WCA] 畫素。
* **[!UICONTROL Delimiter]**: `,`

基礎 [!DNL URL] 範例： `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

從頁面引發的畫素範例。 此範例顯示符合三項資格的使用者 [!DNL Audience Manager] 區段，其ID為3401321、2993399、3263410：

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 参数 | 描述 |
|---------|----------|
| `id` | 您的 [!DNL Facebook] 畫素ID，您可以在 [!DNL Facebook Ad Manager] 建立對象畫素時的使用者介面。 |
| `ev` | Event. 這是任意值，將出現在 [!DNL Facebook Ad Manager] 一旦畫素開始在網站上引發，使用者介面。 請參閱 [!UICONTROL Include] 中的專案 [步驟3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)，以取得詳細資訊。 |
| `cd[segID]` | 另一個引數，此引數會開始填入 [!DNL Facebook Ad Manager] 一旦畫素開始在網站上引發，使用者介面。 `segID` 也是任意的。 |
| `%ALIAS%` | 一個 [!DNL Audience Manager] 巨集，動態替換為 [!DNL Audience Manager] [!UICONTROL segment] 網站訪客符合資格的ID，以逗號分隔， |

您的 [!UICONTROL URL destination] 設定應該如下圖所示：

![目的地設定](/help/using/integration/assets/facebook-wca.png)

儲存 [!UICONTROL destination]. 接著，您可以繼續前往 **區段對應** 步驟。

## 步驟2 — 區段對應 — 將區段對應至目的地 {#step-2-segment-mappings}

在 [設定URL目的地](/help/using/features/destinations/create-url-destination.md) 工作流程，將適用的區段對應至您新建立的 [!UICONTROL destination]. 請注意，對應值會自動填入 [!DNL Audience Manager] [!UICONTROL segment ID].

輸入結束日期（若適用），否則將留空表示無結束日期。

## 步驟3 — 建立 [!UICONTROL Audience] 範圍 [!DNL Facebook Ads Manager] {#step-3-create-audience}

另請參閱 [建立網站自訂對象](https://www.facebook.com/business/help/666509013483225) 在 [!DNL Facebook] 說明檔案。 選取 [!UICONTROL Create Audience] 選項見下表：

| 项目 | 描述 |
|---------|----------|
| 網站流量 | 自訂組合 |
| 包含 | <ul><li>選取 **[!UICONTROL Event]** >選取 **[!UICONTROL Adobe-Audience-Manager-Segment]**. 這是以下專案的值： `ev` 引數（在步驟1的範例畫素中）。 請注意，如果畫素尚未引發， **[!UICONTROL Event]** 選項或 **[!UICONTROL Adobe-Audience-Manager-Segment]** 可能不會出現在 [!DNL Facebook] 使用者介面。</li><li>新增引數：選取 `segID`.</li><li><p>選取 **包含** 運運算元。</p><p>這很重要，因為訪客可能符合多個區段的資格，因此可能有多個 [!UICONTROL segment IDs] 在畫素引數中。 使用等於(`=`)運運算元可能無法讓訪客符合受眾資格，而且您將觀察到數量較少的訪客。</p></li><li>新增值：輸入 [!DNL Audience Manager] 區段ID。</li></ul> |
| 新增條件 | 選擇性設定。 |
| 最近 | 選擇性設定。 |
| 對象名稱 | 我們建議您使用相同的 [!DNL Audience Manager] 區段名稱以保持一致性，除非您向此對象新增其他條件。 |

## 步驟4 — 指派 [!UICONTROL Audience] 至 [!UICONTROL Campaign] 在 [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

建立之後 [!DNL Custom Audience]，將其指派至廣告行銷活動。 建立新行銷活動或編輯現有行銷活動，您會發現新建立的對象列在 [!DNL Facebook] 使用者介面。 如果使用者造訪您的網站時，您的廣告行銷活動會鎖定已看到其瀏覽器上觸發畫素的使用者 [!DNL Audience Manager] 將它們包含在區段中。

## 概要 {#summary}

現在您已指派 [!DNL Audience Manager] 區段至 [!DNL Facebook WCA] 目的地， [!DNL Audience Manager] 將會選擇性地引發 [!DNL Facebook WCA] 畫素填入至具有畫素中相應區段ID之指定區段的使用者 [!DNL Facebook Audience]. 這會導致 [!DNL Facebook Audience] 對網站上適用對象觸發的標籤越多。

>[!NOTE]
>
> 如果使用者退出 [!DNL Audience Manager] 區段，目前無法 [!DNL Audience Manager] 通知 [!DNL Facebook] 將使用者從 [!DNL Custom Audience].
