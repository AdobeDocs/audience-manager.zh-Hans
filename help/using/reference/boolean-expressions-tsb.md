---
description: 本文介绍Audience Manager特征和区段工具如何使用布尔表达式AND、OR和NOT。
seo-description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-title: Boolean Expressions in Trait and Segment Builder
solution: Audience Manager
title: 特征和区段生成器中的布尔表达式
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# 特征和区段生成器中的布尔表达式{#boolean-expressions-in-trait-and-segment-builder}

本文介绍Audience Manager特征和区段工具如何使用布尔表达式AND、OR和NOT。

<!-- 

c_tb_boolean.xml

 -->

**布尔表达式**

布尔逻辑是代数的一个分支，它使用几个基本表达式（或运算符）来确定语句是true还是false。 最常见的运算符是[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]。 这些表达式的组合可帮助您制定出专门适合您数据要求的重点特征或区段资格规则。 下图显示了基本布尔表达式的工作方式。

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT]运算符使用隐含的“与”条件，有时写为[!UICONTROL AND NOT]。

**如何在特征和区段生成器中使用布尔表达式**

可使用布尔表达式构建特征和区段资格规则。 下表描述了使用[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]创建资格标准的一般最佳实践。

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 表达式 </th> 
   <th colname="col2" class="entry"> 使用它创建 </th> 
   <th colname="col3" class="entry"> 获得资格 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle">和</span></b> </p> </td> 
   <td colname="col2"> <p>狭隘、集中的受众资格要求。 </p> </td> 
   <td colname="col3"> <p>用户<i>必须</i>属于所有指定的特征或区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle">或</span></b> </p> </td> 
   <td colname="col2"> <p>广泛、重点较低的受众资格要求。 </p> </td> 
   <td colname="col3"> <p>用户<i>可以</i>属于任何指定的特征或区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>狭隘、集中的受众资格要求。 </p> <p>当存在多个条件导致定义受众资格要求困难或效率低下时，非常有用。 有时，根据排除而不是包含的要求进行验证会更容易。 </p> </td> 
   <td colname="col3"> <p>用户<i>不得</i>属于排除的特征或区段。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]用例示例**

当您轻松枚举特征成员资格要求时，[!UICONTROL AND]运算符非常有用。 例如，假设您需要创建一个“昂贵的相机购买者”受众。 使用像素模型时，必须创建并放置相机的像素以及页面上的数字价格值。 相反，对于特征，您可以应用布尔运算符来处理这两个条件（摄像头[!UICONTROL AND]价格）。 这样可以通过减少的HTTP调用高效地收集数据，进而有助于保留您网站上的用户体验。

**[!UICONTROL OR]用例示例**

当您要创建具有广泛受众资格要求的信号时，[!UICONTROL OR]运算符很有用。 如果您有多个特征或区段资格要求，则当您的网站访客展现这些特征中的[!UICONTROL OR]any *时，*&#x200B;运算符会评估为true。 当您想要快速创建大量符合条件的网站访客时，[!UICONTROL OR]可能最有用。

**[!UICONTROL AND NOT]用例示例**

当通过[!UICONTROL AND NOT]排除项&#x200B;*而不是*&#x200B;包含项&#x200B;*来定义受众时，*&#x200B;运算符很有用。 例如，假设您正在开展销售，并且希望将访客划分为仅查看全价项目的客户。 不是为所有符合条件的全价或销售价项目创建信号列表，而是如果访客&#x200B;*未*&#x200B;看到销售价项目，则可能更容易使访客符合条件。 这在管理上非常高效，因为与全价销售相比，您的售价项目通常更少。 使用布尔值[!UICONTROL NOT]，访客&#x200B;*不得*&#x200B;展示销售信号以获得全价受众成员资格。 相反，[!UICONTROL AND NOT]与[!UICONTROL AND]用例相反，该用例显示受众成员资格如何通过包含来确定（即，访客根据2个明确规定的信号获得资格）。

>[!MORELIKETHIS]
>
>* [在TraitBuilder中使用比较运算符](../features/traits/trait-comparison-operators.md)
>* TraitBuilder表达式中的[运算顺序](../features/traits/trait-operator-precedence.md)
