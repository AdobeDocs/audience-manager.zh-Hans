---
description: People-Based Destinations將可共用對象的概念引入到Audience Manager中。 此量度可協助您瞭解Audience Manager可與目的地平台共用多少雜湊電子郵件地址。
seo-description: People-Based Destinations introduce the notion of Shareable Audiences to Audience Manager. This metric helps you understand how many of the hashed email addresses Audience Manager can share with the destination platform.
seo-title: Shareable Audiences
solution: Audience Manager
title: 可共享的受众
feature: People-based Destinations
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 1%

---

# 可共享的受众 {#shareable-audiences}

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 本文不包含任何法律建議。 請諮詢您自己的法律顧問，以獲得法律指引。

[!DNL People-Based Destinations] 帶來 [!DNL Shareable Audiences] 以Audience Manager。 此量度可協助您瞭解Audience Manager可與目的地平台共用多少雜湊電子郵件地址。

[!DNL Shareable Audiences] 是量度，可協助您解譯上下文中的受眾資料 [!DNL People-Based Destinations]. 您可在以下位置檢視此量度： [!UICONTROL Destinations] 頁面和 [!UICONTROL Segment] 頁面。

## 區段可共用的對象 {#segment-shareable-audiences}

此 [!DNL Segment Shareable Audience] 「區段」頁面中的量度會指出來自符合之資料來源的雜湊電子郵件地址數目 [DPUUID](../../reference/ids-in-aam.md)，在指定的回顧期間，只要已套用設定檔合併規則，該區段就符合定義的區段的資格，而且該Audience Manager可與目的地平台共用。

此量度有1天的回溯期。 這可協助您瞭解特定目的地中區段的受眾觸及率。

## 目的地可共用的對象 {#destination-shareable-audience}

此 [!DNL Destination Shareable Audience] 以人物為基礎的目的地頁面中的量度會指出來自符合之資料來源的雜湊電子郵件地址總數 [DPUUID](../../reference/ids-in-aam.md)，該Audience Manager可與目的地平台共用，從對應至該目的地的所有區段。

![可共用的對象](assets/dest-shareable-audiences.png)

此量度具有期限回顧期間。 這可協助您瞭解從雜湊電子郵件地址資料來源可觸及的受眾規模。

## 示例

Audience Manager客戶的資料來源為110,000 [DPUUID](../../reference/ids-in-aam.md) (CRM ID)。 他們將100,000個雜湊電子郵件地址擷取至Audience Manager，以搭配多個以人物為基礎的目的地使用，並針對CRM ID對100,000個雜湊電子郵件地址執行ID同步。 客戶可使用 [!DNL All Cross-Device Profiles] 合併規則以建立三個受眾區段：

* 母體數為10,000的區段A，已對應至目的地A；
* 人口數為20,000的區段B，已對應至目的地A；
* 人口數為50,000的區段C已對應至目的地B。

在此案例中：

* 區段A可共用的對象= 10,000；
* 區段B可共用對象= 20,000；
* 區段C可共用對象= 50,000；
* 目的地A可共用的對象=區段A可共用的對象+區段B可共用的對象= 30,000；
* 目的地B可共用對象=區段C可共用對象= 50,000。

![shareable-audiences-diagram](assets/shareable-audiences.png)

>[!NOTE]
>
>在上述範例中，這並不意味著三個區段中的所有80,000個雜湊電子郵件地址都與目的地平台中的現有帳戶相符。 這僅表示Audience Manager會將三個區段的雜湊識別碼傳送至其各自的目的地。 將受眾區段傳送至以人物為基礎的目的地時，會在合作夥伴端進行受眾比對。 目的地A最多可以有30,000個相符的使用者帳戶，而目的地B最多可以有50,000個相符的使用者帳戶，但是無法保證相符率。 Adobe無法存取合作夥伴特定量度。 另請參閱 [匹配率](../../faq/faq-people-based-destinations.md#match-rates) 以人物為基礎的目的地在匹配率中的可見性常見問題集。
