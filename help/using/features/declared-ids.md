---
description: 声明的ID如何工作、设置过程、代码示例和变量。
keywords: id同步
seo-description: How declared IDs work, set up procedures, code examples, and variables.
seo-title: Declared IDs
solution: Audience Manager
title: 声明的ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: e17eedfb94f2936c61298c44f3d556bae254b2a7
workflow-type: tm+mt
source-wordcount: '1151'
ht-degree: 8%

---

# [!UICONTROL Declared IDs] {#declared-ids}

[!UICONTROL declared IDs]的工作方式、设置过程、代码示例和变量。

## [!UICONTROL Declared ID] 目标 {#declared-id-targeting}

在不使用或接受永久存储机制的设备或浏览器（如第三方[!DNL Audience Manager]）中，将用户ID与[!DNL cookies]交换并同步。

## [!UICONTROL Declared ID]定位的目的 {#declared-id-targeting-purpose}

某些浏览器和大多数移动设备不接受第三方[!DNL cookies]。 这使得保留有关网站访客的信息或分配永久ID变得困难。 要解决此问题，[!DNL Audience Manager]使用[!UICONTROL DIL]允许您在事件调用中传入[!UICONTROL declared IDs]。 此外，[!UICONTROL declared ID]可以充当通用ID，在[!DNL Experience Cloud]的所有解决方案中应用于同一用户。 下表介绍了ID定位/匹配过程：

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
   <td colname="col2"> <p>要正常工作，您需要在页面上安装<span class="wintitle"> DIL </span>和<a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity服务</a>代码。 <span class="wintitle"> DIL </span>从<span class="wintitle"> Adobe Experience Platform Identity服务</span>提供的<code> setVisitorID </code>函数中获取<span class="keyword">个声明的ID </span>，并将其传递到<span class="keyword"> Audience Manager </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>匹配ID</b> </td> 
   <td colname="col2"> <p>Audience Manager会尝试将客户端和访客ID与系统中的相应ID进行匹配。 如果不存在匹配的ID，Audience Manager会创建一个新的ID，并将其与客户端和访客ID关联。 </p> <p> <p>注意：如果您的ID映射到多个Audience Manager ID，则使用最近的映射。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>返回ID</b> </td> 
   <td colname="col2"> <p>Audience Manager将其同步ID写入客户端域或应用程序中的第一方Cookie（或其他可寻址存储空间）。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>后续事件调用</b> </td>
   <td colname="col2"> <p>其他事件调用将从客户端域中读取Audience Manager ID并将其发送给Audience Manager。 </p> </td>
  </tr> 
 </tbody>
</table>

