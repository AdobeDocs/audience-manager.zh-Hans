---
description: 使用以人物為基礎的目的地，將第一方對象區段傳送至以人物為基礎的環境。 這些環境是屬於一個實體的封閉式生態系統，該實體控制其中顯示的內容。 其中包括Facebook等社交平台，以及其他依賴客戶帳戶個人化顯示內容的平台。
seo-description: Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content.
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: 概述和用例
feature: People-based Destinations
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: ab3361a0a54a7200d2f0c03a82ae6ef61a755be9
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 1%

---

# 概述和用例 {#overview-use-cases}

使用 [!DNL People-Based Destinations] 將第一方對象區段傳送至以人物為基礎的環境。 這些環境是屬於一個實體的封閉式生態系統，該實體控制其中顯示的內容。 其中包含社交平台，例如 [!DNL Facebook]以及依賴客戶帳戶來個人化顯示內容的其他平台。

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 本文不包含任何法律建議。 請諮詢您自己的法律顧問，以獲得法律指引。

## 概述 {#overview}

[!DNL People-Based Destinations] 可讓您對線上和離線資料套用細分，以根據 [雜湊識別碼](people-based-destinations-prerequisites.md#hashing-requirements)，例如電子郵件地址。 然後，您可以將這些區段傳送至「圍牆花園」，例如 [!DNL Facebook]，您可藉此在社交平台上鎖定對象。 [!DNL People-Based Destinations] 可幫助您：

* 定位平台中的離線和線上對象，例如 [!DNL Facebook]，根據雜湊電子郵件地址；
* 補充Audience Manager的現有裝置和Cookie鎖定目標功能；
* 消除與協力廠商資料上線解決方案相關的成本；
* 消除開發自訂資料上線工作流程的相關成本；
* 在無Cookie的環境中鎖定對象；
* 刪除與客戶ID相符的雜湊電子郵件地址，以鎖定對象。

您可以使用 [!DNL People-Based Destinations] 將可能未造訪過您網站的高價值客戶分段並鎖定目標，或停止鎖定已離線轉換的高價值客戶。 此外，您也可以善用 [!DNL Profile Merge Rules] 將離線第一方資料與線上第一方資料(包括其他Adobe Experience Cloud解決方案的客戶資料)結合，以最佳化您的社群媒體廣告工作。

![pbd-overview](assets/pbd-overview.png)

## 可用性 {#availability}

[!DNL People-Based Destinations] 是進階的Audience Manager整合。 請聯絡您的Adobe代表以使用此進階功能。

## 為何應使用 [!UICONTROL People-Based Destinations] {#why-use}

**從Audience Manager內管理整個對象細分，為客戶提供一致的跨頻道體驗。**

若未透過Audience Manager在以人物為基礎的管道中啟用對象區段，會導致客戶造訪您的網站時看到的內容與在其網站中看到的內容之間出現脫節的體驗，例如 [!DNL Facebook] 摘要。 跨頻道保持一致的目標定位，可增加廣告收入，同時最佳化廣告支出。

**無需專用的資料上線解決方案或自訂工作流程，即可透過以人物為基礎的管道觸及對象，進而傳送對象。**

在跨以人物為基礎的管道中鎖定受眾的較為「傳統」的方式包括，您必須以您要在其上廣告的平台所接受的格式匯出客戶資料，然後使用平台的專用資料上線方法將客戶資料帶至您的廣告商帳戶。 這是您需要針對每個要廣告的平台執行的所有手動工作。 此外，不同的平台可能有不同的資料格式要求，使得程式更加繁瑣。

![pbd-overview](assets/pbd-diagram.png)

到 [!DNL People-Based Destinations]，Audience Manager可協助您集中客戶資料、建立受眾區段，並在多個以人物為基礎的管道中啟用這些資料。 您可以透過Audience Manager使用者介面完成上述操作，避免手動將資料上傳至每個平台的額外工作，為您節省在此過程中寶貴的時間。

**從純粹的離線設定檔建立及啟用對象區段。**

[!DNL People-Based Destinations] 解決先前只能根據裝置活動啟用受眾區段的問題。 替換為 [!DNL People-Based Destinations]，您可從自己的純離線資料建立區段 [!DNL CRM]，並在以人物為基礎的平台上啟用這些功能。 此外，您也可以將離線資料與Audience Manager中已擁有的裝置資料建立關聯。

**運用Audience Manager的資料控管和隱私權控制，安全地處理客戶資料。**

[!DNL People-Based Destinations] 要求您僅使用無法還原的雜湊識別碼。 這樣就能減少手動將客戶資料上傳至每個目的地平台的相關風險。

觀看以下影片，概略瞭解使用時的資料流程 [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## 用例 {#use-cases}

協助您更清楚瞭解應該如何及何時使用 [!DNL People-Based Destinations]，以下是兩個範例使用案例，Audience Manager客戶可使用此功能加以解決。

### 使用案例#1 {#use-case-1}

線上零售商想要透過社交平台觸及現有客戶，並根據他們先前的訂單向他們顯示個人化優惠。 替換為 [!DNL People-Based Destinations]，線上零售商可從自己的網站擷取雜湊電子郵件地址 [!DNL CRM] 若要Audience Manager，請從自己的離線資料建立區段，並將這些區段傳送至他們想要廣告的社交平台，以最佳化他們的廣告支出。

### 使用案例#2 {#use-case-2}

航空公司有不同的客戶層級（銅級、銀級和金級），並希望透過社交平台為每個層級提供個人化優惠。 公司使用Audience Manager來分析網站上的客戶活動。 不過，並非所有客戶都使用航空公司的行動應用程式，其中有些客戶尚未登入公司網站。 公司對這些客戶擁有的唯一識別碼是會員ID和電子郵件地址。

若要在社群媒體和類似的以人物為基礎的頻道中鎖定他們，他們可以從他們的網站載入客戶資料 [!DNL CRM] Audience Manager，使用雜湊電子郵件地址做為識別碼。

接著，他們可以結合離線資料與現有的線上活動特徵，建立新的受眾區段，並透過這些區段鎖定目標 [!DNL People-Based Destinations].
