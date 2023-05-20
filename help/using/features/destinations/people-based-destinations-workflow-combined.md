---
description: 此頁面包含如何結合離線CRM資料與您Audience Manager中已擁有的行為資料的逐步指南，以建立新的受眾區段，然後將這些受眾區段傳送至People-Based Destinations。
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow A - Personalization Based on All Online Activity Combined with Offline Data
solution: Audience Manager
title: 工作流程 A - 基于所有在线活动和离线数据的组合进行个性化
feature: People-based Destinations
exl-id: 1f906955-8fe7-4cce-95d6-0e4275d523e8
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 6%

---

# 工作流程 A - 基于所有在线活动和离线数据的组合进行个性化 {#workflow-a}

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 本文不包含任何法律建議。 請諮詢您自己的法律顧問，以獲得法律指引。

本頁包含如何合併離線檔案的逐步指引 [!DNL CRM] 包含您在Audience Manager中已有之行為資料的資料，以建立新的受眾區段，然後傳送這些受眾區段至 [!DNL People-Based Destinations].

## 步驟1 — 設定資料來源設定 {#configure-data-source-settings}

視您的 [DPUUID](../../reference/ids-in-aam.md) 如果是小寫、雜湊的電子郵件地址，您可能需要設定將儲存雜湊電子郵件地址的資料來源。

 

**案例1：您的 [DPUUID](../../reference/ids-in-aam.md) 已經是小寫、雜湊的電子郵件地址。**

在此情況下，您需要將對應的資料來源標示為：

