---
description: 本文說明如何從Audience Manager使用者介面設定新的以裝置為基礎的目的地。
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: 添加新的基于设备的目标
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 3%

---

# 添加新的基于设备的目标 {#add-new-device-based-destinations}

本文說明如何從Audience Manager使用者介面設定新的以裝置為基礎的目的地。

>[!IMPORTANT]
>
>目前，大部分以裝置為基礎的目的地不符合自助服務設定工作流程的資格。 如果目的地清單中未顯示您需要新增的以裝置為基礎的目的地，請聯絡您的Adobe顧問或客戶支援以尋求協助。

## 概述 {#overview}

新增以裝置為基礎之目的地的程式包含兩個主要步驟。 首先，您需要設定Audience Manager與目的地合作夥伴之間的整合。 完成此操作後，您可以建立新的以裝置為基礎的目的地。

## 先决条件 {#prerequisites}

使用整合平台建立第一個以裝置為基礎的目的地時，請聯絡Adobe諮詢或客戶服務，為您的帳戶啟用Audience Manager與整合平台之間的ID同步。 這是在Audience Manager和目的地平台之間正確同步所必需的。

## 步骤 1. 使用目的地平台進行驗證 {#step1}

建立以裝置為基礎的新目的地之前，您需要設定Audience Manager與目的地平台之間的整合。 以下是其操作方式：

1. 登入您的Audience Manager帳戶並前往 **[!DNL Administration > Integrated Accounts]**. 如果您先前設定好與目的地平台的整合，您應會看到此頁面中列出的整合。 否則，頁面會是空的。
1. 单击 **[!DNL Add Account]**.
1. 選取您要驗證的目的地平台，然後按一下 **[!DNL Confirm]** 重新導向至所選平台的驗證頁面。

   ![整合平台](assets/dbd-integrated-platforms.png)

1. 驗證目的地平台帳戶後，系統會將您重新導向至Audience Manager，您應可在其中檢視相關聯的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下 **[!DNL Confirm]**.

## 步骤 2. 建立以裝置為基礎的新目的地 {#step2}

設定完目的地平台整合後，您可以建立新的目的地。 以下是其操作方式：

>[!NOTE]
>
>您無法變更現有以裝置為基礎的目的地的名稱。 請務必提供有助於您正確識別目的地的名稱。

1. 登入您的Audience Manager帳戶，前往 **[!DNL Audience Data > Destinations]**，然後按一下 **[!DNL Create Destination]**.
1. 在 **[!DNL Basic Information]** 區段，輸入 **[!DNL Name]** 和 **[!DNL Description]** ，並使用下列清單中的設定：

   ![設定](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**：選取您要傳送受眾區段的目的地平台。
   * **[!DNL Account]**：選取與所選平台相關聯的所需廣告商帳戶。
1. 单击 **[!DNL Next]**.
1. 選擇 [資料匯出標籤](/help/using/features/data-export-controls.md#controls-labels) 要為此目的地設定的值。
1. 单击 **[!DNL Save]**.
1. 在 **[!DNL Segment Mappings]** 區段，選取您要傳送至此目的地的對象區段。
1. 儲存目的地。
