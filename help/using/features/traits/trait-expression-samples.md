---
description: 有关在表达式生成器代码编辑器中创建表达式的信息，请参阅相关示例。
seo-description: 有关在表达式生成器代码编辑器中创建表达式的信息，请参阅相关示例。
seo-title: 含布尔和比较运算符的示例表达式
solution: Audience Manager
title: 含布尔和比较运算符的示例表达式
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: 特征
exl-id: 68041d61-7942-4c2f-9e78-f2b2f803ef59
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 13%

---

# 含布尔和比较运算符的示例表达式 {#sample-expressions-with-boolean-and-comparison-operators}

有关在[!UICONTROL Expression Builder]代码编辑器中创建表达式的信息，请参阅相关示例。

## 代码示例概述{#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

使用[!UICONTROL Expression Builder]代码编辑器创建您自己的特征规则。 以下示例可帮助您快速入门。 有些示例在&#x200B;*`key`*&#x200B;变量前面加上了`c_` ，以将其标识为用户定义的变量。 如果事件调用使用该语法向[!DNL Audience Manager]发送数据，请为&#x200B;*`key`*&#x200B;变量包含`c_`前缀（或任何其他命名约定）。

## 布尔表达式{#boolean-expressions}

### 和示例

规则使用布尔[!UICONTROL AND]运算符确定特征资格要求。

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
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">查找特定的制作和模型。 </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">从搜索结果页面查找产品（搜索=“1”或“true”）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### 或示例

此规则使用[!DNL Boolean] [!UICONTROL OR]和[!UICONTROL AND]运算符确定特征资格要求。

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

## 范围示例，其大于、小于、等于

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
   <td colname="col2"> 在1.00到100.00之间满足任何价格条件。 </td> 
  </tr> 
 </tbody> 
</table>
