---
description: 本文介紹建立特徵規則時，您必須附加至關鍵變數的首碼。
seo-description: This article describes the prefixes you must attach to key variables when creating trait rules.
seo-title: Prefix Requirements for Key Variables
solution: Audience Manager
title: 关键变量的前缀要求
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
exl-id: 67fe0c74-6831-48cb-90cf-417ebbf7f272
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 4%

---

# 关键变量的前缀要求 {#prefix-requirements-for-key-variables}

本文介紹建立特徵規則時，您必須附加至關鍵變數的首碼。

<!-- r_tb_variable_prefixes.xml -->

## 關鍵變數首碼的用途

當您建立 [!UICONTROL Trait Builder] 規則，請務必在關鍵變數前面加上建議的前置詞。 這些首碼可識別傳入的資料型別，並幫助避免內的名稱空間衝突 [!DNL Audience Manager]. 一般而言，您可以為變數指定任何名稱，但如果索引鍵變數名稱不符合事件呼叫中的變數名稱，則不會處理規則的資料。

## 關鍵變數的首碼

下表定義所使用的常用首碼 [!UICONTROL Trait Builder].

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 金鑰變數首碼 </th> 
   <th colname="col2" class="entry"> 識別變數 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>因客戶而異。 這是從您自己的屬性傳入的重要資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>在 <span class="keyword"> Audience Manager</span> 層級。 此資料在整個中是一致的 <span class="keyword"> Audience Manager</span> 生態系統。 另請參閱 <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> DCS API呼叫的支援屬性</a> 以取得更完整的清單。</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>其中包含 <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP標頭</a> 資訊。 包含標頭引數，例如 <code> referer</code>，<code> IP</code>， <code> accept-language</code>等。 </p> <p> <p>注意：若客戶使用的DIL版本早於9.0，則資料收集需使用 <code> h_referer</code> signal無法在Safari瀏覽器上運作。 透過以下主題介紹 <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>，Safari瀏覽器可能會將demdex.net網域分類為追蹤器，且會在資料收集請求上截斷反向連結，使其僅包含來源，而非完整URL。 另請參閱 <a href="../../dil/dil-overview.md#get-implement-dil-code">取得和實作DIL程式碼</a> 以取得最新的DIL版本。<p>使用此首碼的訊號不會出現在 <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">訊號搜尋</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>我們的 <span class="wintitle"> 資料收集伺服器</span> 允許傳遞私人引數。 基本上，任何開頭為 <code> p_</code> 將用於特徵評估，但不會記錄到下游，也不會儲存。 </p> <p>範例：給定 <code> /event?p_age=23</code> 和一個特徵，例如 <code> YoungPeople = p_age &lt; 25</code>，則會實現特徵，但 <code> p_age=23</code> 要求後將會捨棄機碼值組，且不會加以記錄。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [基本資訊概述](../../features/traits/create-onboarded-rule-based-traits.md)
>* [管理特征规则](../../features/traits/manage-trait-rules.md#managing-trait-rules)

