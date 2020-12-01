---
description: 本文说明Audience Manager特征和段工具如何使用布尔表达式AND、OR和NOT。
seo-description: 本文说明Audience Manager特征和段工具如何使用布尔表达式AND、OR和NOT。
seo-title: 特征和区段生成器中的布尔表达式
solution: Audience Manager
title: 特征和区段生成器中的布尔表达式
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 4%

---


# 特征和区段生成器中的布尔表达式{#boolean-expressions-in-trait-and-segment-builder}

本文说明Audience Manager特征和段工具如何使用布尔表达式AND、OR和NOT。

<!-- 

c_tb_boolean.xml

 -->

**布尔表达式**

布尔逻辑是代数的一个分支，它使用几个基本表达式（或运算符）来确定语句是真还是假。 最常见的运算符是[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]。 这些表达式的组合可帮助您制定专门针对数据要求的特征或细分资格规则。 下图显示了基本布尔表达式的工作方式。

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT]运算符使用隐含的“and”条件，有时写为[!UICONTROL AND NOT]。

**如何在特征和区段生成器中使用布尔表达式**

您可以使用布尔表达式构建特征和区段资格规则。 下表介绍了创建[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]资格标准的一般最佳实践。

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 表达式 </th> 
   <th colname="col2" class="entry"> 使用它创建 </th> 
   <th colname="col3" class="entry"> 要获得资格 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 且</span></b> </p> </td> 
   <td colname="col2"> <p>明确、重点明确的受众资格要求。 </p> </td> 
   <td colname="col3"> <p>用户<i>必须</i>属于所有指定的特征或区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 或者</span></b> </p> </td> 
   <td colname="col2"> <p>广泛、不太重点的受众资格要求。 </p> </td> 
   <td colname="col3"> <p>用户<i>可以</i>属于任何指定的特征或区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>明确、重点明确的受众资格要求。 </p> <p>当存在多种条件导致难以或效率低下地定义受众资格要求时非常有用。 有时，根据排除而非包括的要求进行验证会更容易。 </p> </td> 
   <td colname="col3"> <p>用户<i>不得</i>属于被排除的特征或区段。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]用例示例**

当您轻松枚举特征成员资格要求时，[!UICONTROL AND]运算符很有用。 例如，假设您需要创建“昂贵的相机购物者”受众。 对于像素模型，您必须在页面上创建和放置相机的像素以及数字价格值。 相反，利用特征，您可以应用布尔运算符来处理两种情况（相机[!UICONTROL AND]价格）。 这样，只需减少HTTP调用，即可高效地收集数据，这反过来又有助于保留您网站上的用户体验。

**[!UICONTROL OR]用例示例**

如果要创建具有广泛受众资格要求的信号，[!UICONTROL OR]运算符很有用。 如果您有几个特征或区段资格要求，当您的站点访客显示&#x200B;*任何*&#x200B;这些特征时，[!UICONTROL OR]运算符将计算为true。 [!UICONTROL OR] 当您希望快速创建大量合格网站受众时，可能最有用。

**[!UICONTROL AND NOT]用例示例**

当更容易通过&#x200B;*exclusion*&#x200B;而不是&#x200B;*inclusion*&#x200B;定义受众时，[!UICONTROL AND NOT]运算符很有用。 例如，假设您正在进行销售，并且希望将访客细分为仅查看完整价格项目的客户。 如果访客有&#x200B;*不*&#x200B;看到销售价格项目，则与其为所有符合条件的完整或销售价格项目创建信号列表，不如更容易确定其资格。 这在管理上是有效的，因为与全价销售的产品相比，您的销售价格项目通常更少。 对于布尔值[!UICONTROL NOT],访客&#x200B;*不能*&#x200B;显示销售信号，以获得全价受众成员资格。 相反，[!UICONTROL AND NOT]与[!UICONTROL AND]用例相反，后者显示了如何通过包含(即基于2个明确声明的信号限定的受众)来确定访客成员身份。

>[!MORELIKETHIS]
>
>* [在TraitBuilder中使用比较运算符](../features/traits/trait-comparison-operators.md)
>* [TraitBuilder表达式中的操作顺序](../features/traits/trait-operator-precedence.md)

