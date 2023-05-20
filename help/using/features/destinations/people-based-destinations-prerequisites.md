---
description: 請閱讀下文，概略瞭解您在註冊People-Based Destinations之前需要滿足的客戶需求。
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: 先决条件和注意事项
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: cd40e1e3cc2199d1937950934d674cfad301f3e8
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 3%

---

# 先决条件和注意事项 {#prerequisites-considerations}

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 本文不包含任何法律建議。 請諮詢您自己的法律顧問，以獲得法律指引。

請閱讀下文，概略瞭解註冊前需要滿足的客戶需求 [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> 在進入實作階段前，請先仔細閱讀本文。

## 正在註冊 [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] 是一項進階功能，可讓您透過在社交網路上透過自訂優惠方案或電子郵件行銷來鎖定您的對象，在以人物為基礎的環境中啟用第一方對象區段，藉此增強您的Audience Manager體驗。

請聯絡您的Adobe代表以使用此進階功能。

## 合作夥伴特定先決條件 {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

在您使用之前 [!UICONTROL People-Based Destinations] 傳送您的第一方對象 [!UICONTROL segments] 至 [!DNL Facebook]，確認您符合下列需求：

1. 您的 [!DNL Facebook] 使用者帳戶必須具備 **管理行銷活動** 已為您計畫使用的廣告帳戶啟用許可權。
2. 新增 **Adobe Experience Cloud** 商業帳戶，作為您的廣告合作夥伴 [!DNL Facebook Ad Account]. 使用 `business ID=206617933627973`。另請參閱 [新增合作夥伴至您的業務經理](https://www.facebook.com/business/help/1717412048538897) 以取得詳細資訊。
   >[!IMPORTANT]
   > 設定Adobe Experience Cloud的許可權時，您必須啟用 **管理行銷活動** 許可權。 [!UICONTROL People-Based Destinations] 集成要求具备此权限。
3. 閱讀並簽署 [!DNL Facebook Custom Audiences] 服務條款。 为此，请转到 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`，其中 `accountID` 是您的 [!DNL Facebook Ad Account ID]。

### [!DNL LinkedIn] {#linkedin}

在您使用之前 [!UICONTROL People-Based Destinations] 若要將您的第一方對象區段傳送至 [!DNL LinkedIn]，確定您的 [!DNL LinkedIn Campaign Manager] 帳戶具有 [!DNL Creative Manager] 或更高的許可權層級。

若要瞭解如何編輯您的 [!DNL LinkedIn Campaign Manager] 使用者許可權，請參閱 [新增、編輯和移除Advertising帳戶的使用者許可權](https://www.linkedin.com/help/lms/answer/5753) (位於LinkedIn檔案中)。

另請參閱 [瞭解及設定LinkedIn以人物為基礎的目的地](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) 以取得視訊指示。

### [!DNL Google Customer Match] {#gcm}

在您使用之前 [!UICONTROL People-Based Destinations] 若要將您的第一方對象區段傳送至 [!DNL Google Customer Match] 目的地，請務必閱讀並遵循Google的原則來使用 [!DNL Customer Match]，概述於 [Google支援檔案](https://support.google.com/google-ads/answer/6299717).

接下來，確定您的 [!DNL Google] 帳戶已設定為 [!DNL Standard] 或更高的許可權層級。 請參閱 [Google Ads檔案](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) 以取得詳細資訊。

Google會自動允許擁有符合規範帳戶的客戶列出。

## 数据载入 {#data-onboarding}

資料擷取 [!UICONTROL People-Based Destinations] 目前支援最多10個連結至一個客戶ID的雜湊電子郵件地址([!DNL CRM ID])，每次批次傳輸。 上傳連結至一個客戶ID的10個以上雜湊電子郵件地址會導致Audience Manager以無特定順序擷取其中10個。

在多次批次傳輸中上傳連結至一個客戶ID的10個以上的雜湊電子郵件地址，會導致Audience Manager保留最近新增的10個電子郵件地址。

## 数据隐私 {#data-privacy}

雖然 [!UICONTROL People-Based Destinations] 可讓您根據您所上傳的雜湊電子郵件地址來鎖定對象，但您仍不得將任何可直接識別的訪客資訊上傳至Audience Manager。 在資料上線階段，您必須確保您計畫使用的電子郵件地址已透過 [!DNL SHA256] 演演算法。 否則，您將無法在 [!UICONTROL People-Based Destinations].

## 資料雜湊與加密的比較 {#data-hashing-encryption}

加密是雙向功能。 任何加密的資訊也可以使用正確的解密金鑰解密。 在Audience Manager內容中加密資料會帶來嚴重風險，因為任何加密形式的個人識別資訊都可以解密。 與加密不同， [!UICONTROL People-Based Destinations] 適用於雜湊資料。

雜湊是單向函式，會加擾輸入以產生唯一的結果。 使用適當的雜湊演演算法，例如 [!DNL SHA256]，則無法反轉雜湊函式並顯示解擾資訊。 您即將加入Audience Manager的電子郵件地址必須使用 [!DNL SHA256] 演演算法。 如此一來，您可以確保沒有未雜湊的電子郵件地址會觸及Audience Manager。

## 雜湊需求 {#hashing-requirements}

對電子郵件地址進行雜湊處理時，請務必遵守下列要求：

* 修剪電子郵件字串中的所有前導和尾端空格；例如： `johndoe@example.com`，非 `<space>johndoe@example.com<space>`；
* 雜湊電子郵件字串時，請務必雜湊小寫字串；
   * 範例： `example@email.com`，非 `EXAMPLE@EMAIL.COM`；
* 請確定雜湊字串都是小寫
   * 範例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`，非 `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`；
* 請勿對字串加鹽。

觀看以下影片，瞭解的雜湊需求 [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud可讓您選擇透過以下方式雜湊客戶ID： [!DNL Adobe Experience Platform Identity Service (ECID)]. 另請參閱 [setCustomerIDs的SHA256雜湊支援](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) 有關如何使用ECID來雜湊客戶ID的詳細資訊。

## 取得使用者許可權 {#obtaining-user-permission}

從 [!UICONTROL People-Based Destinations] 可協助您在以人物為基礎的管道中啟用第一方對象資料，您有責任通知客戶，並取得客戶關於您如何將其資料用於廣告或其他目的的任何必要同意。

在您註冊之前 [!UICONTROL People-Based Destinations]，將客戶的資訊用於廣告用途前，請務必先取得客戶的同意。

如果您的客戶希望退出廣告行銷活動，請參閱 [選擇退出管理](../../overview/data-security-and-privacy/data-privacy-requests.md) 有關如何停止Audience Manager進一步收集資料的詳細資訊。

## 強制執行第一方資料啟用 {#enforcing-first-party-activation}

使用時 [!UICONTROL People-Based Destinations]，您只能使用第一方資料在以人物為基礎的管道中啟用對象區段。 您無法在以人物為基礎的管道中，使用任何第二方或第三方資料來啟用對象。

使用時 [!UICONTROL People-Based Destinations]，使用 [資料匯出控制](../data-export-controls.md) 標籤您的 [!UICONTROL data sources] 和 [!UICONTROL destinations] 根據目的地平台和資料提供者的准則和要求。

## 透過宣告ID目標定位將已驗證的雜湊ID上線 {#onboard-authenticated-declared-id}

有两种方法可以将离线数据载入 Audience Manager 以便用于 [!UICONTROL People-Based Destinations]。

* [傳送批次資料](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 以Audience Manager擷取雜湊電子郵件地址。 透過此方法，您可以選擇使用您電子郵件中的雜湊電子郵件地址， [!DNL CRM] 資料庫位於 [!UICONTROL People-Based Destinations]. 此外，使用此方法時，您也可以將雜湊電子郵件地址限定為 [已上線的特徵](../traits/trait-and-segment-qualification-reference.md).
* 使用 [宣告ID](../declared-ids.md) 在傳入已驗證的客戶ID時，宣告雜湊的電子郵件地址。 使用此方法時，Audience Manager代表您只傳送至 [!UICONTROL People-Based Destinations] 已進行線上驗證之使用者的雜湊電子郵件地址。 透過以人物為基礎的管道啟用的電子郵件地址只是宣告ID事件呼叫中的電子郵件地址。 與客戶ID相關聯的其他電子郵件地址不會即時傳送。