1. 前往 [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. 找到包含 [ 宏 ](../../reference/ids-in-aam.md) 的数据源，然后单击它。
1. **[!UICONTROL ID Type]**&#x200B;在下拉菜单中，选择 **[!UICONTROL Cross Device]** 。
1. 请确保该选项 [!UICONTROL Cannot be tied to personally identifiable information] 处于未选中状态。
1. 在 &quot; **[!UICONTROL Data Source Settings]** &quot; 部分，选择 &quot;&quot; 和 **[!UICONTROL Outbound]** &quot;&quot; **[!UICONTROL Inbound]** 选项，然后启用 &quot; **[!UICONTROL Share associated cross-device IDs in people-based destinations]** &quot; 选项。
1. 使用下拉式功能表選取 **[!UICONTROL Emails(SHA256, lowercased)]** 此資料來源的標籤。
   >[!IMPORTANT]
   >
   >此選項只會將資料來源標籤為包含使用該特定演演算法雜湊的資料。 Audience Manager不會在此步驟將資料雜湊。 請確定您計畫儲存至此資料來源的電子郵件地址已使用 [!DNL SHA256] 演演算法。 否則，您將無法將其用於 [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. 儲存資料來源設定。

 

**案例2：您的 [DPUUID](../../reference/ids-in-aam.md) 不是小寫、雜湊的電子郵件地址。**

在這種情況下，您需要建立新的跨裝置資料來源，以儲存雜湊的電子郵件地址。 以下是其操作方式：

1. 登入您的Audience Manager帳戶並前往 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**，然後按一下 **[!UICONTROL Add New]**.
1. 輸入 [!UICONTROL Name] 和 [!UICONTROL Description] 新資料來源的ID。
1. 在 **[!UICONTROL ID Type]** 下拉式功能表，選取 **[!UICONTROL Cross Device]**.
1. 在 **[!UICONTROL Data Source Settings]** 區段，選取兩者 **[!UICONTROL Inbound]** 和 **[!UICONTROL Outbound]** 選項，並啟用 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 選項。
1. 使用下拉式功能表選取 **[!UICONTROL Emails(SHA256, lowercased)]** 此資料來源的標籤。
   >[!IMPORTANT]
   >
   >此選項只會將資料來源標籤為包含使用該特定演演算法雜湊的資料。 Audience Manager不會在此步驟將資料雜湊。 請確定您計畫儲存至此資料來源的電子郵件地址已使用 [!DNL SHA256] 演演算法。 否則，您將無法將其用於 [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. 儲存資料來源設定。

观看以下视频以了解如何创建数据源 [!UICONTROL People-Based Destinations] 的视频教程。

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> 有关如何将离线数据导入到基于人员的目标的 Audience Manager，请参阅 [ 数据 ](people-based-destinations-prerequisites.md#data-onboarding) 提示。

## 步骤 2-通过基于文件的 ID 同步将宏与散列的电子邮件地址匹配 {#match-ids-emails}

>[!IMPORTANT]
>
> 此步驟僅適用於 [案例2](people-based-destinations-workflow-combined.md#configure-data-source-settings) 如上所述。 如果您現有的 [DPUUID](../../reference/ids-in-aam.md) 是已經雜湊的電子郵件地址，請跳至 [步驟3 — 建立分段的設定檔合併規則](people-based-destinations-workflow-combined.md#create-merge-rule).

假設您想要比對現有的 [DPUUID](../../reference/ids-in-aam.md) 從下表（右欄）移至雜湊電子郵件地址，並將雜湊電子郵件地址儲存在您建立的新資料來源中 [步驟1 — 設定資料來源設定](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (CRM ID) | 电子邮件地址 | 雜湊電子郵件地址 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

您最多可以將10個雜湊電子郵件地址連結至單一 [DPUUID](../../reference/ids-in-aam.md). 为此，请将哈希电子邮件地址与同步文件中的 a `<TAB>` 分隔开。

在我们的示例中，现在您有两个数据源。

| 数据源 ID | 数据源内容 |
| -------------- | -------------------------- |
| 999999 | 現有DPUUID (CRM ID) |
| 987654 | 雜湊電子郵件地址 |

 

您的 [ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 會包含下列內容：

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

## 步驟3 — 建立分段的設定檔合併規則 {#create-merge-rule}

下一步是建立新的合併規則，協助您建立對象區段，以傳送至以人物為基礎的目的地。

>[!IMPORTANT]
>
> 如果您已使用定義規則 [!UICONTROL Current Authenticated Profiles] 或 [!UICONTROL Last Authenticated Profiles] 選項，您可以跳至 [步驟4 — 建立受眾區段](people-based-destinations-workflow-combined.md#create-audience-segments).

1. 登入您的Audience Manager帳戶並前往 **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. 单击 **[!UICONTROL Add New Rule]**.
1. 輸入設定檔合併規則 **[!UICONTROL Name]** 和 **[!UICONTROL Description]**.
1. 在 &quot; **[!UICONTROL Profile Merge Rule Setup]** &quot; 部分，选择 &quot;&quot; 或 **[!UICONTROL Last Authenticated Profiles]** &quot;&quot; **[!UICONTROL Current Authenticated Profiles]** 选项。
1. **[!UICONTROL Cross-Device Profile Options]**&#x200B;在列表中，选择要运行分段的数据源。这些是包含现有 [ 宏 ](../../reference/ids-in-aam.md) 的数据源。

## 步骤 4-创建受众区段 {#create-audience-segments}

若要建立新的受眾區段，請使用 [區段產生器](../segments/segment-builder.md). 如果您有想要傳送至的現有受眾區段 [!DNL People-Based Destinations]，跳至 [步驟5 — 設定以人物為基礎的平台驗證](people-based-destinations-workflow-combined.md#configure-authentication).

## 步驟5 — 設定以人物為基礎的平台驗證 {#configure-authentication}

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
>對象管理員會透過在特定時間後過期的驗證權杖來處理與社交平台的整合。 如需如何續約過期權杖的詳細資訊，請參閱驗證權杖續約。

## 步驟6 — 建立以人物為基礎的目的地 {#create-destination}

1. 登入您的Audience Manager帳戶，前往 **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**，然後按一下 **[!UICONTROL Create Destination]**.
1. 在 **[!UICONTROL Basic Information]** 區段，輸入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** ，並使用下列設定：
   * **[!UICONTROL Category]**：整合平台；
   * **[!UICONTROL Type]**：基于人员;
   * **[!UICONTROL Platform]**：选择要发送受众区段的基于人员的平台;
   * **[!UICONTROL Account]**：选择与选定的平台关联的所需广告商帐户。
      ![创建-目标](assets/pbd-create-destination.png)
1. 单击 **[!UICONTROL Next]**.
1. 選擇 **[!UICONTROL Data Export Labels]** 要為此目的地設定的值。
1. 在 **[!UICONTROL Configuration]** 區段，選取包含雜湊資料來源的資料來源。
1. 在 **[!UICONTROL Segment Mappings]** 區段，選取您要傳送至此目的地的區段。 這是您建立的區段 [步驟4 — 建立受眾區段](people-based-destinations-workflow-combined.md#create-audience-segments).
1. 儲存目的地。
