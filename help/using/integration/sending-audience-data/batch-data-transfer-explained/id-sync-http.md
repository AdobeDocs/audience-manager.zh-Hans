---
description: 說明用於初始HTTP呼叫中的語法和引數，以便在廠商和Audience Manager之間同步使用者ID。 ID同步可在您將資料分類法傳送至Audience Manager後開始。
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between a vendor and Audience Manager. ID synchronization can begin after you send your data taxonomy to Audience Manager.
seo-title: ID Synchronization for Inbound Data Transfers
solution: Audience Manager
title: 用于入站数据传输的 ID 同步
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Inbound Data Transfers
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 7%

---

# 用于入站数据传输的 ID 同步 {#id-synchronization-for-inbound-data-transfers}

說明初始程式碼中使用的語法和引數 `HTTP` 呼叫以在廠商和之間同步使用者ID [!DNL Audience Manager]. ID同步可在您將資料分類傳送至之後開始 [!DNL Audience Manager].

ID同步是內送、非同步資料傳輸程式的第一步。 在此步驟中， [!DNL Audience Manager] 和廠商會比較並比對各自網站訪客的ID。 例如， [!DNL Audience Manager] 客戶可透過ID 123認識使用者。 不過，您的資料合作夥伴可以使用ID 456識別此使用者。 同步化程式允許 [!DNL Audience Manager] 和資料供應商協調這些不同的ID，並識別其各自系統中的使用者。 完成後， [!DNL Audience Manager] 而您的協力廠商合作夥伴應該針對網路上的每個不重複使用者，提供對應的ID。

您可以使用下列方法將您的資料放入 [!DNL Audience Manager]：

* [ID同步HTTP要求](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [宣告ID事件](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [從電子郵件內嵌影像進行ID同步](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID同步 `HTTP` 請求 {#id-sync-http}

在ID交換中，正確格式化 [!DNL URL] 字串看起來應該像這樣：

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

此 [!DNL URL] 傳入ID同步呼叫的變數，如下表所述。

>[!NOTE]
>
>以實際引數值取代斜體內容。

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>內容提供者的唯一ID (指派者： <span class="keyword"> Audience Manager</span>)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>不重複使用者ID的URL （百分比）編碼表示法。 除了編碼保留的ASCII字元外，任何非ASCII字元都應根據UTF-8字元編碼表進行百分比編碼。 </p> <p>如需詳細資訊，請參閱 <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL線上編碼/解碼</a> 網站。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>含有巨集的編碼URL重新導向 <code> ${DD_UUID}</code> 內嵌在其中。 </p> <p>注意：僅在內容提供者起始呼叫時新增。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>可选。如果您使用 <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">適用於IAB TCF的Audience Manager外掛程式。</a></p> <p><code> gdpr</code> 可以為0 （GDPR不適用）或1 （GDPR適用）。 </p> <p> <b>注意：</b> 此引數只能搭配 <code>gdpr_consent</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>可选。如果您使用 <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">適用於IAB TCF的Audience Manager外掛程式。</a></p> <p><code>gdpr_consent</code> 是URL安全base64編碼GDPR同意字串(請參閱 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB規格</a>)。 </p> <p> <b>注意：</b> 此引數只能搭配 <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Event {#declared-id-event}

如需詳細資訊，請參閱 [宣告ID](../../../features/declared-ids.md).

## 從電子郵件內嵌影像進行ID同步 {#id-sync-email-image}

透過電子郵件影像比對ID的格式與上述相同。 但是請注意，必須啟用電子郵件中的影像才能使其運作。 這可能會影響透過電子郵件的ID同步，因為大多數郵件系統預設會停用影像。

>[!MORELIKETHIS]
>
>* [数据收集组件](../../../reference/system-components/components-data-collection.md)