若要开始，您需要在要用于数据收集的网站页面上配置[!DNL Experience Cloud] ID服务和[!UICONTROL DIL]。 请参阅[DIL创建](../dil/dil-class-overview/dil-create.md#dil-create)和[声明的ID变量](../features/declared-ids.md#declared-id-variables)。

## 选择退出调用 {#opt-out-calls}

[!UICONTROL declared ID]进程遵循网站访客首选项以选择退出由您的网站定位的[!DNL Audience Manager]。 当[!DNL Audience Manager]收到选择退出请求时，[!DNL JSON]返回的[!DNL DCS]包含错误代码171，消息为`Encountered opt out tag`，而不是[!DNL Audience Manager]用户ID。

* [!DNL Audience Manager]可以在[!UICONTROL declared ID]中与[!DNL Audience Manager] [!UICONTROL UUID]一起传递[!DNL URL]选择退出。
* [!UICONTROL declared ID]选择退出以每个合作伙伴为基础存储在[!UICONTROL Profile Cache Server] ([!UICONTROL PCS])中。 没有使用[!UICONTROL declared IDs]的平台级别选择退出。 此外，[!DNL Audience Manager]会从边缘上的该特定区域选择退出用户（选择退出不会跨越[!DNL DCS]区域）。

有关选择退出数据收集的详细信息，请参阅[数据隐私](../overview/data-security-and-privacy/data-privacy.md)。

## [!UICONTROL Declared ID]个选择退出示例 {#opt-out-examples}

您可以使用[!UICONTROL declared ID]和`d_cid`键值对发出`d_cid_ic`个选择退出请求。 虽然旧版参数（如 `d_dpid` 和 `d_dpuuid`）仍然可用，但已考虑将其弃用。请参阅 [CID 取代 DPID 和 DPUUID](../reference/cid.md)。在示例中，*斜体*&#x200B;表示变量占位符。

### 通过[!UICONTROL CID]和[!UICONTROL CID_IC]选择退出

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

### 通过[!UICONTROL DPID]、[!UICONTROL DPUUID]和[!UICONTROL UUID]选择退出（已弃用）

这些方法仍然有效，但被视为已弃用。 提供此信息是为了方便旧版使用和参考。 旧版选择退出功能包括：

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选择禁用（已弃用） </th> 
   <th colname="col2" class="entry"> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 仅<code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合作伙伴级别的选择退出 </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>为该<code> dpid </code> + <code> dpuuid </code>对到AAM UUID的最新映射存储了合作伙伴级别的选择退出。 如果之前没有映射，Audience Manager会检查请求在Cookie中是否包含AAM UUID，如果包含，则使用该UUID存储选择退出。 否则，Audience Manager会生成一个新的AAM UUID并将选择退出存储在该UUID下。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code>和显式<code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code>始终优先。 如果<code> dpid </code> + <code> dpuuid </code>组合映射到另一个AAM UUID，则选择退出存储在请求中传递的AAM UUID下(<code> d_uuid </code>)。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared IDs]的变量和语法 {#variables-and-syntax}

下表列出了传递您的[!DNL Audience Manager]数据提供程序ID和用户ID或集成代码（如果已使用）的键值对。 请注意，*斜体*&#x200B;表示变量占位符。 已添加空格以使其更易于阅读。

在每个键值对中：

* `=`符号将键与其相关值分开。
* 非打印[!DNL ASCII]字符`%01`用于分隔值。

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
   <td colname="col2"> <p>在一个键值对中包含数据提供程序ID和关联的唯一用户ID。 <code> d_cid </code>替换了<code> d_dpid </code>和<code> d_dpuuid </code>，它们被视为已弃用，但仍受支持。 请参阅<a href="../reference/cid.md"> CID取代DPID和DPUUID </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>在单个键值对中包含集成代码和关联的唯一用户ID。 <code> d_cid_ic </code>替换了<code> d_dpid </code>和<code> d_dpuuid </code>，这两个名称已弃用，但仍受支持。 请参阅<a href="../reference/cid.md"> CID取代DPID和DPUUID </a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例事件调用 {#sample-event-calls}

根据这些键值对及其所需语法，您可以进行如下所示的事件调用。

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 事件调用包括 </th> 
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

描述用于将[!UICONTROL declared IDs]通过[!UICONTROL DIL]传递到[!DNL Audience Manager.]的配置变量

## [!UICONTROL DIL]使用[!DNL Adobe Experience Platform Identity Service]传递[!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

与[Adobe Experience Platform Identity服务](https://experienceleague.adobe.com/docs/id-service/using/home.html)一起使用时，您不再需要通过已弃用的[!UICONTROL declared IDs]和`dpid`变量传入`dpuuid`。 相反，[!UICONTROL DIL]的当前版本依赖于`visitorService`函数从[!UICONTROL declared IDs]中的`setCustomerIDs`函数获取[!UICONTROL Adobe Experience Platform Identity Service]。 有关详细信息，请参阅[客户ID和身份验证状态](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)。 您应在`visitorService`中调用`DIL.create`，如下所示。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

在`namespace`键值对中，`MCORG`是您的[!DNL Experience Cloud]组织ID。 如果您没有此ID，则可以在[!UICONTROL Administration]仪表板的[!DNL Experience Cloud]部分中找到它。 您需要管理员权限才能查看此仪表板。 请参阅[开始使用Experience Cloud服务](https://experienceleague.adobe.com/en/docs/core-services/interface/services/getting-started)。

## 已弃用的函数 {#deprecated-functions}

对于最新版本的[!UICONTROL DIL] (6.2+)，您无需使用这些键值对即可传入[!UICONTROL declared IDs]。 这是因为[!UICONTROL DIL]现在依赖于上面代码示例中显示的`visitorService`函数。 此函数从[!UICONTROL declared IDs]获取[!UICONTROL Adobe Experience Platform Identity Service]。 但是，出于历史和旧版目的，我们在此引用这些变量。 有关如何配置`DIL.create`以从[!UICONTROL declared ID]获取[!UICONTROL Visitor ID Service]的示例，请参阅下面的代码。
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
   <td colname="col3"> <p>Audience Manager分配的数据合作伙伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> 字符串 </td> 
   <td colname="col3"> <p>用户的唯一数据提供程序 ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] 和 [!UICONTROL DPUUID]

[!DNL Audience Manager]将组合的`DPID`和`DPUUID`与系统中的相应用户ID进行比较和匹配。 如果ID不存在，[!DNL Audience Manager]将创建一个新的用户ID并将其同步到`DPID/DPUUID`组合。 在[!DNL Audience Manager]匹配或创建用户ID (`UUID`)后，它会在对客户端域（第一方[!DNL JSON]）或其他本地存储中的[!DNL cookie]的[!DNL cookie]响应中返回该ID。

当您使用[!UICONTROL DIL] v6.1或更早版本时，调用此函数。 但是，此函数已弃用，支持从[!UICONTROL declared IDs]获取[!DNL Adobe Experience Platform Identity Service]的新版本。

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
>您需要以编程方式开发用于提供`d_dpuuid`和`d_dpid`键的ID值的代码。

### 在[!UICONTROL DIL]实例化后传递ID

>[!NOTE]
>
>如果您使用不同的[!DNL API]组合进行`declaredID`调用，则新组合将仅用于该调用。 进一步的常规事件调用将使用原始`DIL.create` `declaredID`组合。

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 请求/响应示例 {#request-response-examples}

该请求向[!DNL Audience Manager]发送数据提供程序和用户ID：

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

响应将返回写入页面域中的第一方Cookie的Audience Manager ID（例如`UUID`）。

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 不定位和选择退出调用 {#do-not-target}

[!UICONTROL declared ID]进程遵循网站访客首选项以选择退出由您的网站定位的[!DNL Audience Manager]。 当[!DNL Audience Manager]收到选择退出请求时，[!DNL DCS]返回空的[!DNL JSON]对象，而不是[!DNL Audience Manager]用户ID。

>[!MORELIKETHIS]
>
>* [CID 取代 DPID 和 DPUUID](../reference/cid.md)
