---
description: 在 Audience Manager 启用 Audience Optimization for Publishers 之前，您必须确保满足本文中列出的所有先决条件。检查所有先决条件后，请与客户关怀团队联系。
seo-description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-title: Import Google Ad Manager Data Files Into Audience Manager
solution: Audience Manager
title: 將Google Ad Manager資料檔案匯入Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization Reports
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
source-git-commit: 7147091e6c253e8124f5f21a2251c1a76ac9d808
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 13%

---

# 將Google Ad Manager （前身為DFP）資料檔案匯入Audience Manager{#import-dfp-data-files-into-audience-manager}

在 Audience Manager 启用 Audience Optimization for Publishers 之前，您必须确保满足本文中列出的所有先决条件。检查所有先决条件后，请与客户关怀团队联系。

## Google Ad Manager記錄擷取的先決條件 {#prereqs-dfp-ingestion}

請注意，必須完成本節中所述的程式 *早於* 接著會介紹啟用記錄擷取的先決條件。

為了使用 [!DNL Google Ad Manager] (前身為Google DFP)記錄檔 [!DNL Audience Manager]，您必須先將 [Audience Manager不重複使用者ID (UUID)](../../../reference/ids-in-aam.md) 在廣告標籤呼叫中。 如此一來，我們的ID便包含在 [!DNL Google Ad Manager] 記錄檔與我們可以比對ID [!DNL Google Ad Manager] 和 [!DNL Audience Manager]. 使用 [!DNL Audience Manager] [!UICONTROL DIL] 程式碼或 [!UICONTROL Audience Management Module] 以設定 [!DNL Audience Manager] 第一方Cookie中的UUID。

以下說明如何設定 [!DNL Audience Manager] 廣告標籤呼叫中的ID，如檔案所述：

* [透過Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [透過Cookie目的地](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

您需要設定 [!DNL Audience Manager] 自行識別，並搭配使用 [!DNL Audience Manager] 諮詢以檢查是否一切正常。 您已設定 [!DNL Audience Manager] ID正確，如果：

* `'aamid'` 是當作識別碼使用的金鑰。
* 使用者ID值的格式正確： [!DNL Audience Manager] UUID，如我們的 [Audience Manager內的ID索引](../../../reference/ids-in-aam.md).
* 您已包含 [!DNL Audience Manager] UUID位於「 」中定義的欄位 [!DNL Google Ad Manager] 記錄（例如CustomTargeting）。

## 啟用記錄擷取的先決條件 {#prereqs-ingestion-enablement}

<table id="table_C980A9F9B0FB4157B4908A64768B1571"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 步骤 </th> 
   <th colname="col2" class="entry"> 详细信息 </th> 
   <th colname="col3" class="entry"> 所有者 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>步骤 1 </p> </td> 
   <td colname="col2"> <p>確認設定 <span class="keyword"> Audience Manager</span> UUID （如上所述）已在移至步驟2前完成 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> 客戶服務或諮詢 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 2 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理員會建立： </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">用於將Google Ad Manager登入的服務帳戶 <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">新認證。 <p>注意：這可能會需要此專案專屬的唯一電子郵件地址，並在布建對Google儲存貯體的存取權時使用。 </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">私密金鑰（以JSON為基礎的認證） </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 3 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理員會授與服務帳戶的API存取權。 此步驟可讓您存取中繼資料，以描述維度（條列專案、訂單、創意）。 <p>注意：使用您在步驟2中設定的服務帳戶電子郵件存取權來授與存取API的許可權。 </p> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 4 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理員會建立Google儲存貯體的存取權。 請記住： </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">這可透過Google群組完成。 </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">將指派給服務帳戶的唯一電子郵件地址與儲存貯體建立關聯。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 5 </p> </td> 
   <td colname="col2"> <p>Google Ad Manager管理員會提供Google Ad Manager網路ID。 這可讓我們在呼叫API時傳入網路ID。 </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步骤 6 </p> </td> 
   <td colname="col2"> <p>依照詳細指示編譯先決條件並開啟支援服務單 <a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html">此處</a> 以啟動記錄擷取程式。 </p> </td> 
   <td colname="col3"> <p>您，或 <span class="keyword"> Audience Manager</span> 代表您諮詢 </p> </td> 
  </tr> 
 </tbody> 
</table>
