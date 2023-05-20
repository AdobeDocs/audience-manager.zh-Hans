---
description: 「個人資料合併規則」選項可讓您根據業務需求或目標來擴大或收窄受眾對特定受眾的關注。 這些一般使用案例會探索如何使用可用選項，並為個人、家庭和跨裝置目標定位建立合併規則。
seo-description: Profile Merge Rules options let you expand or tighten audience focus on specific audiences based on business needs or goals. These general use cases explore how to use available options and create merge rules for individual, household, and cross-device targeting.
seo-title: General Use Cases for Profile Merge Rules
solution: Audience Manager
title: 配置文件合并规则的一般用例
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 2%

---

# 配置文件合并规则的一般用例 {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 選項可讓您根據業務需求或目標，擴大或收緊受眾對特定受眾的關注。 這些一般使用案例會探索如何使用可用選項，並為個人、家庭和跨裝置目標定位建立合併規則。 [!UICONTROL Profile Merge Rules] 使用即時和批次目的地。

>[!TIP]
>
>這些專案的定義和說明 [!UICONTROL Merge Rule] 設定，請參閱 [定義的設定檔合併規則選項](merge-rule-definitions.md).

## 裝置目標定位 {#device-personalization}

此情境適用於想針對Audience Manager中定義的對象區段評估單一裝置設定檔的行銷人員，目的是使用支援裝置ID的鎖定目標平台(DSP、站上個人化平台和其他以裝置為基礎的目標平台)，為裝置提供一致的體驗，而不考慮使用者驗證。

若要建立只鎖定裝置設定檔的規則，請選取 **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![僅限裝置](assets/device-only.png)

假設John擁有三部智慧型手機。 其中兩個是資料計畫A上的iPhone 7，其中一個是資料計畫B上的Samsung 。並未考慮在這三種裝置上的任何一種狀態，John的行動電信業者想要為他提供資料計畫升級，但僅針對在資料計畫A上執行的iPhone 7裝置。

藉由使用 **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** 規則， [!DNL Device 1] 和 [!DNL Device 3] 兩者都符合區段的資格，而裝置2則被忽略。

![僅限裝置](assets/device-management.png)

## 共用裝置目標定位 {#target-shared-devices}

假設John和他的妻子Jane使用相同的筆記型電腦造訪線上商店，並訂購各種商品。

John使用自己的帳戶預訂旅行票和特別優惠，而Jane則使用自己的帳戶購買音樂和電影。

商店的行銷團隊可以使用 **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** 以特定交易目標John和Jane的規則，且僅根據他們已驗證的活動。

![current-no-device](assets/current-no-device.png)

使用此規則時，Audience Manager會完全忽略裝置設定檔、讓John的CRM ID符合該區段的資格，並且不會讓Jane的CRM ID符合資格。

![共用裝置目標定位](assets/shared-device-targeting.png)

## 線上/離線鎖定目標 {#device-household-targeting}

此使用案例涵蓋家庭身分管理。 公司可使用「 」將單一裝置設定檔與在該裝置上驗證的最後一個設定檔合併 **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** 規則。

![last-device-profile](assets/last-device-profile.png)

假設一個區段是由年收入超過$100.000美元的家庭所組成，其中至少包含一個裝置，也就是 [!DNL iPhone 7] 於 [!DNL Data Plan B]. 我們有兩個家庭設定檔（跨裝置設定檔），每個設定檔都連結到兩個不同的裝置設定檔。 符合區段資格所需的特徵會分散在裝置和跨裝置設定檔中。

Audience Manager會合併每個裝置+跨裝置設定檔配對，以檢視合併的特徵集是否符合區段的資格。 由於Audience Manager會評估合併中包含的每個設定檔，因此裝置設定檔和家庭設定檔都可以分段。

裝置和家庭設定檔之間的連結可讓Audience Manager符合資格 [!DNL Household 2] 用於區段，但不適用於 [!DNL Household 1]. 從 [!DNL Household 2]，僅限 [!DNL Device 3] 符合區段的資格。 此 [!UICONTROL Profile Merge Rule] 已讓行銷人員傳送一致的行銷訊息給個別裝置([!DNL Device 3])和更廣泛的家庭([!DNL Household 2])。

![家庭管理](assets/household-management.png)

## 以人物為基礎的目的地目標定位 {#all-cross-device}

>[!IMPORTANT]
>
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 本文不包含任何法律建議。 請諮詢您自己的法律顧問，以獲得法律指引。

此鎖定目標案例僅適用於已購買 [!DNL People-Based Destinations] 附加元件。 此規則可讓行銷人員根據客戶自己的已驗證資料觸及客戶。

假設線上零售商想要透過社交平台觸及現有客戶，並根據他們先前的訂單向他們顯示個人化優惠。 替換為 [!UICONTROL People-Based Destinations]，則他們可從自己的網站擷取雜湊電子郵件地址 [!DNL CRM] 進入Audience Manager後，從離線資料建立區段，然後使用雜湊識別碼，將這些區段傳送至他們想要廣告的社交平台，以最佳化他們的廣告支出。

若要進一步瞭解此選項，請參閱 [以人物為基礎的目的地](../destinations/people-based-destinations-overview.md).

![所有跨裝置](assets/all-cross-device.png)

## 裝置圖表選項 {#device-graph-options}

選擇 [!UICONTROL device graph] 的選項 [!UICONTROL Profile Merge] 規則取決於您數位財產和業務目標的特定條件。 這些一般准則可協助您瞭解何時使用一種圖表型別與另一種圖表型別。 請注意，您必須與外部裝置圖表有合約關係才能使用這些選項。 請參閱下表，瞭解何時選擇裝置圖表選項的一般指引。 如需特定使用案例，請參閱 [設定檔連結裝置圖表使用案例](profile-link-use-case.md) 和 [外部裝置圖表使用案例](external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 裝置圖表型別 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 設定檔連結裝置圖表</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 設定檔合併</span> 使用建立的規則 <span class="wintitle"> 設定檔連結</span> 選項適用於下列情況： </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">具有高階客戶驗證的數位屬性。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">重點突出、觸及率較低的行銷活動。 此 <span class="wintitle"> 設定檔連結</span> 裝置圖表僅以確定性資料建置。 相對於未驗證的使用者和裝置集區，此裝置設定檔集區總是較小。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">客戶必須處於驗證狀態才能符合細分資格的使用案例。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部裝置圖表選項 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 設定檔合併</span> 使用與整合的任何外部裝置圖表建立的規則 <span class="keyword"> Audience Manager</span> 最適合： </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">具有低層級客戶驗證的數位屬性。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">廣泛、高觸及率的品牌行銷活動。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">客戶不需要處於驗證狀態就能符合細分資格的使用案例。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

觀看以下影片，概略瞭解可能的使用案例 [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [配置文件关联设备图用例](profile-link-use-case.md)
>* [外部设备图用例](external-graph-use-cases.md)
>* [設定檔合併規則常見問題集](../../faq/faq-profile-merge.md)

