---
description: Travical Builder根据下面列出的操作顺序对表达式进行评估，无论是从高到低还是低优先级。优先级元素定义的特征元素首先在其他优先运算符之前进行评估。此部分按优先级从高到低排列每个操作符。
seo-description: Travical Builder根据下面列出的操作顺序对表达式进行评估，无论是从高到低还是低优先级。优先级元素定义的特征元素首先在其他优先运算符之前进行评估。此部分按优先级从高到低排列每个操作符。
seo-title: Travical Builder中的操作顺序
solution: Audience Manager
title: Travical Builder中的操作顺序
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Order of Operations in Trait Builder {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] 根据下面列出的操作顺序(从高到低)评估表达式。优先级元素定义的特征元素首先在其他优先运算符之前进行评估。此部分按优先级从高到低排列每个操作符。

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 运营商优先级 </th> 
   <th colname="col2" class="entry"> Symbol </th> 
   <th colname="col3" class="entry"> 注释 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 括号 </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> 括号中的表达式始终按优先顺序进行评估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 比较运算符 </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> 小于、大于、小于、大于/等于大于/等于的大于/等于的值。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 平等运算符 </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> 等于，不等于等于之前的运算符。 </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> AND</span> </td> 
   <td colname="col3" morerows="1"> 不适用 </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> 或者</span> </td> 
   <td colname="col3" morerows="1"> 不适用 </td> 
  </tr> 
 </tbody>
</table>

>[!MORE_ LIKE_ This]
>
>* [在TritBuilder中使用Boolean表达式(AND、OR、NOT)](../../reference/boolean-expressions-tsb.md)
>* [在TritBuilder中与比较运算符协作](../../features/traits/trait-comparison-operators.md)

