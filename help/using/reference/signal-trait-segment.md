---
description: 描述Audience Manager段的组件、用于设置受众资格标准的表达式，以及在事件呼叫中如何传输数据。
seo-description: 描述Audience Manager段的组件、用于设置受众资格标准的表达式，以及在事件呼叫中如何传输数据。
seo-title: 信号、特征和细分
solution: Audience Manager
title: 信号、特征和细分
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 1%

---


# 信号、特征和细分{#signals-traits-and-segments}

描述区段的组 [!DNL Audience Manager] 件、用于设置受众资格标准的表达式，以及事件呼叫中如何传输数据。

<!-- 

c_signal_trait_segment.xml

 -->

**构图和用途**

[!DNL Audience Manager] 数据包括信号、特征、细分和相关资格规则。 数据元素和规则结合起来，创建细分。 区段将站点访客组织到相关组中。 下表定义了段中的三个主要 [!DNL Audience Manager] 组件。

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
   <td colname="col2"> <p>信号是Audience Manager中最小的 <span class="keyword"></span> ，表示为 <a href="../reference/key-value-pairs-explained.md"> 键值对</a>。 </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">关键是定义数据集（如性别、颜色、价格）的常数。 </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">该值是与常数（例如，男／女、绿色、100）相关的变量。 </li> 
    </ul> <p>比较运算符连接键值对并设置它们之间的关系。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product=camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> price&gt;1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type=digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>特性</b> </td> 
   <td colname="col2"> <p>一个或多个信号的组合。 </p> <p>布尔表达式和比较运算符允许您创建特征限定规则。 </p> <p>使用特征和特征组的组合创建精确的资格要求。 </p> </td> 
   <td colname="col3"> <p>根据可用信号，您可以创建“高端相机浏览器”规则，表示为： </p> <p><code> product=camera AND price&gt;1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>区段</b> </td> 
   <td colname="col2"> <p>共享一组通用属性并符合相关特征的用户。 </p> <p>布尔表达式以及最近／频率要求允许您创建细分资格规则。 </p> <p>结合特征和细分规则，创建精确的资格要求。 </p> </td> 
   <td colname="col3"> <p>根据可用的特征和信号，您可以创建表示为： </p> <p><code> (product=camera AND type=digital SLR) OR (price&gt;1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

使用下图记住信号、特征和区段之间的关系。

![](assets/signals-traits-segments.png)

**使用可视化工具和代码编辑器构建特征和细分规则**

客户端使用用户界面中的可视化工具和代码编辑器管理特 [!DNL Audience Manager] 征和细分。 可视化工具允许您使用搜索功能、弹出选项、下拉菜单和拖放功能创建规则。 代码编辑器为高级用户提供了一种有序开发受众分段标准的方法。

**事件调用将数据发送到Audience Manager**

事件调用将数据从您的网站发送到 [!DNL Audience Manager]。 该调用包含请求中的信号、特征和段 [!DNL HTTP] 数据。 事件本身是字符串 `/event` 之后的一 [!DNL URL] 切。 如以下示例所示，此过程只需一个事件调用即可将多个变量传递给 [!DNL Audience Manager]。

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [细分： 目的、构成和规则](../features/segments/segments-purpose.md)

