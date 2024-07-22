---
description: 特征生成器根据下面列出的操作顺序（从高优先级到低优先级）评估表达式。 首先评估由高优先级运算符定义的特征元素，然后再评估其他优先级运算符。 本节根据优先级从高到低对每个运算符进行排序。
seo-description: Trait Builder evaluates expressions according to the order-of-operations listed below, from high to low precedence. Trait elements defined by high-precedence operators are evaluated first, before other precedence operators. This section ranks each operator according to precedence, from high to low.
seo-title: Order of Operations in Trait Builder
solution: Audience Manager
title: 特征生成器中的运算顺序
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
exl-id: 90700479-4a8e-4a07-81ef-2e9d8a1d9f15
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 3%

---

# 特征生成器中的运算顺序 {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder]根据下面列出的操作顺序从高优先级到低优先级评估表达式。 首先评估由高优先级运算符定义的特征元素，然后再评估其他优先级运算符。 本节根据优先级从高到低对每个运算符进行排序。

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 运算符优先级 </th> 
   <th colname="col2" class="entry"> 符号 </th> 
   <th colname="col3" class="entry"> 注释 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 圆括号 </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> 括号中的表达式始终按优先顺序计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 比较运算符 </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> 接下来评估“小于”、“大于”、“小于/等于”、“大于/等于”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 相等运算符 </td> 
   <td colname="col2"> ==！= </td> 
   <td colname="col3"> 在前面的运算符之后计算“等于”、“不等于”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1">布尔值<span class="wintitle">和</span> </td> 
   <td colname="col2"><span class="wintitle">和</span> </td> 
   <td colname="col3" morerows="1"> 不适用 </td> 
  </tr> 
  <tr> 
   <td colname="col1">布尔值<span class="wintitle">或</span> </td> 
   <td colname="col2"><span class="wintitle">或</span> </td> 
   <td colname="col3" morerows="1"> 不适用 </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [在TraitBuilder中使用布尔表达式(AND、OR、NOT)](../../reference/boolean-expressions-tsb.md)
>* [在TraitBuilder中使用比较运算符](../../features/traits/trait-comparison-operators.md)
