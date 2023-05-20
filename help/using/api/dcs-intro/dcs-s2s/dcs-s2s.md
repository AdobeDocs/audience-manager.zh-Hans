---
description: 伺服器對伺服器(S2S) API提供程式碼和方法，可讓您傳送和接收DCS使用者資料，並在您自己的系統或應用程式中使用此資訊。
seo-description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-title: DCS APIs for Server-to-Server Data Transfers
solution: Audience Manager
title: 用于服务器到服务器数据传输的 DCS API
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 10%

---

# 用于服务器到服务器数据传输的 DCS API{#dcs-apis-for-server-to-server-data-transfers}

伺服器對伺服器([!UICONTROL S2S]) [!DNL API]提供可讓您傳送及接收的程式碼和方法 [!DNL DCS] 使用者資料，並在您自己的系統或應用程式中使用此資訊。

## 常見使用案例 {#common-use-cases}

[!UICONTROL Server-to-server] 傳輸可協助您根據訪客興趣自訂登入頁面或其他互動。 常見的使用案例包括：

* 網站上的個人化：根據訪客所屬的區段動態新增相關內容和行動號召，以量身打造訪客在您網站上的體驗。
* 改善客戶服務：匯入 [!DNL Audience Manager] 將區段轉換為 [!DNL CRM] 或其他系統（透過伺服器對伺服器資料傳輸）。 此資料可提供電話服務或線上聊天操作員，並提供客戶的個人化相關資訊。

## 需求：使用者ID和地區伺服器名稱 {#requirements}

此 [!UICONTROL DCS API] 需要使用者ID和地區ID才能驗證及提出資料請求。

* 使用者ID為必要項，因為您必須將資料與特定訪客建立關聯。
* 區域ID必須將呼叫連結回伺服器名稱，而且使用者資料會儲存在地理位置上最接近網站訪客的資料中心。

## 入门指南 {#getting-started}

目前，本指南涵蓋如何：

* 從取得使用者和地區ID [!DNL DCS] 您可能已收到的檔案 [!DNL Audience Manager] 客戶。

* 如果您使用，請取得使用者和地區ID [!DNL Visitor ID Service].
* 呼叫 [!DNL DCS] 在您擁有使用者和地區ID之後。

我們會在新方法可用時加以新增。 請參閱下列章節以開始使用。

* [从 DCS 响应中获取用户 ID 和区域](dcs-aam-ids.md)
* [透過Experience CloudID取得使用者ID和地區……](dcs-mcid-ids.md)
* [进行服务器到服务器 DCS API 调用](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS API 参考](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

