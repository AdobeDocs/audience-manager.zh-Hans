---
description: 声明的ID的工作方式、设置过程、代码示例和变量。
keywords: id同步
seo-description: 声明的ID的工作方式、设置过程、代码示例和变量。
seo-title: 声明的 ID
solution: Audience Manager
title: 声明的 ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID同步
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1183'
ht-degree: 9%

---

# [!UICONTROL Declared IDs] {#declared-ids}

[!UICONTROL declared IDs]的工作方式、设置过程、代码示例和变量。

## [!UICONTROL Declared ID] 目标 {#declared-id-targeting}

使用或接受永久存储机制（如第三方[!DNL cookies]）的设备或浏览器中的[!DNL Audience Manager]与用户ID进行交换和同步。

## [!UICONTROL Declared ID]定位的用途 {#declared-id-targeting-purpose}

某些浏览器和大多数移动设备不接受第三方[!DNL cookies]。 这使得很难保留有关网站访客或分配永久ID的信息。 要解决此问题，[!DNL Audience Manager]使用[!UICONTROL DIL]在事件调用中允许您传入[!UICONTROL declared IDs]。 此外，[!UICONTROL declared ID]可以充当一个通用ID，该ID适用于[!DNL Experience Cloud]中所有解决方案中的同一用户。 下表介绍了ID定位/匹配流程：

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 过程 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>事件调用</b> </td> 
   <td colname="col2"> <p>要使用，您需要页面上的<span class="wintitle">DIL</span>和<a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>代码。 <span class="wintitle"> DIL </span> 从Adobe Experience Platform  <span class="wintitle"> Identity Service </span> 提供 <code> setVisitorID </code> 的函数中获取 <span class="keyword"> 声明的 </span> ID，并将其传递 <span class="keyword"> 到Audience Manager </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>匹配ID</b> </td> 
   <td colname="col2"> <p>Audience Manager会尝试将客户端ID和访客ID与我们系统中的相应ID进行匹配。 如果不存在匹配的ID，则Audience Manager会创建一个新ID，并将其与客户端ID和访客ID关联。 </p> <p> <p>注意： 如果您的ID映射到多个Audience ManagerID，则会使用最新的映射。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>返回ID</b> </td> 
   <td colname="col2"> <p>Audience Manager将其同步的ID写入客户端域或应用程序中的第一方Cookie（或其他可寻址存储空间）。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>后续事件调用</b> </td>
   <td colname="col2"> <p>其他事件调用会从客户端的域中读取Audience ManagerID，并将其发送给Audience Manager。 </p> </td>
  </tr> 
 </tbody>
</table>

