---
description: 描述Audience Manager区段的组件、用于设置受众资格标准的表达式以及在事件调用中传输数据的方式。
seo-description: 描述Audience Manager区段的组件、用于设置受众资格标准的表达式以及在事件调用中传输数据的方式。
seo-title: 信号、特征和区段
solution: Audience Manager
title: 信号、特征和区段
uuid: 485cfc5c-b289-463b-a610-0d727 df90 f3 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Signals, Traits, and Segments{#signals-traits-and-segments}

描述Audience Manager区段的组件、用于设置受众资格标准的表达式以及在事件调用中传输数据的方式。

<!-- 

c_signal_trait_segment.xml

 -->

**合成和用途**

[!DNL Audience Manager] 数据包括信号、特征、细分和相关资质规则。数据元素和规则组合以创建区段。区段可将站点访客组织到相关组中。The following table defines the three principal components in an [!DNL Audience Manager] segment.

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 由 </th> 
   <th colname="col3" class="entry"> 示例 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>信号</b> </td> 
   <td colname="col2"> <p>Signals are the smallest data units in <span class="keyword"> Audience Manager</span> and are expressed as <a href="../reference/key-value-pairs-explained.md"> key-value pairs</a>. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">该键是定义数据集(例如性别、颜色、价格)的常数。 </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">该值是与常数相关的变量(例如，男性/女性、绿色、100)。 </li> 
    </ul> <p>比较运算符加入键值对并设置它们之间的关系。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product= camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> price&gt;1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type= digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>特性</b> </td> 
   <td colname="col2"> <p>一个或多个信号的组合。 </p> <p>Boolean表达式和比较运算符允许您创建特征资格规则。 </p> <p>通过特征组和特征组组合创建精确的资格要求。 </p> </td> 
   <td colname="col3"> <p>在可用信号中，您可以创建一个“高端相机浏览器”规则，该规则表示为： </p> <p><code> product= camera and price&gt;1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>区段</b> </td> 
   <td colname="col2"> <p>共享一组常用属性并符合相关特征的用户。 </p> <p>Boolean表达式以及新近度/频率要求允许您创建细分资格规则。 </p> <p>通过特征和细分规则组合创建精确的资格要求。 </p> </td> 
   <td colname="col3"> <p>从可用的特征和信号中，您可以创建区段规则，以： </p> <p><code> (product= camera AND type= digital SLR) OR(price&gt;1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

使用下图，明确说明信号、特征和细分之间的关系。

![](assets/signals-traits-segments.png)

**使用可视工具和代码编辑器构建特征和区段规则**

Clients manage traits and segments with visual tools and code editors in the [!DNL Audience Manager] user interface. 可视工具可让您使用搜索功能、弹出选项、下拉菜单和拖放功能创建规则。代码编辑器为高级用户提供了一种编程开发受众细分标准的方法。

**事件调用将数据发送到Audience Manager**

An event call sends data from your website to [!DNL Audience Manager]. 该调用包含HTTP请求中的信号、特征和区段数据。The event itself is everything after the `/event` part of a URL string. As shown in the example below, this process requires only a single event call to pass in multiple variables to [!DNL Audience Manager].

```
https://<domain>/event?product=camera&price>100
```

>[!MORE_ LIKE_ This]
>
>* [区段：用途、构图和规则](../features/segments/segments-purpose.md)

