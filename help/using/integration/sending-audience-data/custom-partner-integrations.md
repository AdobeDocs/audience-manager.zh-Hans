---
description: 此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: 自定义合作伙伴集成
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 18%

---

# 自定义合作伙伴集成 {#custom-partner-integrations}

此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。

## oracleData Cloud {#oracle-data-cloud}

### 描述

Audience Manager 通过入站数据文件从 Oracle Data Cloud for Audience Marketplace 中提取 Cookie 和移动 ID 数据。下述自訂整合規格僅適用於包含行動ID （IDFA和Android裝置ID）的傳入資料檔案。

### 整合細節

從OracleData Cloud收到的傳入資料檔案與中所述的標準傳入檔案名稱語法不同 [傳入資料檔案的Amazon S3名稱和檔案大小要求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) 以及從中說明的標準傳入檔案內容語法 [傳入資料檔案內容：語法、無效字元、變數和範例](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

除了傳入資料檔案的標準實作欄位外，以下醒目提示的元素為必要專案。 如需所有其他標準欄位和檔案名稱元素的說明，請參閱上述兩個連結頁面中的檔案名稱語法和檔案內容語法。

### 檔案命名

ODC檔案名稱的結構為：

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

此 `odc` file name元素會將檔案識別為從Oracle資料雲端匯入，並指示Audience Manager傳入檔案驗證器照常處理。

### 檔案內容

ODC傳入資料檔案中的欄位必須以下列順序顯示：

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

此 `ID type` 可以是：

* IDFA
* Android裝置ID

>[!IMPORTANT]
>
>請勿在相同的傳入資料檔案中傳送IDFA和Android裝置ID。

## 範例ODC傳入檔案

下載 [範例檔案](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). 此檔案可讓特徵ID38838數符合數個IDFA的資格。 您可以在標準文字編輯器或程式碼編輯器中開啟此檔案。
