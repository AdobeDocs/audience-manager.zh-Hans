---
description: 合併規則選項可讓您控制Audience Manager用來劃分割槽段的資料型別。 合併規則可包含由設定檔連結裝置圖表和/或與Audience Manager整合的其他第三方裝置圖表提供者對應的裝置設定檔。 您最多可以建立4個設定檔合併規則。
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: 定义的配置文件合并规则选项
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 2%

---

# [!UICONTROL Profile Merge Rules] 已定義的選項 {#profile-merge-rule-options-defined}

此 [!UICONTROL profile merge rule] 選項可讓您控制資料型別 [!DNL Audience Manager] 使用進行分段。 A [!UICONTROL profile merge rule] 可以包含裝置設定檔的對應 [!UICONTROL Profile Link] 與整合的裝置圖表及/或其他協力廠商裝置圖表提供者 [!DNL Audience Manager]. 您最多可以建立4個 [!UICONTROL Profile Merge Rules]. 第四個 [!UICONTROL Profile Merge Rule] 僅適用於已購買 [!UICONTROL People-Based Destinations] 附加元件。

您建置 [!UICONTROL Profile Merge Rule] 從下列選項中進行選取，位於 [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] 選項概觀 {#overview}

[!UICONTROL Profile Merge Rules] 允許使用許多規則組合，每個都適合特定使用案例。 請參閱下表，瞭解何時使用每個規則組合的詳細資訊。

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | 可用性 | 評估型別 | [!UICONTROL Audience Lab] 支持 | 用例 |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | 所有客戶 | 即時和批次 | 是 | [裝置目標定位](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | 所有客戶 | 即時和批次 | 否 | [擴充的裝置鎖定目標](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | 所有客戶 | 僅限即時 | 否 | [共用裝置目標定位](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | 所有客戶 | 即時和批次 | 是 | [線上/離線鎖定目標](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | 所有客戶 | 即時和批次 | 是 | [跨裝置目標定位](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | 所有客戶 | 即時和批次 | 否 | [進階跨裝置目標定位](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | 不适用 | 專屬於 [以人物為基礎的目的地](../destinations/people-based-destinations-overview.md) 客戶 | 僅批次 | 否 | [以人物為基礎的目的地目標定位](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] 評估 {#segment-evaluation}

視您的 [!UICONTROL Profile Merge Rules] 設定， [!DNL Audience Manager] 可以執行 [!UICONTROL segment] 即時評估、批次評估或兩者兼而有之。

* 即時 [!UICONTROL segment] 評估需要 [!DNL DCS] 若要檢視訪客即時存取您的數位財產，以符合 [!UICONTROL segment].
* 批次 [!UICONTROL segment] 評估會針對先前符合資格的人員執行 [!UICONTROL traits].
* [!UICONTROL Profile Merge Rules] 同時支援即時和批次 [!UICONTROL segment] 評估會將即時訪客活動與先前符合資格的結合 [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] 報告延遲 {#reporting-latency}

即時 [!UICONTROL segment] 評估會立即反映在 [!UICONTROL Profile Merge Rules] 報表。

批次 [!UICONTROL segment] 評估最多可能需要24小時才能反映在 [設定檔合併規則報表](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

此 [!UICONTROL Cross-Device Options] 可讓您選取已驗證和未驗證的使用者，並利用其跨裝置設定檔進行細分。 這些選項可協助您識別並觸及共用裝置上的特定使用者。 如需匿名和已驗證使用者的詳細資訊，請參閱 [Audience Manager中的訪客驗證狀態](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 跨裝置選項 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 無跨裝置設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> 不要使用從已驗證身分的使用者收集的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 目前驗證的設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> 以在訪客已登入您的網站時讀取資料並將資料寫入已驗證的訪客資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 上次驗證的設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> 從上次登入裝置之使用者的已驗證設定檔讀取資料。 </p> <p>選取時， <span class="keyword"> Audience Manager</span> 如果使用者是匿名的，則不會將新特徵資料寫入已驗證的設定檔。 驗證後，新特徵資料會寫入使用者的已驗證設定檔中。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 所有跨裝置設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告訴Audience Manager從所有跨裝置設定檔讀取資料，無論驗證狀態為何。 此選項僅適用於已購買People-Based Destinations附加元件的Audience Manager客戶。</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

此 [!UICONTROL Cross-Device Profile Options] 列出您的 [!UICONTROL cross-device data sources]. 這些選項會使用您在建立 [!UICONTROL cross-device] [!UICONTROL data source] (請參閱 [建立跨裝置資料來源](merge-rules-start.md#create-data-source))。 您最多可以選取3個 [!UICONTROL cross-device data sources] 以搭配每個設定檔規則使用。 此 [!UICONTROL Authenticated Profile Options] 可供您選擇 **[!UICONTROL Current Authenticated Profiles]** 或 **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

此 [!UICONTROL Device Options] 可讓您選取 *`device profile`* 使用者 [!UICONTROL Profile Merge Rule]. 裝置設定檔建置來源： [!UICONTROL traits] 從匿名瀏覽活動收集。 至少， [!UICONTROL profile merge rule] 包含 [!UICONTROL authenticated option] 和 [!UICONTROL device option].

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 裝置選項 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 無裝置設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> 不要使用匿名設定檔中包含的特徵進行細分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 裝置設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> 使用匿名裝置設定檔進行分段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 設定檔連結裝置圖表</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> 從目前裝置和最多100部使用者已驗證的其他裝置讀取設定檔。 此裝置圖表是根據您自己的第一方資料建置，位於 <span class="keyword"> Audience Manager</span>. 它非常適合在其數位屬性中具有高驗證等級的客戶。 此 <span class="wintitle"> 設定檔連結</span> 裝置圖表會即時更新。 當您選取時，此選項可供使用 <b><span class="uicontrol"> 目前驗證的設定檔</span></b> 或 <b><span class="uicontrol"> 上次驗證的設定檔</span></b>. 使用此選項時，您只能選擇單一已驗證的設定檔(<span class="keyword"> Audience Manager</span> 會自動將其他變灰)。 另請參閱 <a href="profile-link-use-case.md"> 設定檔連結裝置圖表使用案例</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>協力廠商裝置圖表選項</b> （個人和家庭） </p> </td>
   <td colname="col2"> <p>這些選項可讓您根據協力廠商提供的裝置圖表技術建立合併規則。 協力廠商裝置圖表提供： </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 機率和/或確定性資料。 </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">個人或家庭層級的資料。 </li> 
     </ul> </p> <p>若要使用這些選項，您必須是已整合的裝置圖表提供者的客戶 <span class="keyword"> Audience Manager</span>. 如需詳細資訊或開始使用，請聯絡您的客戶經理。 </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

從其他自動建立的對象區段 [!DNL Experience Cloud] 解決方案，根據之外定義的合併規則 [!DNL Audience Manager]，會使用 [!UICONTROL External Merge Policy]. 例如，請參閱 [Audience Manager和Adobe Experience Platform之間的受眾共用](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [設定檔合併規則常見問題集](../../faq/faq-profile-merge.md)

