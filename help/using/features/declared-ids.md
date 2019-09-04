---
description: 声明的ID如何工作、设置过程、代码示例和变量。
keywords: id同步
seo-description: 声明的ID如何工作、设置过程、代码示例和变量。
seo-title: 声明的ID
solution: Audience Manager
title: 声明的ID
uuid: 49bb4f7e-b4 a7-4d87-a29 c-c3 dca036 d2 a3
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# 声明的ID {#declared-ids}

声明的ID如何工作、设置过程、代码示例和变量。

## 声明 ID 定位 {#declared-id-targeting}

通过不使用或接受永久存储机制(如第三方Cookie)的设备或浏览器，与Audience Manager交换用户ID并将其同步。

<!-- declared_id_about.xml -->

## 声明ID定位的目的 {#declared-id-targeting-purpose}

某些浏览器和大多数移动设备不接受第三方cookie。这使得很难保留有关站点访客的信息或分配永久ID。为了解决此问题，Audience Manager使用 [!UICONTROL DIL] 使您能够通过事件调用。[!UICONTROL declared IDs]此外，a可以 [!UICONTROL declared ID] 作为应用于同一用户中所有解决方案的通用ID [!DNL Experience Cloud]。下表描述了ID定位/匹配过程：

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 过程 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>活动电话</b> </td> 
   <td colname="col2"> <p>要工作，您需要 <span class="wintitle"> 在页面上使用DIL </span> 和 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID服务 </a> 代码。<span class="wintitle"> DIL </span> 从 <span class="wintitle"> Experience </span> Cloud ID服务提供的 <code> setVisitorID </code> 函数 <span class="keyword"> 获得声明的ID，并将 </span> 该ID传递给 <span class="keyword"> Audience Manager </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>匹配ID</b> </td> 
   <td colname="col2"> <p>Audience Manager会尝试在我们的系统中与相应ID匹配客户端和访客ID。如果不存在匹配的ID，Audience Manager将创建一个新ID并将其与客户端ID和访问者ID关联。 </p> <p> <p>注意：如果您的ID映射到多个Audience Manager ID，则使用最新映射。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>返回ID</b> </td> 
   <td colname="col2"> <p>Audience Manager将其同步ID写入客户端域或应用程序中的第一方cookie(或其他可寻址存储空间)。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>后续事件调用</b> </td>
   <td colname="col2"> <p>其他活动调用从客户端域读取Audience Manager ID并将其发送到Audience Manager。 </p> </td>
  </tr> 
 </tbody>
</table>

