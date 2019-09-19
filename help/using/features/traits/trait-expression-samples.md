---
description: 有关在Expression builder代码编辑器中创建表达式的示例，请参阅。
seo-description: 有关在Expression builder代码编辑器中创建表达式的示例，请参阅。
seo-title: 具有布尔和比较运算符的示例表达式
solution: Audience Manager
title: 具有布尔和比较运算符的示例表达式
uuid: ee74c376-2099-4816-8694-43f58845a0ac
translation-type: tm+mt
source-git-commit: 92b75773d2bbe2f635d84bd5bffe625d2023b6cf

---


# 具有布尔和比较运算符的示例表达式 {#sample-expressions-with-boolean-and-comparison-operators}

有关在代码编辑器中创建表达式的示例， [!UICONTROL Expression Builder] 请参阅。

## 代码示例概述 {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

使用代码编辑器创建您自己的特 [!UICONTROL Expression Builder] 征规则。 以下示例可以帮助您快速入门。 一些示例在变量前面加 *`key`* 以引 `c_` 用，以将其标识为用户定义的变量。 如果事 `c_` 件调用使用该语法向 *`key`* 发送数据，则包括变量的前缀(或任何其 [!DNL Audience Manager] 他命名约定)。

## 布尔表达式 {#boolean-expressions}

### AND示例

该规则使用布尔运算符建立特征资格 [!UICONTROL AND] 要求。

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 示例代码 </th> 
   <th colname="col2" class="entry"> 要获得资格，访客必须 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A")AND(c_model=="B")AND(c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">查找特定品牌和型号。 </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">从搜索结果页面中查找产品（search = "1"或"true"）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### OR示例

此规则使用运算符和运算符建立特 [!DNL Boolean] 征 [!UICONTROL OR] 资格 [!UICONTROL AND] 要求。

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 示例代码 </th> 
   <th colname="col2" class="entry"> 要获得资格，访客必须 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>（a== "1"或b=="1"）和(c=="new")</code> </td> 
   <td colname="col2"> 满足变量a或 <code><i>b和 </i></code> c设 <code><i>置 </i></code> 的 <code><i>条件 </i></code>。 </td> 
  </tr> 
 </tbody> 
</table>

## 大于、小于、等于的范围示例

此规则使用范围建立特征资格要求。

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 示例代码 </th> 
   <th colname="col2" class="entry"> 要获得资格，访客必须 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>（价格&gt;= 1.00，价格&lt;= 100.00）</code> </td> 
   <td colname="col2"> 满足1.00到100.00之间的任何价格条件。 </td> 
  </tr> 
 </tbody> 
</table>