---
description: 本文解释Audience Manager特征和细分工具如何使用Boolean表达式AND、OR和NOT。
seo-description: 本文解释Audience Manager特征和细分工具如何使用Boolean表达式AND、OR和NOT。
seo-title: 特征和区段生成器中的布尔表达式
solution: Audience Manager
title: 特征和区段生成器中的布尔表达式
uuid: 14f02d3f-4c844-41fe-bc91-b34 f0 d49574 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Boolean Expressions in Trait and Segment Builder{#boolean-expressions-in-trait-and-segment-builder}

本文解释Audience Manager特征和细分工具如何使用Boolean表达式AND、OR和NOT。

<!-- 

c_tb_boolean.xml

 -->

**Boolean表达式**

Boolean逻辑是代数的一个分支，它使用几个基本表达式(或操作符)确定语句是真的还是假的。The most common operators are [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]. 这些表达式的组合可帮助您制作具有针对性的特征或专门适合您的数据要求的细分资格规则。下图显示了基本Boolean表达式的工作原理。

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT] 该运算符使用隐含的“和”条件，有时编写为 [!UICONTROL AND NOT]。

**如何在特征和区段生成器中使用布尔表达式**

您可以使用Boolean表达式构建特征和细分资格规则。The table below describes general best practices for creating qualification criteria with [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 表达式 </th> 
   <th colname="col2" class="entry"> 使用它创建 </th> 
   <th colname="col3" class="entry"> 要符合资格 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> AND</span></b> </p> </td> 
   <td colname="col2"> <p>更窄、更专注的受众资格要求。 </p> </td> 
   <td colname="col3"> <p>Users <i>must</i> belong to all specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OR</span></b> </p> </td> 
   <td colname="col2"> <p>广泛、专注的受众资格要求。 </p> </td> 
   <td colname="col3"> <p>Users <i>can</i> belong to any specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>更窄、更专注的受众资格要求。 </p> <p>当有多种条件导致定义受众资格要求困难或低效时有用。有时，验证排除的要求更容易，而不是包含在内。 </p> </td> 
   <td colname="col3"> <p>Users <i>must not</i> belong to an excluded trait or segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]用例示例**

[!UICONTROL AND] 当您轻松枚举特征会员资格要求时，该运算符很有用。例如，假设您需要创建“昂贵的相机购物者”。”有了像素模型，您就必须为相机创建像素并为其放置数字价格值。By contrast, with traits you can apply Boolean operators to handle both conditions (cameras [!UICONTROL AND] price). 结果是，使用较少HTTP调用的高效数据收集功能可以帮助保留站点上的用户体验。

**[!UICONTROL OR]用例示例**

[!UICONTROL OR] 当您希望创建具有广泛受众资格要求的信号时，此运算符很有用。If you have several trait or segment qualification requirements, the [!UICONTROL OR] operator will evaluate to true when your site visitors exhibit *any* of those characteristics. [!UICONTROL OR] 当您希望快速创建大量符合条件的站点访客时最有用。

**[!UICONTROL AND NOT]用例示例**

[!UICONTROL AND NOT] 当 *通过排除* 而不 *是包含包含受众更容易定义受众时，此运算符很有用*。例如，假设您要进行销售，并希望将访客细分到只查看完完整价格项目的客户。Rather than create a list of signals for all qualifying full or sale-price items, it may be easier to qualify visitors if they have *not* seen a sale price item. 这种效率更高，因为与完全价格相比，您的销售价格项目通常更少。With a Boolean [!UICONTROL NOT], visitors *must not* exhibit the sale signal to qualify for full-price audience membership. By contrast, [!UICONTROL AND NOT] is the opposite of the [!UICONTROL AND] use case, which showed how audience membership is determined by inclusion (i.e., the visitor qualified based on 2 explicitly stated signals).

>[!MORE_ LIKE_ This]
>
>* [在TritBuilder中与比较运算符协作](../features/traits/trait-comparison-operators.md)
>* [TritBuilder表达式中的操作顺序](../features/traits/trait-operator-precedence.md)

