---
description: 設定Google群組，將您的Google Campaign Manager資料檔案匯入Audience Manager。 本節中的內容總結了整合流程，並提供Google Campaign Manager資源的連結，以協助您開始使用。
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: 將Google Campaign Manager資料檔案匯入Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# 將Google Campaign Manager資料檔案匯入Audience Manager {#import-dcm-data-files-into-audience-manager}

設定 [!DNL Google] 群組，將您的 [!DNL Google Campaign Manager] 將資料檔案放入Audience Manager。 本節中的內容會概述整合程式，並提供您以下連結至 [!DNL Google Campaign Manager] 協助您開始使用的資源。

## 整合摘要

[!DNL Google Campaign Manager] 是 [!DNL Google] 推出的 [!DNL DoubleClick for Advertisers] (DFA) 的替代产品。與DFA類似， [!DNL Google Campaign Manager] 客戶可以在以下位置匯入、檢視和處理其資料： [!DNL Audience Manager]. 但是 [!DNL Audience Manager] 無法直接存取和匯入 [!UICONTROL Data Transfer] 和 [!UICONTROL Match Table] 檔案。 要导入这些文件，需要客户自行完成。

不過，此設定程式已完整記錄在 [按兩下Campaign Manager說明](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). 您也可以檢閱下列步驟以開始。

>[!CAUTION]
>
>[!DNL Google Campaign Manager] 資料檔案包含您所有廣告商或使用者端的資料。 如果您需要省略特定使用者端，則必須先編輯檔案，才能讓檔案可供使用 [!DNL Audience Manager].

## 資料傳輸頻率和可用性

[!DNL Audience Manager] 每天檢查並傳輸資料一次。 資料通常提供於 [!DNL Audience Manager] 24小時之後。

## 步骤

1. [创建群组](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   群組控制對您的存取權 [!DNL Google Campaign Manager] 資料。 最終，您將邀請並新增 [!DNL Audience Manager] 至此群組。

1. [驗證您的Google雲端儲存空間狀態](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google Cloud Storage包含資料貯體，其中儲存了 [!UICONTROL Data Transfer] 和 [!UICONTROL Match Tables]. 您需要設定貯體，或確認您的新群組有權存取現有的資料儲存貯體。

1. [取得資料檔案URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   使用您的 [!DNL Google Campaign Manager] 客戶經理或平台解決方案顧問。 它們會提供您資料檔案的URL。 [!DNL Google] 未來版本可能會變更貯體和檔案名稱的格式。 再次強調，請使用您的 [!DNL Google Campaign Manager] 客戶經理以確保您使用正確的格式。

1. [設定貯體許可權](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   此 [!DNL Cloud Storage Manager] 可讓您控制資料共用和貯體存取。 為群組提供儲存貯體的讀取存取權，該儲存貯體包含 [!UICONTROL Data Transfer] 和 [!UICONTROL Match Table] 檔案。

1. [設定資料共用](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   已共用 [!DNL Google Campaign Manager] 使用者ID會加密以保護隱私權。 加密會在您的資料傳輸檔案結尾新增2欄， `PartnerId1` 和 `PartnerId2`. 這些欄包含每個接收這些檔案之公司專屬的編碼使用者ID。

   作為獲授權的第三方， [!DNL Audience Manager] 可以接收 [!DNL Google Campaign Manager] 但無法解碼ID。 不過，在 [!DNL Audience Manager] 側邊，我們知道編碼ID和我們的ID如何相符。 這表示我們能夠以信賴度和正確性比對及同步使用者。

   >[!NOTE]
   >您無法匯入 [!DNL Google Campaign Manager] 檔案到 [!DNL Audience Manager] 如果您已與其他2個協力廠商合作夥伴共用資料。

1. 邀請 [!DNL Audience Manager] 以加入群組。

   建立群組並授予其資料儲存貯體存取權後，請邀請 [!DNL Audience Manager] 以加入群組。 傳送邀請電子郵件至dfaaam@adobe.com。 請務必加入步驟3中的資料檔案URL。 接受邀請後，我們的內部團隊將與您合作以驗證存取權。 1.設定兩個資料來源，用於 [!DNL Google Campaign Manager] 中的資料 [!DNL Audience Manager] 使用者介面。

   為資料來源命名 `Advertiser Analytics: DCM Platform` 和 `Advertiser Analytics: AAM+DCM Platform`. 在 [建立資料來源](../../../features/manage-datasources.md#create-data-source) 工作流程，將ID型別設為 `Cookie`. 與我們的內部團隊共用兩個新資料來源的ID。

1. 您可以輕鬆建立特徵，從 [!DNL Google Campaign Manager] 您匯入的檔案 [!DNL Audience Manager]. 另請參閱 [可操作的記錄檔](../../../integration/media-data-integration/actionable-log-files.md) 並詢問您的 [!DNL Audience Manager] 顧問或客戶服務人員，為您啟用此功能。
