---
description: 您可以透過使用者端或伺服器端整合，將合格的區段傳送至Google Ad Manager。 以下列出這兩種方法的需求和相關資訊。
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: 使用Google發佈商代碼(GPT)傳送區段至Google Ad Manager的需求和方法
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# 使用Google發佈商代碼(GPT)傳送區段至Google Ad Manager的需求和方法 {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

您可以將合格的區段傳送至 [!DNL Google Ad Manager] （前身為DFP）透過使用者端或伺服器端整合提供。 以下列出這兩種方法的需求和相關資訊。

## 使用者端整合 {#client-side-integration}

若要進行使用者端整合，您需要設定 [!DNL GPT] Audience Manager中的目的地。 當您想要設定時，請考慮以下幾點 [!DNL GPT] 作為Audience Manager目的地：

* **新增 [!UICONTROL DIL]：** 部署 [!UICONTROL Data Integration Library (DIL)] 所有要鎖定的頁面上的程式碼。 [!UICONTROL DIL] 將Audience Manager區段資料和使用者ID寫入Cookie，以便 [!DNL GPT] 目標定位。

* **建立 [!UICONTROL Cookie Destination]：** [!DNL GPT] 必須設定為Audience Manager中以Cookie為基礎的目的地。

* **實作Cookie檢查程式碼：** 換行 [!DNL GPT] `.setTargeting` 我們建議的API方法 [Cookie檢查程式碼](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). 此程式碼會先尋找有效的AAM Cookie，然後再尋找 `.setTargeting` 叫用方法。

* **新增 `AamGpt` 函式：** 此 `AamGpt` 程式碼會從Audience ManagerCookie擷取資料並將其傳送到 [!DNL GPT]. 放置 [Google發佈商廣告的Audience Manager代碼](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`)在頁面頂端或內部 `<head>` 程式碼區塊。

   >[!NOTE]
   >
   >此 `AamGpt` 如果您使用自己的程式碼來讀取Audience ManagerCookie資料，則不需要使用函式。

* **傳送傳遞記錄至Audience Manager：** 如果您想要區段傳送報表（選用），請為Audience Manager提供包含曝光層級傳送資料的每日記錄。 資料可以是原始格式，但每筆記錄都必須包含Audience Manager `UUID`. Audience Manager可以透過以下方式取得或接收這些內容： [!DNL FTP].

### 只有合格的區段才會傳送至GPT

傳遞至的資料量 [!DNL GPT] 視特定使用者符合的區段數量而定。 例如，假設您設定100個Audience Manager區段。 如果網站訪客符合其中五個區段的資格，則系統只會將這五個區段傳送至 [!DNL GPT] （並非全部100個）。

>[!NOTE]
>
>您可以傳送的索引鍵值數目沒有限制，但 [!DNL Google] 請求 [!DNL URL] 對於可接受的字元數有限制。 另請參閱 [使用GPT設定目標定位和大小](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## 伺服器端整合 {#server-side-integration}

如果您想要設定伺服器端整合，請洽詢您的Audience Manager顧問或客戶服務 [!DNL Google Ad Manager]，使用 [!DNL GPT]. 您需要提供您的 [!DNL Google Ad Manager] 帳戶網路ID和對象連結ID。

>[!IMPORTANT]
>
>如果您的網頁執行 [Accelerated Media頁面](https://www.ampproject.org/) ([!DNL AMP])程式庫時，您必須使用伺服器端與Audience Manager整合。 如果您在 [!DNL AMP] 並與進行使用者端整合 [!DNL AMP]，您必須移轉至伺服器端整合。 請聯絡您的Audience Manager顧問或客戶服務，討論移轉事宜。

>[!MORELIKETHIS]
>
>* [GPT API參考指南](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

