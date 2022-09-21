---
description: 这是一个可选的布尔型配置，用于确定 DIL 是否会将数据发送到 Adobe Experience Cloud 设备协作。
seo-description: An optional, Boolean configuration that determines if DIL sends (or does not send) data to the Adobe Experience Cloud Device Co-op.
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: c5362a38-93c0-4edb-bdcb-106e43f33a92
feature: DIL Implementation
exl-id: 33dca495-6923-4966-9ec3-8b0fd2f17649
hide: true
hidefromtoc: true
index: n
source-git-commit: 3f4a161ee856357b5cb5eb757ad779dee5357b09
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 76%

---

# isCoopSafe{#iscoopsafe}

>[!WARNING]
>
>此功能已被弃用。

这是一个可选的布尔型配置，用于确定 DIL 是否会将数据发送到 Adobe Experience Cloud 设备协作。

## 要求 {#requirements}

使用 `isCoopSafe` 您必须：

* 使用 [!UICONTROL DIL] v6.11或更高版本。
* 参与 [Experience Cloud 设备协作](https://experienceleague.adobe.com/docs/device-co-op/using/home.html)。潜在的协作成员也应查阅此文档，以确定 `isCoopSafe` 是否可以解决可能与如何使用数据来创建设备图有关的问题。

* 使用 [!DNL Adobe] 顾问，以在您允许列表的设备协阻止列表作帐户中设置或标记。 没有启用这些标志的自助路径。

## 用例 {#use-cases}

`isCoopSafe` 可帮助解决以下 2 个与设备协作的当前成员或潜在成员进行的收集数据有关的用例。这两个用例与如何将网站访客数据传递到设备协作以帮助构建设备图有关。下表描述了 `isCoopSafe` 如何在这两个用例中使用，以阻止数据发送至设备图或将数据发送至设备图。

<table id="table_A24C63D2A21F47EDBAC8FA5E7BE888D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>经过身份验证的访客</b> </p> </td> 
   <td colname="col2"> <p>添加 <code> isCoopSafe </code> 至 <span class="wintitle"> DIL </span> 用于控制设备协作如何使用经过身份验证的访客（已接受或未接受使用条款协议）的数据来构建设备图。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>第三方网站上的 DIL</b> </p> </td> 
   <td colname="col2"> <p>添加 <code> isCoopSafe </code> 至 <span class="wintitle"> DIL </span> 用于第三方网站的代码，其中： </p> <p> 
     <ul id="ul_C27BB26510314834A2A7CD99D46DA4AC"> 
      <li id="li_4E6AE574F18646F09C0CF4553EEA1A9E">您无法确保经过身份验证的访客是否已接受使用条款协议。 </li> 
      <li id="li_26D0561BF32B4278B0A6B5082C17FED8">您需要控制设备协作如何使用该数据来构建设备图。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 语法和代码示例 {#syntax-code-sample}

**语法：**`isCoopSafe: true | false`

布尔选项可确定设备协作是否可以使用客户数据。

* `isCoopSafe: true`：通过 Mobile SDK 或网站收集的访客数据&#x200B;*可以*&#x200B;用来帮助构建设备图。

* `isCoopSafe: false`：通过 Mobile SDK 或网站收集的访客数据&#x200B;*不能*&#x200B;用来帮助构建设备图。

**代码示例**

在DIL实例化时设置此设置。

```js
var dilInstance = DIL.create({ 
     ... 
     isCoopSafe: true 
});
```

## 事件调用 POST 参数 {#post-parameters}

根据您设置的标记( `true` 或 `false`)、 [!UICONTROL DIL] 转换 `isCoopSafe` 并将其发送到这些POST参数 [!DNL Adobe] 在事件调用中：

* `d_coop_safe=1`
* `d_coop_unsafe=1`

这两个 POST 参数告知 [!DNL Experience Cloud] 设备协作是否可以在设备图中包含用户数据。下表定义了 `isCoopSafe` 布尔标记与在事件调用中传入的 POST 参数之间的关系。如果您没有使用 `isCoopSafe`，则无法在事件调用中传递这两个参数。

<table id="table_0A544534CA904F4D9836A34B8C1EACBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 配置状态 </th> 
   <th colname="col2" class="entry"> POST 参数 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: true </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_safe=1 </code> </p> <p>设备协作可以使用访客数据来帮助构建设备图。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: false </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_unsafe=1 </code> </p> <p>设备协作不能使用访客数据来帮助构建设备图。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 实例化后 API {#post-instantiation}

这些 API 允许您覆盖 `isCoopSafe` 状态。这些 API 是必需的，因为它们允许您在页面没有刷新的网站或单页应用程序上更改访客的实例化后/登录后状态。例如，如果用户在您的网站或应用程序中进行了身份验证，且随后接受了允许设备协作使用其数据的使用条款政策，则您将需要调用这些 API。

<table id="table_BAA96B1F82BE48C3A61A1AF1367BA45C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopSafe(); </code> </p> </td> 
   <td colname="col2"> <p>设置POST参数 <code> d_coop_safe=1 </code> 在所有后续事件调用中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopUnsafe(); </code> </p> </td> 
   <td colname="col2"> <p>设置POST参数 <code> d_coop_unsafe=1 </code> 在所有后续事件调用中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- 

Wiki page https://wiki.corp.adobe.com/x/RCfFTg

 -->
