---
description: 有关在表达式生成器代码编辑器中创建表达式的示例，可参阅。
seo-description: Examples you can refer to for creating expressions in the Expression Builder code editor.
seo-title: Sample Expressions With Boolean and Comparison Operators
solution: Audience Manager
title: 带布尔和比较运算符的示例表达式
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
exl-id: 68041d61-7942-4c2f-9e78-f2b2f803ef59
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 3%

---

# 带布尔和比较运算符的示例表达式 {#sample-expressions-with-boolean-and-comparison-operators}

有关在[!UICONTROL Expression Builder]代码编辑器中创建表达式的示例，您可以参阅。

## 代码示例概述 {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

使用[!UICONTROL Expression Builder]代码编辑器创建您自己的特征规则。 以下示例可帮助您入门。 某些示例在变量&#x200B;*`key`*&#x200B;前加上`c_`，以将其标识为用户定义的变量。 如果您的事件调用使用该语法将数据发送到`c_`，请包含&#x200B;*`key`*&#x200B;变量的[!DNL Audience Manager]前缀（或任何其他命名约定）。

## 布尔表达式 {#boolean-expressions}

### 和示例

该规则使用布尔[!UICONTROL AND]运算符建立特征资格要求。

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 示例代码 </th> 
   <th colname="col2" class="entry"> 要获得资格，访客必须 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">查找特定的品牌和型号。 </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">从搜索结果页面查找产品（搜索=“1”或“true”）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### 或示例

此规则使用[!DNL Boolean] [!UICONTROL OR]和[!UICONTROL AND]运算符建立特征资格要求。

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 示例代码 </th> 
   <th colname="col2" class="entry"> 要获得资格，访客必须 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> 满足变量<code><i>a </i></code>或<code><i>b </i></code>和<code><i>c </i></code>设置的条件。 </td> 
  </tr> 
 </tbody> 
</table>

## 范围示例大于、小于、等于

此规则使用范围确定特征资格要求。

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 示例代码 </th> 
   <th colname="col2" class="entry"> 要获得资格，访客必须 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> 满足介于1.00和100.00之间的任何价格条件。 </td> 
  </tr> 
 </tbody> 
</table>
