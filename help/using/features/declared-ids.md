---
description: 声明的ID如何工作、设置过程、代码示例和变量。
keywords: id同步
seo-description: 声明的ID如何工作、设置过程、代码示例和变量。
seo-title: 声明的ID
solution: Audience Manager
title: 声明的ID
uuid: 49bb4f7e-b4 a7-4d87-a29 c-c3 dca036 d2 a3
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Declared IDs {#declared-ids}

声明的ID如何工作、设置过程、代码示例和变量。

## 声明 ID 定位 {#declared-id-targeting}

通过不使用或接受永久存储机制(如第三方Cookie)的设备或浏览器，与Audience Manager交换用户ID并将其同步。

<!-- declared_id_about.xml -->

## Purpose of Declared ID Targeting {#declared-id-targeting-purpose}

某些浏览器和大多数移动设备不接受第三方cookie。这使得很难保留有关站点访客的信息或分配永久ID。To resolve this issue, Audience Manager uses [!UICONTROL DIL] to let you pass in [!UICONTROL declared IDs] on an event call. Also, a [!UICONTROL declared ID] can act as a universal ID that applies to the same user across all the solutions in the [!DNL Experience Cloud]. 下表描述了ID定位/匹配过程：

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
   <td colname="col2"> <p>To work, you need <span class="wintitle"> DIL </span> and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID service </a> code on the page. <span class="wintitle"> DIL </span> 从 <span class="wintitle"> Experience </span> Cloud ID服务提供的 <code> setVisitorID </code> 函数 <span class="keyword"> 获得声明的ID，并将 </span> 该ID传递给 <span class="keyword"> Audience Manager </span>。 </p> </td> 
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

To get started, you need to configure the [!DNL Experience Cloud] ID service and [!UICONTROL DIL] across the pages on your site that you want to use for data collection. See [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) and [Declared ID Variables](../features/declared-ids.md#declared-id-variables).

## Opt-out Calls {#opt-out-calls}

[!UICONTROL declared ID] 该流程遵循网站访客偏好来选择退出您的网站受众管理器定位。When Audience Manager receives an opt-out request, the [!DNL JSON] returned by the [!UICONTROL DCS] contains the error code 171, with the message &quot;Encountered opt out tag&quot;, instead of the Audience Manager user ID.

* Audience Manager can pass in a [!UICONTROL declared ID] opt-out alongside an Audience Manager [!UICONTROL UUID] in the [!DNL URL].
* [!UICONTROL declared ID] 选择退出存储在[！UICCONTRL Profile Cache Serveur([!UICONTROL PCS])(每合作伙伴)。There is no platform-level opt-out using [!UICONTROL declared IDs]. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross [!UICONTROL DCS] regions).

See [Data Privacy](../overview/data-security-and-privacy/data-privacy.md) for more information about opting-out of data collection.

## Declared ID Opt-Out Examples {#opt-out-examples}

You can make a [!UICONTROL declared ID] opt-out requests with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. 请参阅 [CID 取代 DPID 和 DPUUID](../reference/cid.md)。In the examples, *italics* indicates a variable placeholder.

### 选择退出CID和CID_ IC

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

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
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid=用户ID&amp; d_ dpid=数据提供者ID </code> </p> <p>A partner level opt-out gets stored for the latest mapping of this <code> dpid </code> + <code> dpuuid </code> pair to an AAM UUID. 如果没有以前存在的映射，Audience Manager会检查请求中是否包含AAM UUID，如果该请求中包含AAM UUID，则会使用它存储选择退出。否则，Audience Manager会生成一个新的AAM UUID并在其下面存储选择退出。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuid </code> + <code> d_ dpid </code> 和explicible <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>用户ID和d_ dpuid=数据提供者的用户ID&amp;<i>d_ dpid=数据提供者ID</i></code> </p> <p> <code> d_ uuid </code> 始终优先。If the <code> dpid </code> + <code> dpuuid </code> combination maps to another AAM UUID, the opt-out is stored under the AAM UUID passed in the request ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables and Syntax for Declared IDs {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

The following table lists the key-value pairs that pass in your [!DNL Audience Manager] data provider ID and user IDs or integration codes, if used. Note, *italics* indicates a variable placeholder. 增加了空格，使它们更易于阅读。

在每个键值对中：

* `=` 符号将键与相关值分开。
* The non-printing [!DNL ASCII] character `%01` separates the values.

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

## Sample Event Calls {#sample-event-calls}

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
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>名</i>/事件？d_ cid=123%1987&amp; d_ cid_ ic=456%01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [CID替换DPID和DPUUID](../reference/cid.md)


## Declared ID Variables {#declared-id-variables}

Describes the configuration variables used to pass declared IDs through [!UICONTROL DIL] to [!DNL Audience Manager.]

## DIL Uses the Experience Cloud ID Service to Pass Declared IDs {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

When used with the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), you no longer need to pass in [!UICONTROL declared IDs] with the deprecated `dpid` and `dpuuid` variables. Instead, the current versions of [!UICONTROL DIL] rely on the `visitorService` function to get the [!UICONTROL declared IDs] from the `setCustomerIDs` function in the [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). You would call `visitorService` in `DIL.create` as shown below.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

`namespace` 在键值对中， `MCORG` 是 [!DNL Experience Cloud] 您的组织ID。If you don&#39;t have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. 您需要管理员权限才能查看此控制板。See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Deprecated Functions {#deprecated-functions}

With the latest versions of [!UICONTROL DIL] (6.2+), you don&#39;t need to use these key-value pairs to pass in [!UICONTROL declared IDs]. That&#39;s because [!UICONTROL DIL] now relies on the `visitorService` function shown in the code sample above. This function gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service]. 但是，我们将出于历史和传统目的引用这些变量。See the code below for an example of how to configure `DIL.create` to get a [!UICONTROL declared ID] from the [!UICONTROL Visitor ID Service].
The following table describes the legacy variables used by the `declaredId` object:

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

Audience Manager compares and matches the combined `DPID` and `DPUUID` to a corresponding user ID in our system. If an ID does not exist, Audience Manager creates a new user ID and synchronizes it to the `DPID/DPUUID` combination. Once Audience Manager matches or creates a user ID (the `UUID`) it returns that ID in the [!DNL JSON] response to the cookie in the client&#39;s domain (first-party cookie) or other local storage.

Call this function when you&#39;re using [!UICONTROL DIL] v6.1 or earlier. However, this function has been deprecated in favor of the new version that gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service].

<pre class="js"><code>DIL. create({
合作伙伴：“合作伙伴姓名”，
声明ID：{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{
dpuid： <i>dpuid</i>，
DPID： <i>dpid</i> 
}}
})；</code>
</pre>

>[!NOTE]
>
>Note, you need to programmatically develop the code that supplies the ID values for the `d_dpuuid` and `d_dpid` keys.

### 在DIL实例化后传入ID

>[!NOTE]
>
>If you make an [!DNL API] call with a different `declaredID` combination, the new combination will be used for that call only. Further regular event calls will use the original `DIL.create`  `declaredID` combination.

<pre class="js"><code>DIL. getDil('合作伙伴名称'). api.信号({…}).声明Dreamwead({
dpuid：<i>dpuid</i> 
dpid：<i>dpid</i> }). 
mit()；</code>
</pre>

## Request/Response Examples {#request-response-examples}

请求将数据提供程序和用户ID发送到Audience Manager：

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

The response returns the Audience Manager ID (e.g., `UUID`) which is written to a first-party cookie in the page domain.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Do Not Target and Opt-Out Calls {#do-not-target}

[!UICONTROL declared ID] 该流程遵循网站访客偏好来选择退出您的网站受众管理器定位。When Audience Manager receives an opt-out request, the [!UICONTROL DCS] returns an empty [!DNL JSON] object instead of the Audience Manager user ID.