---
description: 此頁面包含如何結合已驗證身分的使用者的離線CRM資料和即時行為資料的逐步指南，以建立對象區段，然後將這些對象區段傳送至以人物為基礎的目的地。
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with real-time behavioral data for authenticated users to create audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow C - Personalization Based on Authenticated Activity Combined with Offline Data
solution: Audience Manager
title: 工作流程 C - 基于已验证活动和离线数据的组合进行个性化
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 5%

---

# 工作流程 C - 基于已验证活动和离线数据的组合进行个性化 {#workflow-c}

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 本文不包含任何法律建議。 請諮詢您自己的法律顧問，以獲得法律指引。

本頁包含如何合併離線檔案的逐步指引 [!DNL CRM] 已驗證身分的使用者使用即時行為資料建立受眾區段，然後將這些受眾區段傳送至 [!DNL People-Based Destinations].

## 步驟1 — 設定資料來源設定 {#configure-data-source-settings}

視您的 [DPUUID](../../reference/ids-in-aam.md) 如果是小寫、雜湊的電子郵件地址，您可能需要設定將儲存雜湊電子郵件地址的資料來源。

 

**案例1：您的 [DPUUID](../../reference/ids-in-aam.md) 已經是小寫、雜湊的電子郵件地址。**

在此情況下，請跳至 [步驟5 — 設定以人物為基礎的平台驗證](#configure-authentication).

 

**案例2：您的 [DPUUID](../../reference/ids-in-aam.md) 不是小寫、雜湊的電子郵件地址。**

在這種情況下，您需要建立新的跨裝置資料來源，以儲存雜湊的電子郵件地址。 以下是其操作方式：

1. 登入您的Audience Manager帳戶並前往 **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**，然後按一下 **[!UICONTROL Add New]**.
1. 輸入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** 新資料來源的ID。
1. 在 **[!UICONTROL ID Type]** 下拉式功能表，選取 **[!UICONTROL Cross Device]**.
1. 在 **[!UICONTROL Data Source Settings]** 區段，選取兩者 **[!UICONTROL Inbound]** 和 **[!UICONTROL Outbound]** 選項，並啟用 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 選項。
1. 使用下拉式功能表選取 **[!UICONTROL Emails(SHA256, lowercased)]** 此資料來源的標籤。
   >[!IMPORTANT]
   >
   >此選項只會將資料來源標籤為包含使用該特定演演算法雜湊的資料。 Audience Manager不會在此步驟將資料雜湊。 請確定您計畫儲存至此資料來源的電子郵件地址已使用 [!DNL SHA256] 演演算法。 否則，您將無法將其用於 [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 另請參閱 [資料上線](people-based-destinations-prerequisites.md#data-onboarding) 有關如何將離線資料帶入People-Based Destinations的Audience Manager的常見問題。

觀看以下影片，觀看如何建立的資料來源教學影片。 [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## 步驟2 — 透過即時HTTP呼叫，使用宣告ID來比對DPUUID與雜湊電子郵件地址 {#match-email-addresses}

若要讓已驗證身分的使用者符合規則型特徵的資格，您需要透過傳送特徵資格 [宣告ID](../declared-ids.md).

### 示例

假設您已建立下列兩個資料來源。

| 資料來源ID | 資料來源內容 |
| -------------- | -------------------------- |
| 999999 | 現有DPUUID (CRM ID) |
| 987654 | 雜湊電子郵件地址 |

 

然後，您想要讓下列CRM ID符合表格中的特徵。

| DPUUID (CRM ID) | 电子邮件地址 | 雜湊電子郵件地址 | 特征 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | 位置=美國 |

 

您宣告的ID應遵循下列語法：

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

在上述範例中，宣告ID呼叫看起來應該像這樣：

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## 步驟3 — 建立分段的設定檔合併規則 {#create-profile-merge-rule-segmentation}

下一步是建立新的合併規則，協助您建立要傳送至 [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>如果您已使用定義規則 **[!UICONTROL Current Authenticated Profiles]** 或 **[!UICONTROL Last Authenticated Profiles]** 選項，您可以跳至 [步驟4 — 建立受眾區段](#create-audience-segments).

1. 登入您的Audience Manager帳戶並前往 **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. 单击 **[!UICONTROL Add New Rule]**.
3. 輸入設定檔合併規則 **[!UICONTROL Name]** 和 **[!UICONTROL Description]**.
4. 在 **[!UICONTROL Profile Merge Rule Setup]** 區段，選取 **[!UICONTROL Current Authenticated Profiles]** 或 **[!UICONTROL Last Authenticated Profiles]** 規則來自 **[!UICONTROL Cross-Device Options]** 清單。
5. 在 **[!UICONTROL Cross-Device Profile Options]** 清單中，選取您要對其執行分段的資料來源。 這些應該是包含現有DPUUID的資料來源。
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## 步驟4 — 建立受眾區段 {#create-audience-segments}

若要建立新區段，請使用 [區段產生器](../segments/segment-builder.md). 如果您有想要傳送至的現有受眾區段 [!DNL People-Based Destinations]，跳至 [步驟5 — 設定以人物為基礎的平台驗證](#configure-authentication).

## 步驟5 — 設定以人物為基礎的平台驗證 {#configure-authentication}

1. 登入您的Audience Manager帳戶並前往 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. 如果您先前設定好與社交平台的整合，您應會看到此頁面中列出的整合。 否則，頁面會是空的。
   ![以人物為基礎的整合](assets/pbd-config.png)
2. 单击 **[!UICONTROL Add Account]**.
3. 使用 **[!UICONTROL People-Based Platform]** 下拉式功能表，以選取您要設定整合的平台。
   ![以人物為基礎的平台](assets/pbd-add.png)
4. 按一下 **[!UICONTROL Confirm]** 重新導向至所選平台的驗證頁面。
5. 在驗證您的Social Platform帳戶後，系統會將您重新導向至Audience Manager，您應可在其中檢視關聯的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下 **[!UICONTROL Confirm]**.
6. Audience Manager會在頁面頂端顯示通知，讓您知道帳戶是否已成功新增。 通知也可讓您新增連絡人電子郵件地址，以在Social平台驗證即將到期時接收通知。

>[!IMPORTANT]
>
>Audience Manager會透過在特定時間後過期的驗證權杖來處理與社交平台的整合。 如需如何續約過期權杖的詳細資訊，請參閱驗證權杖續約。

## 步驟6 — 建立以人物為基礎的目的地 {#create-destination}

1. 登入您的Audience Manager帳戶，前往 **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**，然後按一下 **[!UICONTROL Create Destination]**.
1. 在 **[!UICONTROL Basic Information]** 區段，輸入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** ，並使用下列設定：
   * **[!UICONTROL Category]**：整合平台；
   * **[!UICONTROL Type]**：以人物為基礎；
   * **[!UICONTROL Platform]**：選取您要傳送受眾區段的目標人物型平台；
   * **[!UICONTROL Account]**：選取與所選平台相關聯的所需廣告商帳戶。
      ![create-destination](assets/pbd-create-destination.png)
1. 单击 **[!UICONTROL Next]**.
1. 選擇 **[!UICONTROL Data Export Labels]** 要為此目的地設定的值。
1. 在 **[!UICONTROL Configuration]** 區段，選取包含雜湊資料來源的資料來源。
1. 在 **[!UICONTROL Segment Mappings]** 區段，選取您要傳送至此目的地的區段。 這是您建立的區段 [步驟4 — 建立受眾區段](#create-audience-segments).
1. 儲存目的地。
