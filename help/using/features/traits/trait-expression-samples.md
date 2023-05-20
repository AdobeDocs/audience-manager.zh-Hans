---
description: 在運算式產生器程式碼編輯器中建立運算式時可參考的範例。
seo-description: Examples you can refer to for creating expressions in the Expression Builder code editor.
seo-title: Sample Expressions With Boolean and Comparison Operators
solution: Audience Manager
title: 含布尔和比较运算符的示例表达式
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
exl-id: 68041d61-7942-4c2f-9e78-f2b2f803ef59
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 10%

---

# 含布尔和比较运算符的示例表达式 {#sample-expressions-with-boolean-and-comparison-operators}

您可參考的範例，說明如何在中建立運算式 [!UICONTROL Expression Builder] 程式碼編輯器。

## 程式碼範例概觀 {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

使用建立您自己的特徵規則 [!UICONTROL Expression Builder] 程式碼編輯器。 以下範例可協助您開始使用。 部分範例的前言為 *`key`* 變數搭配 `c_` 以識別為使用者定義的變數。 包含 `c_` 首碼（或任何其他命名慣例） *`key`* 變數(如果您的事件呼叫將資料傳送至 [!DNL Audience Manager] 使用該語法。

## 布林運算式 {#boolean-expressions}

### AND範例

規則會使用布林值來建立特徵資格需求 [!UICONTROL AND] 運運算元。

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 示例代码 </th> 
   <th colname="col2" class="entry"> 若要符合資格，訪客必須 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">尋找特定的品牌和模型。 </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">從搜尋結果頁面尋找產品（搜尋= "1"或"true"）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### OR範例

此規則會使用以下專案建立特徵資格要求 [!DNL Boolean] [!UICONTROL OR] 和 [!UICONTROL AND] 運運算元。

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 示例代码 </th> 
   <th colname="col2" class="entry"> 若要符合資格，訪客必須 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> 符合變數設定的條件 <code><i>a </i></code> 或 <code><i>b </i></code> 和 <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## 大於、小於、等於的範圍範例

此規則會使用範圍來建立特徵資格需求。

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 示例代码 </th> 
   <th colname="col2" class="entry"> 若要符合資格，訪客必須 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> 符合1.00到100.00之間的任何價格條件。 </td> 
  </tr> 
 </tbody> 
</table>
