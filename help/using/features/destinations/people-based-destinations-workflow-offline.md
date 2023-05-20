---
description: 此頁面包含如何從僅限離線使用的客戶資料建立對象區段，並傳送至People-Based Destinations的逐步指南。
seo-description: This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.
seo-title: Workflow B - Personalization Based on Offline-Only Data
solution: Audience Manager
title: 工作流程 B - 基于仅离线数据进行个性化
feature: People-based Destinations
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
source-git-commit: 87c3169083f0dc66490e6a8c808e16371f1d78c0
workflow-type: tm+mt
source-wordcount: '1143'
ht-degree: 6%

---

# 工作流程 B - 基于仅离线数据进行个性化 {#workflow-b}

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 本文不包含任何法律建議。 請諮詢您自己的法律顧問，以獲得法律指引。

此頁面包含如何從僅限離線使用的客戶資料建立對象區段，並傳送至People-Based Destinations的逐步指南。

## 步驟1 — 上線離線特徵 {#step-1-onboard-traits}

在此案例中建立受眾區段的第一步，是將您的離線客戶資料帶入Audience Manager。

>[!IMPORTANT]
>
> 在繼續之前，請確定您即將上線的客戶活動已定義在與對應的Audience Manager中 [已上線的特徵](../traits/trait-and-segment-qualification-reference.md).

無論您現有的Audience Manager客戶ID為([DPUUID](../../reference/ids-in-aam.md))是否為雜湊電子郵件，您必須對包含下列專案的資料來源執行特徵上線： [DPUUID](../../reference/ids-in-aam.md).

### 示例

您想要確認下表中的客戶ID是否符合對應的已上線特徵ID。 讓我們考慮您的 [DPUUID](../../reference/ids-in-aam.md) 會儲存在ID為999999的資料來源中，而您的Audience Manager資料來源ID為123。

| 客戶ID (DPUUID) | 已上線特徵ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />

若要讓上述範例中的客戶ID符合對應已上線特徵的資格，您必須上傳 [傳入資料檔案](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) 包含下列內容：

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

檔案名稱如下所示： `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
另請參閱 [傳入資料檔案的Amazon S3名稱和檔案大小要求](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) 檔案名稱結構的詳細資訊。

## 步驟2 — 設定資料來源設定 {#configure-data-source-settings}

視您的 [DPUUID](../../reference/ids-in-aam.md) 如果是小寫、雜湊的電子郵件地址，您可能需要設定將儲存雜湊電子郵件地址的資料來源。

 

**案例1：您的 [DPUUID](../../reference/ids-in-aam.md) 已經是小寫、雜湊的電子郵件地址。**

在此情況下，您需要將對應的資料來源標示為：

1. 前往 **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**.
1. 尋找包含下列專案的資料來源： [DPUUID](../../reference/ids-in-aam.md)，然後按一下。
1. 確認選項 **[!UICONTROL Cannot be tied to personally identifiable information]** 未勾選。
1. 儲存資料來源設定。

 

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

## 步驟3 — 透過檔案式ID同步將DPUUID與雜湊電子郵件地址進行比對 {#match-ids-emails}

>[!IMPORTANT]
>
> 此步驟僅適用於 [案例2](people-based-destinations-workflow-offline.md#configure-data-source-settings) 如上所述。 如果您現有的 [DPUUID](../../reference/ids-in-aam.md) 是已經雜湊的電子郵件地址，請跳至 [步驟4 — 建立區段的設定檔合併規則](#create-profile-merge-rule).

假設您想要比對現有的 [DPUUID](../../reference/ids-in-aam.md) 從步驟1的範例到下表（右欄）中的雜湊電子郵件地址，並將雜湊電子郵件地址儲存在您建立的新資料來源中 [步驟2 — 設定資料來源設定](#configure-data-source-settings).

提醒您，您現在有兩個資料來源：

| 資料來源ID | 資料來源內容 |
| -------------- | -------------------------- |
| 999999 | 現有DPUUID (CRM ID) |
| 987654 | 雜湊電子郵件地址 |

| DPUUID (CRM ID) | 电子邮件地址 | 雜湊電子郵件地址 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

在我們的範例中，您的 [ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 會包含下列內容：

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

此 [ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 必須遵循此命名結構：

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

在上述範例中，檔案名稱看起來像這樣：
`c2c_id_999999_987654_1560431657.sync`

[在這裡下載範例檔案](assets/c2c_id_999999_987654_1560431657.sync).

建立ID同步檔案後，您需要將其上傳至 [!DNL Amazon S3] 貯體。 若要瞭解如何上傳ID同步檔案，請參閱 [將批次資料傳送至Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## 步驟4 — 建立區段的設定檔合併規則 {#create-profile-merge-rule}

下一步是建立新的合併規則，協助您建立要傳送至 [!DNL People-Based Destinations].

1. 登入您的Audience Manager帳戶並前往 **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. 单击 [!UICONTROL Add New Rule].
3. 輸入設定檔合併規則 **[!UICONTROL Name]** 和 **[!UICONTROL Description]**.
4. 在 **[!UICONTROL Profile Merge Rule Setup]** 區段，選取 **[!UICONTROL All Cross-Device Profiles]** 規則來自 **[!UICONTROL Cross-Device Options]** 清單。
5. 在 **[!UICONTROL Cross-Device Profile Options]** 清單中，選取您的特徵要據以上線的資料來源。
   ![merge-rule-setup](assets/pbd-pmr.png)

## 步驟5 — 建立受眾區段 {#create-audience-segments}

若要從僅限離線資料建立新區段，請使用 [區段產生器](../segments/segment-builder.md) 並確保在建立區段時使用您在上一步中建立的新設定檔合併規則。

## 步驟6 — 設定以人物為基礎的平台驗證 {#configure-authentication}

1. 登入您的Audience Manager帳戶並前往 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. 如果您先前設定好與社交平台的整合，您應會看到此頁面中列出的整合。 否則，頁面會是空的。
   ![以人物為基礎的整合](assets/pbd-config.png)
1. 单击 **[!UICONTROL Add Account]**.
1. 使用 **[!UICONTROL People-Based Platform]** 下拉式功能表，以選取您要設定整合的平台。
   ![以人物為基礎的平台](assets/pbd-add.png)
1. 按一下 **[!UICONTROL Confirm]** 重新導向至所選平台的驗證頁面。
1. 在驗證您的Social Platform帳戶後，系統會將您重新導向至Audience Manager，您應可在其中檢視關聯的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下 **[!UICONTROL Confirm]**.
1. Audience Manager會在頁面頂端顯示通知，讓您知道帳戶是否已成功新增。 通知也可讓您新增連絡人電子郵件地址，以在Social平台驗證即將到期時接收通知。

>[!IMPORTANT]
>
>Audience Manager會透過在特定時間後過期的驗證權杖來處理與社交平台的整合。 如需如何續約過期權杖的詳細資訊，請參閱驗證權杖續約。

## 步驟7 — 建立以人物為基礎的目的地 {#create-destination}

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
1. 在 **[!UICONTROL Segment Mappings]** 區段，選取您要傳送至此目的地的區段。 這是您建立的區段 [步驟5 — 建立受眾區段](people-based-destinations-workflow-offline.md#create-audience-segments).
1. 儲存目的地。
