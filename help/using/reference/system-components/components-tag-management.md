---
description: Audience Manager標籤管理元件包括使用者端入口網站、Adobe Tag Manager (已取代並改用Adobe Experience Platform Launch)、DIL、Akamai和控制資料庫。
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: 标记管理组件
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 3%

---

# 标记管理组件{#tag-management-components}

Audience Manager標籤管理元件包括使用者端入口網站、Adobe Tag Manager (已棄用，改為Adobe Experience Platform標籤)、DIL、Akamai和控制資料庫。

<!-- 

c_comptag.xml

 -->

Audience Manager包含下列元件：

* [使用者端入口網站](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM容器](../../reference/system-components/components-tag-management.md#dil-tim)
* [Data Information Library (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [控制項資料庫](../../reference/system-components/components-tag-management.md#control-database)

## 使用者端入口網站 {#client-portal}

使用者端入口網站是標籤和資料管理的主要使用者介面(UI)。 客戶可使用此入口網站處理標籤、建立特徵和區段、設定目的地，以及使用報告監控行銷活動績效。

## DIL/TIM容器 {#dil-tim}

此 [!UICONTROL DIL] 容器協助部署 [!DNL Audience Manager] 資料收集程式碼至您的網站。 [!UICONTROL TIM] 是已過時的標籤插入管理員。 不再由使用 [!DNL Audience Manager]. 您改為使用 [!DNL Audience Manager] 中的擴充功能 [Adobe Experience Platform標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) 以設定並產生您放置在詳細目錄頁面上的貨櫃代碼。

## 数据集成库 (DIL) {#dil}

此 [資料資訊庫](../../dil/dil-overview.md) (DIL)是獨立的API模組，可從您的網站收集資料。 [!UICONTROL DIL] 協助您免除撰寫特殊程式碼以進行資料收集、整合、讀取Cookie值及復原頁面資料的需求。 [!UICONTROL DIL] 會自動執行這些動作。 此外， [!UICONTROL DIL] 精簡。 這是獨立的程式碼程式庫，有助於減少收集資訊所需的程式碼數量。 最後， [!UICONTROL DIL] 協助您整合 [!DNL Audience Manager] 與其他產品一起使用 [!DNL Adobe] Experience Cloud。

## Akamai {#akamai}

[!DNL Audience Manager] 使用 [Akamai](https://www.akamai.com/us/en/about/) 從我們自己的標籤管理平台(稱為 [!UICONTROL TIM (Tag Insertion Manager)]. 不過，使用部署程式碼 [!UICONTROL TIM] 已逐步淘汰，改為 [!DNL Adobe Experience Platform Tags].

## 控制項資料庫 {#control-database}

控制項資料庫：

* 處理來自入口網站的使用者端輸入（例如，建立特徵和目的地）。
* 將資料傳輸至Akamai，其中包括用來建置容器範本和目的地發佈iFrame的資料。
* 傳回UI報表系統的資料。
