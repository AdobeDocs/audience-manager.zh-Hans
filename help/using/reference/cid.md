---
description: 更新您的程式碼以使用d_cid或d_cid_ic，而非d_dpid和d_dpuuid。 DPID和DPUUID變數仍會繼續運作，但您應將其視為已棄用。 這包括沒有d_首碼的DPID和DPUUID變體。
seo-description: Update your code to use d_cid or d_cid_ic instead of d_dpid and d_dpuuid. The DPID and DPUUID variables will continue to work, but you should consider them deprecated. This includes DPID and DPUUID variants without the d_ prefix.
seo-title: CID Replaces DPID and DPUUID
solution: Audience Manager
title: CID 取代 DPID 和 DPUUID
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
feature: Reference
exl-id: 18e6b1db-fe51-4560-9458-8d65474d2506
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 4%

---

# CID 取代 DPID 和 DPUUID{#cid-replaces-dpid-and-dpuuid}

更新您的程式碼以使用 `d_cid` 或 `d_cid_ic` 而非 `d_dpid` 和 `d_dpuuid`. DPID和DPUUID變數仍會繼續運作，但您應將其視為已棄用。 這包含不具下列專案的DPID和DPUUID變體： `d_ prefix`.

## DPID和DPUUID：評論 {#dpid-dpuuid-review}

DPID和DPUUID是包含資料提供者ID和使用者ID的機碼值組。 這些機碼值組會將提供者ID連結至使用者ID。 它們會在事件呼叫期間、傳入同步事件和ID呼叫時傳送資料。 沒有它們， [!DNL Audience Manager]和其他服務或功能無法比對和同步ID。 這些變數有時會有或不有 `d_` 前置詞如下所示。 注意，在程式碼中， *斜體* 表示變數預留位置。

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 语法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>資料提供者ID (DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_dpid=<i>data provider ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>data provider ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>資料提供者不重複使用者ID (DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_dpuuid=<i>data provider unique user ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=<i>data provider unique user ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

這些機碼值組仍然有效，但已過時。 您應該更新程式碼以改用CID或CID_IC。

## CID和CID_IC：關於 {#cid-cidic-about}

CID和CID_IC索引鍵值配對會取代DPID和DPUUID。 它們提供與DPID和DPUUID相同的功能，但效率較高，因為它們將資料提供者ID （或整合代碼）和使用者ID包含在單一索引鍵/值組中。 在每個索引鍵/值組中：

* =符號會將金鑰與其相關值分開。
* 非列印ASCII字元%01會分隔值。

`d_cid` 和 `d_cid_ic` 使用下列語法。 注意，在程式碼中， *斜體* 表示變數預留位置。

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 语法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>客戶ID (CID) </p> </td> 
   <td colname="col2"> <p> <code>d_cid=<i>data provider ID</i>%01<i>user ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>客戶ID整合代碼(CID_IC) </p> </td> 
   <td colname="col2"> <p> <code>d_cid_ic=<i>integration code</i>%01<i>user ID</i></code> </p> <p> 一個 <span class="term"> 整合程式碼</span> 是您可用來代替資料來源ID的備用ID，指派者為 <span class="keyword"> Audience Manager</span>. 另請參閱 <a href="../features/manage-datasources.md#create-data-source"> 建立資料來源</a> 如果您需要設定整合程式碼。 </p> </td> 
  </tr> 
 </tbody> 
</table>

另請參閱 [宣告ID的URL變數和語法](../features/declared-ids.md#variables-and-syntax).

>[!NOTE]
>
>您可以將整合程式碼用於您自己的資料來源和全域 [共用資料來源](../features/datasources-list-and-settings.md#settings-menu-options)，您可存取此專案。 例如，使用行動識別碼資料來源時，可以使用整合代碼。 請使用下列整合程式碼，與以下指定完全一致：

* **DSID_20914** 對於GAID，代表執行Android作業系統的裝置。
* **DSID_20915** 對於IDFA，代表執行iOS作業系統的裝置。

**示例**

下表提供依事件型別的範例。

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 事件类型 </th> 
   <th colname="col2" class="entry"> 示例 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Event </p> </td> 
   <td colname="col2"> 
    <ul id="ul_6EAB4188C6954512A28D1A8328794BCB"> 
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">新增了: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">已弃用: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>傳入同步(IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">新增了: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">已弃用: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>產生Audience ManagerUUID (ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">新增了: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">已弃用: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

每個呼叫也可包含多個 `d_cid` 和 `d_cid_ic` 索引鍵值配對，如下所示：

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## 開發團隊的重要考量 {#dev-considerations}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>项目 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>URL編碼 </p> </td> 
   <td colname="col2"> <p>您的開發團隊 <i>必須</i> 將URL編碼套用至CID機碼值組中的下列變數： </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> user ID</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>注意：您必須URL編碼使用者ID和整合代碼 <i>早於</i> 將它們串聯為字串。 這是因為URL編碼中不能擷取分隔兩個變數的ASCII字元%01。 </p> </p> <p>URL編碼可確保包含保留或不安全字元（例如但不限於、+或=）的使用者ID和整合程式碼，正確傳輸至我們的伺服器。 </p> <p>使用 <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> ASCII編碼表格</a> 以供參考。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用全域共用資料來源的整合代碼 </p> </td> 
   <td colname="col2"> <p>您可以將整合程式碼用於您自己的資料來源和全域 <a href="../features/datasources-list-and-settings.md#settings-menu-options"> 共用資料來源</a>，您可存取此專案。 例如，使用行動識別碼資料來源時，可以使用整合代碼。 請使用下列整合程式碼，與以下指定完全一致： </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>DSID_20914</b> 對於GAID，代表執行Android作業系統的裝置。 </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_20915</b> 對於IDFA，代表執行iOS作業系統的裝置。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>
