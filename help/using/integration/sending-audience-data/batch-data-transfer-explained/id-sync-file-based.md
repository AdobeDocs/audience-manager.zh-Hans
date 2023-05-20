---
description: 說明用於檔案式ID同步的必填欄位、語法和命名慣例。 根據這些規格命名並組織您的檔案內容。
seo-description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-title: Name and Content Requirements for ID Synchronization Files
solution: Audience Manager
title: ID 同步文件的名称和内容要求
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: Inbound Data Transfers
exl-id: e6b3a438-f843-4a24-89fd-03ef77d7cf04
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 5%

---

# ID 同步文件的名称和内容要求 {#name-and-content-requirements-for-id-synchronization-files}

說明用於檔案式ID同步的必填欄位、語法和命名慣例。 根據這些規格命名並組織您的檔案內容。

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）檔案中會指示程式碼元素和選項。 请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

## 檔案名稱語法和範例 {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID檔案名稱包含下列必要和選用元素：

*`[adobe_id_]`* *`[c2c_id_]`*`MASTERDPID_DPID`*`[_DPID]`*`_TIMESTAMP.sync`*`[.SPLIT_NUMBER]`*`[.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_id</code> </p> </td> 
   <td colname="col2"> <p>將檔案識別為ID同步檔案的靜態首碼。 比對裝置ID與其他裝置ID或客戶ID (DPUUID)時，請使用此首碼。  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>將檔案識別為People-Based Destinations之ID同步檔案的靜態首碼。 將客戶ID (DPUUID)與以人物為基礎的目的地的雜湊電子郵件地址比對時，請使用此首碼。  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> <p>主要資料提供者ID是檔案名稱中DPID的父系ID。 此外，資料檔案中的第一個使用者ID會對應至主ID。 後續的DPID是屬於主磁碟機的其他識別碼。 同步會將檔案名稱中的DPID對應至檔案中的UUID。</p> <p>此DPID只能包含裝置ID，例如AAM UUID、GAID、IDFA等。 不可包含DPUUID。 這樣做可能會導致不正確的同步。</p>  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>資料提供者ID。 這些ID代表與主DPID相關聯的實體或資料來源。 同步會將檔案名稱中的DPID對應至檔案中的UUID。 </p> <p>檔案名稱中的DPID數量必須與資料檔案中的UUID數量相符。 例如，假設您的檔案名稱包含主DPID和3個DPID。 您的資料檔案必須包含4個相對應的UUID欄，格式如以下檔案內容一節中所述。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>以秒為單位的10位數UNIX時間戳記。 時間戳記有助於讓每個檔案名稱是唯一的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>表示正常、完整的同步處理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整數。 將大型檔案分割成多個較小檔案時使用。 這有助於改善處理時間。 數字表示您傳送的原始檔案的哪個部分。 請參閱下列檔案名稱範例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>指定檔案壓縮為選用的gzip壓縮。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 檔案名稱範例

下列範例顯示格式正確的檔案名稱。 您的檔案名稱可能類似。

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> 如需以人物為基礎的目的地的ID同步檔案命名（c2c首碼），請參閱 [工作流程A — 以所有線上活動和離線資料為基礎的個人化](../../../features/destinations/people-based-destinations-workflow-combined.md) 或 [工作流程B — 以僅限離線資料為基礎的個人化](../../../features/destinations/people-based-destinations-workflow-offline.md).

## 檔案內容語法和範例 {#file-content-syntax}

ID檔案的內容包括下列元素：

*`UUID`* `<tab>`*`UUID`*`<tab>`*`UUID`*`<tab>`*`UUID`*

檔案包含使用者ID ([!DNL UUID])。 在每列中，以索引標籤分隔ID。 下列範例顯示正確格式化的ID檔案。 您的內容看起來可能類似。

```
abc123 def456 ghi789 xyz987
```

### 檔案內容考量事項 {#considerations}

建立傳入檔案時，請確定第一欄僅填入裝置ID，例如 [!DNL AAM UUID]， [!DNL GAID]， [!DNL IDFA]、等等。 另請參閱 [Audience Manager內的ID索引](../../../reference/ids-in-aam.md) 以取得Audience Manager所支援ID的詳細說明。

>[!IMPORTANT]
>
>不要使用 [DPUUID](../../../reference/ids-in-aam.md) 在第一欄中。 這樣做可能會導致不正確的同步。

## 同步會比對DPUUID與UUID {#sync-matches-dpuuids-uuids}

ID同步檔案的用途是同步 [DPUUID](../../../reference/ids-in-aam.md) 從您自己的資料來源，使用 [!DNL Audience Manager] UUID。 同步對應 [!DNL DPUUID]來自主版 [!DNL DPID] 及其相關專案 [!DNL DPID]s到 [!DNL Audience Manager] [!DNL UUID]s.將ID放在檔案名稱與內文中的位置，可決定這些識別碼如何相互對應。 舉例來說，請取這裡所示的兩個範例檔案：

* **檔案1：** `adobe_id_0_12345_1476312152.sync`

* **檔案2：**  `adobe_id_12345_67890_1476312876.sync`

<br/>

根據範例名稱和內容，ID會像這樣對應在一起：

**檔案1** ( [下載範例檔案](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = ADOBE AUDIENCE MANAGER UUID | DPID12345定 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

步驟1： ID同步程式會同步 [!DNL DPUUID]s from [!DNL DPID] 使12345 [!DNL Audience Manager] [!DNL UUID]s在左欄。 請注意 [!DNL DPID] 檔案名稱中的「0」代表 [!DNL Audience Manager] [!DNL UUID]s.
<br/>

**檔案2** ( [下載範例檔案](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

步驟2： [!DNL DPUUID]s from [!DNL DPID] 12345已在步驟1中與Audience Manager同步 [!DNL UUID]s.此ID同步會同步處理 [!DNL DPUUID]s from [!DNL DPID] 67890用Audience Manager [!DNL UUID]步驟1中的。

<br/>

## 其他格式需求 {#other-format-reqs}

使用者ID不能：

* ID本身有索引標籤。 標籤僅用於分隔資料檔案中的個別ID。
* 包含個人識別資訊([!UICONTROL PII])。
* 使用 [!DNL URL] 編碼。 僅傳入未編碼的ID。

系統不會處理或實現任何以定位字元或空格結尾的列。 通常，請確定列尾保持清晰。