要开始配置，您需要在网站上要用于数据收集的页面上配置[!DNL Experience Cloud] ID服务和[!UICONTROL DIL]。 请参阅[DIL创建](../dil/dil-class-overview/dil-create.md#dil-create)和[声明的ID变量](../features/declared-ids.md#declared-id-variables)。

## 选择退出调用 {#opt-out-calls}

[!UICONTROL declared ID]过程遵循网站访客首选项来选择退出您网站的[!DNL Audience Manager]定位。 当[!DNL Audience Manager]收到选择退出请求时，由[!DNL DCS]返回的[!DNL JSON]包含错误代码171，消息为`Encountered opt out tag`，而不是[!DNL Audience Manager]用户ID。

* [!DNL Audience Manager] 可以在中 [!UICONTROL declared ID] 传递选择退 [!DNL Audience Manager] [!UICONTROL UUID] 出和 [!DNL URL]。
* [!UICONTROL declared ID]选择退出按合作伙伴存储在[!UICONTROL Profile Cache Server]([!UICONTROL PCS])中。 没有使用[!UICONTROL declared IDs]的平台级别选择退出。 此外，[!DNL Audience Manager]会从边缘上的特定区域选择用户退出（选择退出不会跨[!DNL DCS]区域）。

有关选择退出数据收集的更多信息，请参阅[数据隐私](../overview/data-security-and-privacy/data-privacy.md)。

## [!UICONTROL Declared ID] 选择退出示例 {#opt-out-examples}

您可以使用`d_cid`和`d_cid_ic`键值对发出[!UICONTROL declared ID]选择退出请求。 虽然旧版参数（如 `d_dpid` 和 `d_dpuuid`）仍然可用，但已考虑将其弃用。请参阅 [CID 取代 DPID 和 DPUUID](../reference/cid.md)。在示例中，*斜体*&#x200B;表示变量占位符。

### 使用[!UICONTROL CID]和[!UICONTROL CID_IC]选择退出

有关说明和语法，请参阅[已声明 ID 的 URL 变量和语法](../features/declared-ids.md#variables-and-syntax)。

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选择退出请求所用方式 </th> 
   <th colname="col2" class="entry"> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>数据提供商 ID 和用户 ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>集成代码和用户 ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多个<code> d_cid </code>和<code> d_cid_ic </code>键值对。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 选择退出条件：[!UICONTROL DPID]、[!UICONTROL DPUUID]和[!UICONTROL UUID]（已弃用）

这些方法仍可用，但视为已弃用。 此信息仅供旧版参考之用。 旧版选择退出包括：

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选择退出（已弃用） </th> 
   <th colname="col2" class="entry"> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> 在 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合作伙伴级别的选择退出 </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>将存储合作伙伴级别的选择退出，以便将此<code> dpid </code> + <code> dpuuid </code>对的最新映射到AAM UUID。 如果之前没有现有映射，则Audience Manager会检查请求在Cookie中是否包含AAM UUID，如果包含，则会使用该UUID来存储选择退出。 否则，Audience Manager会生成一个新的AAM UUID，并将选择退出存储在该UUID下。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> 和显式  <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> 始终优先。如果<code> dpid </code> + <code> dpuuid </code>组合映射到其他AAM UUID，则选择退出会存储在请求中传递的AAM UUID(<code> d_uuid </code>)下。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared IDs]的变量和语法 {#variables-and-syntax}

下表列出了在[!DNL Audience Manager]数据提供程序ID和用户ID或集成代码（如果使用）中传递的键值对。 请注意， *斜体*&#x200B;表示变量占位符。 添加了空格，以便更便于阅读。

在每个键值对中：

* `=`符号将键值与其相关值分隔开。
* 非打印的[!DNL ASCII]字符`%01`用于分隔值。

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid =<i>data provider ID</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>在单个键值对中包含数据提供程序ID和关联的唯一用户ID。 <code> d_cid </code> 替换 <code> d_dpid </code> 和 <code> d_dpuuid </code>，后者被视为已弃用，但仍受支持。请参阅 <a href="../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>在单个键值对中包含集成代码和关联的唯一用户ID。 <code> d_cid_ic </code> 替换 <code> d_dpid </code> 和 <code> d_dpuuid </code>，尽管已弃用但仍受支持。请参阅 <a href="../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 事件调用示例 {#sample-event-calls}

鉴于这些键值对及其所需的语法，您将发起事件调用，如下所示。

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 事件调用包含 </th> 
   <th colname="col2" class="entry"> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>数据提供商 ID 和用户 ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>集成代码和用户 ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多个<code> d_cid </code>和<code> d_cid_ic </code>键值对。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] 变量 {#declared-id-variables}

描述用于将[!UICONTROL declared IDs]传递到[!UICONTROL DIL]到[!DNL Audience Manager.]的配置变量

## [!UICONTROL DIL] 使用 [!DNL Adobe Experience Platform Identity Service] 传递  [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

与[Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)一起使用时，您不再需要使用已弃用的`dpid`和`dpuuid`变量传入[!UICONTROL declared IDs]。 相反，当前版本的[!UICONTROL DIL]依赖于`visitorService`函数从[!UICONTROL Adobe Experience Platform Identity Service]的`setCustomerIDs`函数中获取[!UICONTROL declared IDs]。 有关更多信息，请参阅[客户ID和身份验证状态](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)。 您将在`DIL.create`中调用`visitorService`，如下所示。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

在`namespace`键值对中，`MCORG`是您的[!DNL Experience Cloud]组织ID。 如果您没有此ID，可以在[!DNL Experience Cloud]功能板的[!UICONTROL Administration]部分找到此ID。 您需要管理员权限才能查看此功能板。 请参阅[管理：核心服务](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html)。

## 已弃用的函数 {#deprecated-functions}

对于最新版本的[!UICONTROL DIL](6.2+)，您无需使用这些键值对即可传入[!UICONTROL declared IDs]。 这是因为[!UICONTROL DIL]现在依赖于上述代码示例中显示的`visitorService`函数。 此函数从[!UICONTROL Adobe Experience Platform Identity Service]获取[!UICONTROL declared IDs]。 但是，我们在此处将引用这些变量以用于历史和旧版目的。 有关如何配置`DIL.create`以从[!UICONTROL Visitor ID Service]获取[!UICONTROL declared ID]的示例，请参阅以下代码。
下表描述了`declaredId`对象使用的旧版变量：

<table id="table_A1884B72950F4BBDA87F17DDFF173628"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名称 </th> 
   <th colname="col2" class="entry"> 类型 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> 字符串 </td> 
   <td colname="col3"> <p>由Audience Manager分配的数据合作伙伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> 字符串 </td> 
   <td colname="col3"> <p>用户的唯一数据提供程序 ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] 和 [!UICONTROL DPUUID]

[!DNL Audience Manager] 将和组合的与 `DPID` 匹 `DPUUID` 配到我们系统中的相应用户ID。如果ID不存在，则[!DNL Audience Manager]会创建一个新的用户ID，并将其同步到`DPID/DPUUID`组合。 在[!DNL Audience Manager]匹配或创建用户ID(`UUID`)后，它会在对客户端域（第一方[!DNL cookie]）或其他本地存储中的[!DNL cookie]的[!DNL JSON]响应中返回该ID。

使用[!UICONTROL DIL] v6.1或更低版本时，请调用此函数。 但是，此函数已被弃用，取而代之的是从[!DNL Adobe Experience Platform Identity Service]中获取[!UICONTROL declared IDs]的新版本。

```js
DIL.create({
    partner : "partner name",
    declaredId : {
       dpuuid : dpuuid,
       DPID : dpid
    }
 });
```

>[!NOTE]
>
>您需要以编程方式开发提供`d_dpuuid`和`d_dpid`键ID值的代码。

### 在[!UICONTROL DIL]实例化之后传递ID

>[!NOTE]
>
>如果您使用不同的`declaredID`组合进行[!DNL API]调用，则新组合将仅用于该调用。 进一步的常规事件调用将使用原始的`DIL.create` `declaredID`组合。

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 请求/响应示例 {#request-response-examples}

该请求会向[!DNL Audience Manager]发送数据提供程序和用户ID:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

响应会返回Audience ManagerID（例如`UUID`），该ID会写入页面域中的第一方Cookie。

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 不定位和选择退出调用 {#do-not-target}

[!UICONTROL declared ID]过程遵循网站访客首选项来选择退出您网站的[!DNL Audience Manager]定位。 当[!DNL Audience Manager]收到选择退出请求时，[!DNL DCS]会返回空的[!DNL JSON]对象，而不是[!DNL Audience Manager]用户ID。

>[!MORELIKETHIS]
>
>* [CID 取代 DPID 和 DPUUID](../reference/cid.md)

