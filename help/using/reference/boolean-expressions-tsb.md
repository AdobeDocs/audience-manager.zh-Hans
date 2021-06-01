---
description: 本文介绍Audience Manager特征和区段工具如何使用布尔表达式AND、OR和NOT。
seo-description: 本文介绍Audience Manager特征和区段工具如何使用布尔表达式AND、OR和NOT。
seo-title: 特征和区段生成器中的布尔表达式
solution: Audience Manager
title: 特征和区段生成器中的布尔表达式
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: 参考
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---

# 特征和区段生成器中的布尔表达式{#boolean-expressions-in-trait-and-segment-builder}

本文介绍Audience Manager特征和区段工具如何使用布尔表达式AND、OR和NOT。

<!-- 

c_tb_boolean.xml

 -->

**布尔表达式**

布尔逻辑是代数的一个分支，它使用一些基本表达式（或运算符）来确定语句是true还是false。 最常见的运算符是[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]。 这些表达式的组合可帮助您使重点突出的特征或区段鉴别规则特别适合您的数据要求。 下图显示了基本布尔表达式的工作方式。

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT]运算符使用默示的“and”条件，有时写为[!UICONTROL AND NOT]。

**如何在特征和区段生成器中使用布尔表达式**

您可以使用布尔表达式构建特征和区段鉴别规则。 下表介绍了使用[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]创建资格标准的一般最佳实践。

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 表达式 </th> 
   <th colname="col2" class="entry"> 使用它创建 </th> 
   <th colname="col3" class="entry"> 符合条件 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 且</span></b> </p> </td> 
   <td colname="col2"> <p>狭隘、重点突出的受众资格要求。 </p> </td> 
   <td colname="col3"> <p>用户<i>必须</i>属于所有指定的特征或区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 或者</span></b> </p> </td> 
   <td colname="col2"> <p>广泛、重点较浅的受众资格要求。 </p> </td> 
   <td colname="col3"> <p>用户<i>可以</i>属于任何指定的特征或区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>狭隘、重点突出的受众资格要求。 </p> <p>当存在多种导致定义受众资格要求困难或效率低下的条件时，此变量非常有用。 有时，根据排除而不是包含的要求进行验证会比较容易。 </p> </td> 
   <td colname="col3"> <p>用户<i>不得</i>属于排除的特征或区段。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]用例示例**

当您轻松枚举了特征成员资格要求时，[!UICONTROL AND]运算符非常有用。 例如，假设您需要创建“昂贵的相机购物者”的受众。 对于像素模型，您必须为相机创建并放置像素，并在页面上放置数字价格值。 相反，使用特征，您可以应用布尔运算符来处理两个条件（相机价格[!UICONTROL AND]）。 这样可以减少HTTP调用，从而高效地收集数据，进而有助于保留您网站上的用户体验。

**[!UICONTROL OR]用例示例**

当您想要创建具有广泛受众资格要求的信号时，[!UICONTROL OR]运算符非常有用。 如果您有多个特征或区段资格要求，当您的网站访客显示这些特征的&#x200B;*任意*&#x200B;时，[!UICONTROL OR]运算符将评估为true。 [!UICONTROL OR] 当您想要快速创建大量符合条件的网站访客时，可能会非常有用。

**[!UICONTROL AND NOT]用例示例**

当通过&#x200B;*exclusion*&#x200B;而不是&#x200B;*inclusion*&#x200B;定义受众时，[!UICONTROL AND NOT]运算符非常有用。 例如，假设您正在进行销售，并且希望将访客细分为只查看完整价格项目的客户。 与其为所有符合条件的完整或销售价格项目创建一个信号列表，如果访客&#x200B;*未*&#x200B;看到销售价格项目，则更容易确定其资格。 这在管理上是有效的，因为与全价提供的价格相比，您的销售价格项目通常较少。 如果使用布尔值[!UICONTROL NOT]，则访客&#x200B;*不得*&#x200B;显示销售信号以符合全价受众成员资格条件。 相反， [!UICONTROL AND NOT]与[!UICONTROL AND]用例相反，用于显示受众成员资格如何通过包含（即，访客根据2个明确指示的信号进行鉴别）来确定。

>[!MORELIKETHIS]
>
>* [在TraitBuilder中使用比较运算符](../features/traits/trait-comparison-operators.md)
* [特征生成器表达式中的运算顺序](../features/traits/trait-operator-precedence.md)

