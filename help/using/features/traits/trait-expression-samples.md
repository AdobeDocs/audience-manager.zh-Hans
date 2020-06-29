---
description: 有关在表达式生成器代码编辑器中创建表达式的示例，请参阅。
seo-description: 有关在表达式生成器代码编辑器中创建表达式的示例，请参阅。
seo-title: 含布尔和比较运算符的示例表达式
solution: Audience Manager
title: 含布尔和比较运算符的示例表达式
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 12%

---


# 含布尔和比较运算符的示例表达式 {#sample-expressions-with-boolean-and-comparison-operators}

有关在代码编辑器中创建表达式的示例， [!UICONTROL Expression Builder] 请参阅。

## 代码示例概述 {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

使用代码编辑器创建您自己的 [!UICONTROL Expression Builder] 特征规则。 以下示例可以帮助您开始。 有些示例在变量前 *`key`* 面加 `c_` 以说明，将其标识为用户定义的变量。 如果事件 `c_` 调用使用该语法向发送数据，则 *`key`* 请为变量添加前缀(或任何其 [!DNL Audience Manager] 他命名约定)。

## 布尔表达式 {#boolean-expressions}

### 和示例

该规则使用布尔运算符建立特征资格 [!UICONTROL AND] 要求。

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 示例代码 </th> 
   <th colname="col2" class="entry"> 要符合条件，访客 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">查找特定品牌和型号。 </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">在搜索结果页面中查找产品（search = "1"或"true"）。 </li> 
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
   <th colname="col2" class="entry"> 要符合条件，访客 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> 满足变量或和设 <code><i>a </i></code> 置的 <code><i>b </i></code> 条件 <code><i>c </i></code>。 </td> 
  </tr> 
 </tbody> 
</table>

## 大于、小于、等于的范围示例

此规则使用范围建立特质资格要求。

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 示例代码 </th> 
   <th colname="col2" class="entry"> 要符合条件，访客 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> 满足1.00到100.00之间的任何价格条件。 </td> 
  </tr> 
 </tbody> 
</table>