要开始，您需要配置 [!DNL Experience Cloud] ID服务以及 [!UICONTROL DIL] 要用于数据收集的站点上的整个页面。请参阅 [DIL创建](../dil/dil-class-overview/dil-create.md#dil-create) 和 [声明ID变量](../features/declared-ids.md#declared-id-variables)。

## 退出调用 {#opt-out-calls}

[!UICONTROL declared ID] 该流程遵循网站访客偏好来选择退出您的网站受众管理器定位。Audience Manager收到选择退出请求时，由包含错误代码171 [!DNL JSON] 的 [!UICONTROL DCS] 用户返回，消息“遇到的选择退出标记”，而不是Audience Manager用户ID。

* Audience Manager可以在Audience [!UICONTROL declared ID] Manager [!UICONTROL UUID] 中通过Audience [!DNL URL]Manager。
* [!UICONTROL declared ID] 选择退出存储在[！UICCONTRL Profile Cache Server([!UICONTROL PCS])(每合作伙伴)。没有平台级选择退出 [!UICONTROL declared IDs]。此外，Audience Manager还将用户从边缘的特定区域选择退出(选择退出不会跨 [!UICONTROL DCS] 区域)。

有关选择退出数据收集的更多信息，请参阅 [数据隐私](../overview/data-security-and-privacy/data-privacy.md) 。

## 声明的ID退出示例 {#opt-out-examples}

您可以使用和键值对发出 [!UICONTROL declared ID]`d_cid``d_cid_ic` 退出请求。传统参数(如 `d_dpid` 但 `d_dpuuid` 仍有效)被认为已弃用。请参阅 [CID 取代 DPID 和 DPUUID](../reference/cid.md)。In the examples, *italics* indicates a variable placeholder.

### 选择退出CID和CID_ IC

有关描述和语法，请参阅 [声明ID的URL变量和语法](../features/declared-ids.md#variables-and-syntax)。

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选择退出 </th> 
   <th colname="col2" class="entry"> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>数据提供者ID和用户ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>名</i>/demoptout.jpg？d_ cid=123%01987… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>集成代码和用户ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>名</i>/去排票？d_ cid_ ic=456%1321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多 <code> d_ cid </code> 和 <code> d_ cid_ ic </code> 键值对。 </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>名</i>/去排票？d_ cid=123%1987&amp; d_ cid_ ic=456%01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 使用DPID、DPUUID和UUID退出选择退出(已弃用)

这些方法仍然有效，但被认为已弃用。此信息为旧用途和参考提供。旧版选择退出包括：

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选择退出(已弃用) </th> 
   <th colname="col2" class="entry"> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid </code> only </p> </td> 
   <td colname="col2"> <p> <code> DetailID <i></i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合作伙伴级别选择退出 </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid=用户ID&amp; d_ dpid=数据提供者ID </code> </p> <p>将会存储合作伙伴级别选择退出，以便将此 <code> dpid </code> + <code> dpuid </code> 对的最新映射映射到AAM UUID。如果没有以前存在的映射，Audience Manager会检查请求中是否包含AAM UUID，如果该请求中包含AAM UUID，则会使用它存储选择退出。否则，Audience Manager会生成一个新的AAM UUID并在其下面存储选择退出。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuid </code> + <code> d_ dpid </code> 和explicible <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>用户ID和d_ dpuid=数据提供者的用户ID&amp;<i>d_ dpid=数据提供者ID</i></code> </p> <p> <code> d_ uuid </code> 始终优先。如果 <code> dpid </code> + <code> dpuid </code> 组合映射到另一AAM UUID，则选择退出存储在请求( <code> d_ uuid </code>)中传递的AAM UUID下。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 声明ID的变量和语法 {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

下表列出了传入 [!DNL Audience Manager] 数据提供者ID、用户ID或集成代码(如果使用)的键值对。Note, *italics* indicates a variable placeholder. 增加了空格，使它们更易于阅读。

在每个键值对中：

* `=` 符号将键与相关值分开。
* 非打印 [!DNL ASCII] 字符 `%01` 将分隔这些值。

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid=<i>data provider ID</i> %01<i>user ID</i></code> </p> </td> 
   <td colname="col2"> <p>在一个键值对中包含数据提供者ID和关联的唯一用户ID。<code> d_ cid </code> 替换 <code> d_ dpid </code> 和 <code> d_ dpuuid </code>，它们被视为已弃用，但仍受支持。请参阅 <a href="../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid_ ic=<i>integration code</i> %01<i>user ID</i></code> </p> </td> 
   <td colname="col2"> <p>包含一个集成代码和一个关联的唯一用户ID(在一个键值对中)。<code> d_ cid_ ic </code> 替换 <code> d_ dpid </code> 和 <code> d_ dpuuid </code>，它们已弃用，但仍受支持。请参阅 <a href="../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例事件调用 {#sample-event-calls}

鉴于这些键值对及其所需的语法，您应如下所示进行事件调用。

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 活动调用包括 </th> 
   <th colname="col2" class="entry"> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>数据提供者ID和用户ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>名</i>/事件？d_ cid=123%01987… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>集成代码和用户ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>名</i>/事件？d_ cid_ ic=456%1321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多 <code> d_ cid </code> 和 <code> d_ cid_ ic </code> 键值对。 </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>名</i>/事件？d_ cid=123%1987&amp; d_ cid_ ic=456%01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [CID替换DPID和DPUUID](../reference/cid.md)


## 声明的ID变量 {#declared-id-variables}

介绍用于传递声明的ID的 [!UICONTROL DIL] 配置变量 [!DNL Audience Manager.]

## DIL使用Experience Cloud ID服务传递声明ID {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

与 [Experience Cloud ID服务](https://marketing.adobe.com/resources/help/en_US/mcvid/)一起使用时，您不再需要 [!UICONTROL declared IDs] 使用已弃用 `dpid` 的变量和 `dpuuid` 变量。相反， [!UICONTROL DIL] 依赖函数 `visitorService` 的当前版本将从函数中获取函数 [!UICONTROL declared IDs]`setCustomerIDs`[!UICONTROL Experience Cloud ID Service]。For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). 您将调用 `visitorService``DIL.create` 如下所示。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

`namespace` 在键值对中， `MCORG` 是 [!DNL Experience Cloud] 您的组织ID。如果您没有此ID，可以在仪表板的 [!UICONTROL Administration] 部分找到 [!DNL Experience Cloud] 它。您需要管理员权限才能查看此控制板。See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## 已弃用的函数 {#deprecated-functions}

使用最新版本 [!UICONTROL DIL] 的(6.2+)，您无需使用这些键值对 [!UICONTROL declared IDs]即可传入。这是因为 [!UICONTROL DIL] 现在依赖于以上代码示例中所示的 `visitorService` 函数。此函数从 [!UICONTROL declared IDs] 中获取 [!UICONTROL Experience Cloud ID Service]。但是，我们将出于历史和传统目的引用这些变量。有关如何配置 `DIL.create` 以从中获取a [!UICONTROL declared ID] 的示例，请参见下面的代码 [!UICONTROL Visitor ID Service]。
下表描述 `declaredId` 了对象使用的传统变量：

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

### `DPID` 和 `DPUUID`

Audience Manager在我们的系统中比较并 `DPID``DPUUID` 与相应用户ID相匹配。如果ID不存在，Audience Manager将创建新的用户ID并将其同步到 `DPID/DPUUID` 组合。Audience `UUID`Manager匹配或创建一个用户ID后，它将返回该ID， [!DNL JSON] 以响应客户端域(第一方cookie)或其他本地存储中的cookie。

在使用 [!UICONTROL DIL] v6.1或更早版本时调用此函数。但是，已弃用此函数，以支持从中获取 [!UICONTROL declared IDs] 的新版本 [!UICONTROL Experience Cloud ID Service]。

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
>注意，您需要有计划地开发提供和 `d_dpuuid``d_dpid` 键ID值的代码。

### 在DIL实例化后传入ID

>[!NOTE]
>
>如果 [!DNL API] 您使用不同 `declaredID` 组合发出呼叫，则新组合将仅用于该调用。其他常规事件调用将使用原始 `DIL.create``declaredID` 组合。

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 请求/响应示例 {#request-response-examples}

请求将数据提供程序和用户ID发送到Audience Manager：

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

响应返回Audience Manager ID(例如 `UUID`，)，该ID写入页面域中的第一方cookie。

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 不要定位和退出调用 {#do-not-target}

[!UICONTROL declared ID] 该流程遵循网站访客偏好来选择退出您的网站受众管理器定位。Audience Manager收到选择退出请求时，将 [!UICONTROL DCS] 返回一个空 [!DNL JSON] 对象，而不是Audience Manager用户ID。
