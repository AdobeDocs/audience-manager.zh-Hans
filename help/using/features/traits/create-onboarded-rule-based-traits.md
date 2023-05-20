---
description: 說明規則型和已上線特徵建立程式的特定設定步驟和功能。
keywords: 建立特徵；建立特徵
seo-description: Describes set up steps and features specific to the rules-based and onboarded trait creation process.
seo-title: Create Rules-Based or Onboarded Traits
solution: Audience Manager
title: 创建基于规则的特征或已载入的特征
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 7%

---

# 创建[!UICONTROL Rules-Based]或 [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

說明的設定步驟和特定功能 [!UICONTROL rules-based] 和 [!UICONTROL onboarded] 特徵建立過程。

<!-- c_tb_rules_traits.xml -->

## 特徵的基本資訊 {#basics}

在 [!UICONTROL Trait Builder]，則 [!UICONTROL Basic Information] 設定可讓您建立新或編輯現有 [!UICONTROL traits]. 此 [!UICONTROL Basic Information] 的設定相同 [!UICONTROL rules-based]， [!UICONTROL onboarded] 和 [!UICONTROL algorithmic traits]. 若要建立新的 [!UICONTROL trait]，提供名稱（避免特殊字元）、 [!UICONTROL data source]，並選取 [!UICONTROL storage folder]. 其他 [!UICONTROL Basic Information] 欄位為選用。

<!-- c_tb_basics.xml -->

![建立特徵](assets/create-trait.png)

### 已定義的基本資訊欄位

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 介面元素 </th> 
   <th colname="col2" class="entry"> 说明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">名称</span></b> </td> 
   <td colname="col2"> <p>特徵名稱。 必需. </p> <p>長度上限： 255個字元。 </p> <p> <p>注意：為特徵命名時，請避免使用下列特殊字元： 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">逗號 </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">破折號 </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">連字型大小 </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">索引標籤 </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">垂直條或垂直線符號 </li> 
      </ul> </p> </p> <p>這有助於減少您在設定 <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 傳入資料檔案傳輸</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 描述</span></b> </td> 
   <td colname="col2"> 幾個字詞可協助說明特徵的用途或功能。 可选。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 数据源</span></b> </td> 
   <td colname="col2"> 將特徵與特定資料提供者建立關聯。 必需. <p>使用第一個下拉式選單，在Audience Manager資料來源、Adobe Analytics報表套裝或兩者之間篩選。 然後，使用第二個下拉式選單來選擇資料來源。</p><p> 如果您未使用Adobe Analytics報表套裝，資料來源型別選擇器會停用，並預設為僅Audience Manager資料來源。</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 事件类型</span></b> </td> 
   <td colname="col2"> 通常根據功能（例如轉換、網站訪客、合作夥伴、頁面檢視等），將特徵指派給型別或類別。 可选。 <p> 若要瞭解如何建立轉換特徵，請參閱 <a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">在Audience Manager影片中建立轉換特徵</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 集成代码</span></b> </td> 
   <td colname="col2"> 供內部業務流程使用的ID、SKU或其他值的欄位。 可选。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 评论</span></b> </td> 
   <td colname="col2"> 特徵的一般注意事項。 可选。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 存放位置</span></b> </td> 
   <td colname="col2"> 決定特徵所屬的儲存資料夾。 必需. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 資料類別</span></b> </td> 
   <td colname="col2"> 根據常見類別來分類特徵。 <p>注意：特徵僅屬於單一類別。 可选。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 設定 [!UICONTROL Trait] 到期間隔 {#set-expiration-interval}

在 [!UICONTROL Trait Builder]，則 [!UICONTROL Advanced Options] 可讓您設定存留時間([!DNL TTL])間隔 [!UICONTROL trait]. [!DNL TTL] 定義合格訪客在網站內停留的天數 [!UICONTROL trait] （預設為120天）。 設為0時， [!UICONTROL trait] 會籍永不過期。

<!-- t_tb_ttl.xml -->

### 設定的TTL [!UICONTROL trait]

1. 展開 [!UICONTROL Advanced Options] 區段並輸入數字以設定 [!DNL TTL] 的值 [!UICONTROL trait].
1. 单击 **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [區段存留時間說明](../../features/traits/segment-ttl-explained.md)

