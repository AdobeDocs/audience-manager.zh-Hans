---
description: 本文介绍Audience manager特征和区段工具如何使用布尔表达式AND、OR和NOT。
seo-description: 本文介绍Audience manager特征和区段工具如何使用布尔表达式AND、OR和NOT。
seo-title: Trait和Segment Builder中的布尔表达式
solution: Audience Manager
title: Trait和Segment Builder中的布尔表达式
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Trait和Segment Builder中的布尔表达式{#boolean-expressions-in-trait-and-segment-builder}

本文介绍Audience manager特征和区段工具如何使用布尔表达式AND、OR和NOT。

<!-- 

c_tb_boolean.xml

 -->

**布尔表达式**

Boolean逻辑是代数的一个分支，它使用一些基本表达式（或运算符）来确定语句是真还是假。 最常见的操作符 [!UICONTROL AND]有、 [!UICONTROL OR]和 [!UICONTROL NOT]。 这些表达式的组合可帮助您制作出专门针对您的数据要求的特征或细分资格规则。 下图显示了基本的Boolean表达式的工作方式。

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>运 [!UICONTROL NOT] 算符使用默示的“and”条件，有时编写为 [!UICONTROL AND NOT]。

**如何在Trait和Segment Builder中使用Boolean表达式**

您可以使用Boolean表达式构建特征和区段资格规则。 下表介绍了使用、和创建资格标准的一 [!UICONTROL AND]般最 [!UICONTROL OR]佳实践 [!UICONTROL NOT]。

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
   <td colname="col1"> <p><b><span class="wintitle"> AND</span></b> </p> </td> 
   <td colname="col2"> <p>缩小重点受众资格要求。 </p> </td> 
   <td colname="col3"> <p>用户 <i>必须属于</i> 所有指定的特征或区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 或</span></b> </p> </td> 
   <td colname="col2"> <p>广泛、不太集中的受众资格要求。 </p> </td> 
   <td colname="col3"> <p>用 <i>户可</i> 属于任何指定的特征或区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>缩小重点受众资格要求。 </p> <p>当存在多种导致定义受众资格要求难以或效率低下的条件时很有用。 有时，根据排除而非包含的要求进行验证会更加容易。 </p> </td> 
   <td colname="col3"> <p>用 <i>户不得属</i> 于被排除的特征或区段。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]用例示例**

当您 [!UICONTROL AND] 轻松列举了特征成员资格要求时，该运算符很有用。 例如，假设您需要创建“昂贵的相机购物者”的受众。使用像素模型，您必须为相机创建和放置像素，并在页面上设置数字价格值。 相反，通过特征，您可以应用Boolean运算符来处理这两种情况(相机 [!UICONTROL AND] 价格)。 结果是，使用更少的HTTP调用高效地收集数据，这反过来又有助于保留您网站上的用户体验。

**[!UICONTROL OR]用例示例**

当您 [!UICONTROL OR] 希望创建具有广泛受众资格要求的信号时，该运营商很有用。 如果您有几个特征或区段资格要求，则当您的 [!UICONTROL OR] 网站访问者显示任何这些特征时，此运 *算符将* 评估为true。 [!UICONTROL OR] 当您希望快速创建大量合格网站访客时，可能最有用。

**[!UICONTROL AND NOT]用例示例**

当通 [!UICONTROL AND NOT] 过排除而非包含来更轻松地定义受众时，此运 *算符很* 有用 **。 例如，假设您正在进行销售，并且希望将访客细分为仅查看完整价格项目的客户。 如果访客没有看到销售价格项目，则可能更容易确定访问者的资 *格* ，而不是为所有符合条件的完整或销售价格项目创建信号列表。 这在管理上是有效的，因为与全价提供的产品相比，您的售价项目通常更少。 使用布尔 [!UICONTROL NOT]值时，访 *客不得显示* “销售信号”，以获得全价受众会员资格。 相反， [!UICONTROL AND NOT][!UICONTROL AND] 这与用例相反，用于显示如何通过包含（即，根据2个明确声明的信号确定访客资格）来确定受众成员资格。

>[!MORELIKETHIS]
>
>* [在TraitBuilder中使用比较运算符](../features/traits/trait-comparison-operators.md)
>* [TraitBuilder表达式中的操作顺序](../features/traits/trait-operator-precedence.md)

