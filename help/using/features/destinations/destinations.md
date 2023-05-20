---
description: 了解目标（任何第三方系统，如您共享数据的广告服务器或 DSP）的优势、类型和用法。使用 Destination Builder 创建和管理 Cookie、URL 或服务器到服务器目标。
keywords: 整合代碼，目的地，目的地概觀，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地
landing-page-description: 了解目标（任何第三方系统，如您共享数据的广告服务器或 DSP）的优势、类型和用法。使用 Destination Builder 创建和管理 Cookie、URL 或服务器到服务器目标。
short-description: 了解目标（任何第三方系统，如您共享数据的广告服务器或 DSP）的优势、类型和用法。使用 Destination Builder 创建和管理 Cookie、URL 或服务器到服务器目标。
seo-title: Destinations
solution: Audience Manager
title: 目标
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 20%

---

# [!UICONTROL Destinations] 概述 {#destinations}

在Audience Manager中， [!UICONTROL destination] 是任何協力廠商系統(廣告伺服器、 [!DNL DSP]、廣告網路等) 任何其他系统（广告服务器、DSP、广告网络等）。[!UICONTROL Destination Builder] 是您用來建立及管理的工具 [!UICONTROL cookie]， [!DNL URL]，或 [!UICONTROL server-to-server destinations].

## 用途與優點 {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 和 [!UICONTROL Destination Builder] 可讓您建立 [!UICONTROL destinations] 並將分段使用者的相關資訊傳送給您的資料合作夥伴。 這可協助您：

* **Protect資料值：** 不要將所有使用者資料傳送至 [!UICONTROL destination]， [!UICONTROL Destination Builder] 僅可讓您共用合格使用者的特定資訊。
* **對您的資料採取行動：** 傳送資料至 [!UICONTROL destination] 合作夥伴可協助他們快速開發及鎖定合格的受眾區段。
* **減少技術上的額外負荷：** 業務使用者可以設定 [!UICONTROL destinations] 安全地在 [!UICONTROL Destination Builder] 介面。 這有助於縮短部署前測試所需的時間。 替換為 [!UICONTROL Destination Builder]，即可建立、管理和刪除 [!UICONTROL destinations] 隨著您的業務需求改變，不必經過漫長的開發週期。

## 技术考虑事项 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

資料傳送取決於您的資料合作夥伴想要或能夠接收的方式 [!UICONTROL destination] 資訊。 技術或工程限制可能會導致 [!UICONTROL destination] 透過接收資料 [!DNL URL]， [!UICONTROL cookie]，或 [!UICONTROL server-to-server] 程式。 請與您的協力廠商合作夥伴合作，決定他們可以使用哪種方法。

## 业务考虑事项 {#business-considerations}

選擇一種傳送方法而非另一種傳送方法的業務決策，取決於您的技術能力 [!UICONTROL destination] 合作夥伴以及您想要使用合格使用者資訊執行的動作。 例如，技術限制可限制您的選項，如果 [!UICONTROL destination] 無法透過特定傳遞方式接收資料。 不過，如果沒有技術問題，您可以根據要如何對該資料採取行動來傳送資訊。 例如：

* [!DNL URL]s和 [!UICONTROL cookie-based destinations] 與頁面上的使用者動作幾乎同步運作。
* [!UICONTROL Server-to-server] 方法有助於隨著時間建立深層受眾區段。

## [!UICONTROL Destination] 型別和一般用途 {#destination-types}

下表中的範例可協助您瞭解何時應使用特定 [!UICONTROL destination] 以及每種型別之間的差異。

| [!UICONTROL Destination] 键入 | 通常用於 | 示例 | 注意事项 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 您需要傳送資料至其他Adobe Experience Cloud解決方案。 | 傳送資料至Adobe Analytics。 |  |
| **[!UICONTROL People-Based Destinations]** | 您需要將受眾區段傳送至以人物為基礎的環境，例如Facebook。 | 根據現有客戶的購買記錄，為其提供個人化優惠方案 | 對象鎖定目標會透過雜湊識別碼完成。 另請參閱 [以人物為基礎的目的地](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**伺服器對伺服器**) | <ul><li>不需要立即傳輸資料。</li><li>收集資料以建立龐大的合格使用者受眾集區。</li></ul> | 隨著時間（小時或天）收集資料，以便用於設為稍後日期執行的行銷活動。 | <ul><li>傳輸新的和先前的網站訪客資料。 </li><li>訪客不需要再次出現，即可符合其他區段的資格。</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** 或 **Cookie**) | 您需要立即傳輸資料，以便目的地可以立即對合格使用者採取行動。 | 從票證購買網站傳送資料。 使用 [!UICONTROL URL] 或 [!UICONTROL cookie destination] 以符合使用者資格並立即重新鎖定目標。 | <ul><li>僅傳輸新訪客的相關資料。 </li><li>訪客必須再次出現，才符合區段的資格。</li></ul> |
