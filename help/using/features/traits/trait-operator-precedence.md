---
description: Trait Builder根据下面列出的运算顺序计算表达式，从高到低的优先级。 由高优先级运算符定义的特征元素首先在其它优先级运算符之前进行评估。 此部分按优先级对每个运算符进行从高到低的排序。
seo-description: Trait Builder根据下面列出的运算顺序计算表达式，从高到低的优先级。 由高优先级运算符定义的特征元素首先在其它优先级运算符之前进行评估。 此部分按优先级对每个运算符进行从高到低的排序。
seo-title: Trait builder中的操作顺序
solution: Audience Manager
title: Trait builder中的操作顺序
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Trait builder中的操作顺序 {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] 根据下面列出的运算顺序（从高到低的优先级）计算表达式。 由高优先级运算符定义的特征元素首先在其它优先级运算符之前进行评估。 此部分按优先级对每个运算符进行从高到低的排序。

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
   <td colname="col3"> 括号中的表达式始终以优先顺序计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 比较运算符 </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> 接下来计算小于、大于、小于／等于、大于／等于。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 等于运算符 </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> 等于、不等于在前一个运算符之后计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> 和</span> </td> 
   <td colname="col3" morerows="1"> 不适用 </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> 或者</span> </td> 
   <td colname="col3" morerows="1"> 不适用 </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [在TraitBuilder中使用布尔表达式(AND、OR、NOT)](../../reference/boolean-expressions-tsb.md)
>* [在TraitBuilder中使用比较运算符](../../features/traits/trait-comparison-operators.md)

