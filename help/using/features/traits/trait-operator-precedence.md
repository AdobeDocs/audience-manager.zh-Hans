---
description: 特征生成器根据下面列出的操作顺序（从高到低优先级）评估表达式。 由高优先级运算符定义的特征元素首先在其它优先级运算符之前进行评估。 此部分根据优先级对每个运算符进行排序，从高到低。
seo-description: 特征生成器根据下面列出的操作顺序（从高到低优先级）评估表达式。 由高优先级运算符定义的特征元素首先在其它优先级运算符之前进行评估。 此部分根据优先级对每个运算符进行排序，从高到低。
seo-title: 特征生成器中的运算顺序
solution: Audience Manager
title: 特征生成器中的运算顺序
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 13%

---


# 特征生成器中的运算顺序 {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] 根据下面列出的操作顺序评估表达式，从高优先级到低优先级。由高优先级运算符定义的特征元素首先在其它优先级运算符之前进行评估。 此部分根据优先级对每个运算符进行排序，从高到低。

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
   <td colname="col2"> () </td> 
   <td colname="col3"> 括号中的表达式始终优先计算，并按优先顺序排列。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 比较运算符 </td> 
   <td colname="col2"> &lt;&gt; &lt;&gt;= </td> 
   <td colname="col3"> 接下来评估小于、大于、小于／等于、大于／等于。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 等式运算符 </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> 等于、不等于在前一个运算符之后计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1">布尔值<span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> 且</span> </td> 
   <td colname="col3" morerows="1"> 不适用 </td> 
  </tr> 
  <tr> 
   <td colname="col1">布尔值<span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> 或者</span> </td> 
   <td colname="col3" morerows="1"> 不适用 </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [在TraitBuilder中使用布尔表达式(AND、OR、NOT)](../../reference/boolean-expressions-tsb.md)
>* [在TraitBuilder中使用比较运算符](../../features/traits/trait-comparison-operators.md)

