---
description: 声明的ID的工作方式、设置过程、代码示例和变量。
keywords: id sync
seo-description: 声明的ID的工作方式、设置过程、代码示例和变量。
seo-title: 声明的ID
solution: Audience Manager
title: 声明的ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# 声明的ID {#declared-ids}

声明的ID的工作方式、设置过程、代码示例和变量。

## 声明 ID 定位 {#declared-id-targeting}

在不使用或接受永久存储机制（如第三方Cookie）的设备或浏览器中，与Audience Manager交换用户ID并同步。

<!-- declared_id_about.xml -->

## 声明ID定位的目的 {#declared-id-targeting-purpose}

某些浏览器和大多数移动设备不接受第三方Cookie。 这使得很难保留有关网站访客的信息或分配永久ID。 要解决此问题，Audience Manager会 [!UICONTROL DIL] 允许您通过活 [!UICONTROL declared IDs] 动调用。 此外， [!UICONTROL declared ID] 可以充当通用ID，该通用ID适用于中所有解决方案的同一用户 [!DNL Experience Cloud]。 下表介绍了ID定位／匹配过程：

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 过程 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>活动调用</b> </td> 
   <td colname="col2"> <p>要使用，您需 <span class="wintitle"> 要页 </span> 面上的 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> DIL和Adobe Experience Platform Identity Service </a> 代码。 <span class="wintitle"> DIL通过 </span><span class="wintitle"> Adobe Experience Platform Identity Service提供的函数获得声明的ID </span> ，并将该ID <code> setVisitorID </code> 传递给 <span class="keyword"></span><span class="keyword"></span>Audience Manager。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>匹配ID</b> </td> 
   <td colname="col2"> <p>Audience Manager会尝试将客户端ID和访客ID与系统中的相应ID进行匹配。 如果不存在匹配的ID,Audience Manager将创建新ID并将其与客户端ID和访客ID关联。 </p> <p> <p>注意： 如果您的ID映射到多个Audience Manager ID，则会使用最新的映射。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>返回ID</b> </td> 
   <td colname="col2"> <p>Audience Manager将其同步ID写入客户端域或应用程序中的第一方Cookie（或其他可寻址存储空间）。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>后续事件调用</b> </td>
   <td colname="col2"> <p>其他活动调用从客户端域读取Audience Manager ID，并将其发送到Audience Manager。 </p> </td>
  </tr> 
 </tbody>
</table>

要开始使用，您需要配置 [!DNL Experience Cloud] ID服务， [!UICONTROL DIL] 并跨站点上要用于数据收集的页面进行配置。 请参 [阅DIL create](../dil/dil-class-overview/dil-create.md#dil-create) and [Declared ID变量](../features/declared-ids.md#declared-id-variables)。

## 退出呼叫 {#opt-out-calls}

该过 [!UICONTROL declared ID] 程支持网站访客偏好，以便根据您的网站选择退出Audience Manager定位。 当Audience Manager收到退出请求时，由返回的 [!DNL JSON][!UICONTROL DCS] 包含错误代码171，并显示消息“遇到退出标记”，而不是Audience Manager用户ID。

* Audience Manager可以与中的Audience Manager [!UICONTROL declared ID] 一起通过选择退出 [!UICONTROL UUID] 方式 [!DNL URL]。
* 退 [!UICONTROL declared ID] 出按合作伙伴存储在[!UICONCONTROL配置文件缓存服务器([!UICONTROL PCS])中。 没有平台级别的退出使用 [!UICONTROL declared IDs]。 此外，Audience Manager还会选择用户从边缘的特定区域退出(选择退出不会跨区域 [!UICONTROL DCS] )。

有关 [选择退出数据收集的更多信息](../overview/data-security-and-privacy/data-privacy.md) ，请参阅数据隐私。

## 声明的ID退出示例 {#opt-out-examples}

您可以使用 [!UICONTROL declared ID] 键值和键值对发出 `d_cid` 退 `d_cid_ic` 出请求。 旧参数(如和 `d_dpid` 仍可 `d_dpuuid` 用，但被视为已弃用。 请参阅 [CID 取代 DPID 和 DPUUID](../reference/cid.md)。In the examples, *italics* indicates a variable placeholder.

### 使用CID和CID_IC选择退出

有关说明和语法，请参阅 [URL变量和Declared ID的语法](../features/declared-ids.md#variables-and-syntax)。

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选择退出使用 </th> 
   <th colname="col2" class="entry"> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>数据提供者ID和用户ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>集成代码和用户ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多个 <code> d_cid </code> 和 <code> d_cid_ic </code> 键值对。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### DPID、DPUUID和UUID的退出（已弃用）

这些方法仍然有效，但被视为已弃用。 此信息是为了传统用途和参考而提供的。 旧版选择退出包括：

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 退出（已弃用） </th> 
   <th colname="col2" class="entry"> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> 在 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合作伙伴级别选择退出 </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>将存储一个合作伙伴级别的退出选项，以将此 <code> dpid </code> +对的最 <code> dpuuid </code> 新映射到AAM UUID。 如果之前没有现有映射，Audience Manager将检查请求在cookie中是否包含AAM UUID，如果包含，则使用它存储退出。 否则，Audience Manager将生成一个新的AAM UUID，并在其下存储退出选项。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> and explicit <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> 始终优先。 如果 <code> dpid </code> +组 <code> dpuuid </code> 合映射到另一个AAM UUID，则退出将存储在请求()中传递的AAM UUID下 <code> d_uuid </code>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 声明ID的变量和语法 {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

下表列出了传入数据提供者ID和用户ID或集成代码（如果使用） [!DNL Audience Manager] 的键值对。 Note, *italics* indicates a variable placeholder. 已添加空格，以便更轻松地阅读。

在每个键值对中：

* 符号 `=` 将键与其相关值分开。
* 非打印字 [!DNL ASCII] 符 `%01` 分隔值。

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
   <td colname="col2"> <p>在单个键值对中包含数据提供者ID和关联的唯一用户ID。 <code> d_cid </code> 替换 <code> d_dpid </code> 和 <code> d_dpuuid </code>，后者被视为已弃用，但仍受支持。 请参阅 <a href="../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>在单个键值对中包含集成代码和关联的唯一用户ID。 <code> d_cid_ic </code> 替换 <code> d_dpid </code> 和 <code> d_dpuuid </code>（已弃用但仍支持）。 请参阅 <a href="../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例事件调用 {#sample-event-calls}

鉴于这些键值对及其必需的语法，您将进行如下所示的事件调用。

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
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>集成代码和用户ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多个 <code> d_cid </code> 和 <code> d_cid_ic </code> 键值对。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 声明的ID变量 {#declared-id-variables}

描述用于将声明的ID传递给的配置变 [!UICONTROL DIL] 量 [!DNL Audience Manager.]

## DIL使用Adobe Experience Platform Identity Service传递声明的ID {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

与 [Adobe Experience Platform Identity Service一起使用时](https://marketing.adobe.com/resources/help/en_US/mcvid/)，您不再需要传递已弃用 [!UICONTROL declared IDs] 的变量 `dpid` 和变 `dpuuid` 量。 相反，当前版本的 [!UICONTROL DIL] 依赖函 `visitorService` 数从中的函 [!UICONTROL declared IDs] 数 `setCustomerIDs` 获取该函数 [!UICONTROL Adobe Experience Platform Identity Service]。 For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). 如下所示， `visitorService` 您可 `DIL.create` 以拨入。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

在键 `namespace` 值对中，您的 `MCORG` 组织 [!DNL Experience Cloud] ID。 如果您没有此ID，则可以在仪表板的部分 [!UICONTROL Administration] 找到该 [!DNL Experience Cloud] ID。 您需要管理员权限才能查看此功能板。 See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## 已弃用的函数 {#deprecated-functions}

使用最新版本 [!UICONTROL DIL] (6.2+)，您无需使用这些键值对即可传入 [!UICONTROL declared IDs]。 这是因为现 [!UICONTROL DIL] 在依赖于上面的 `visitorService` 代码示例中显示的函数。 此函数 [!UICONTROL declared IDs] 来自 [!UICONTROL Adobe Experience Platform Identity Service]。 但是，我们在此引用这些变量以用于历史和传统用途。 有关如何配置以从中获取的示例，请参 `DIL.create` 阅以下代 [!UICONTROL declared ID] 码 [!UICONTROL Visitor ID Service]。
下表描述了该对象使用的旧版变 `declaredId` 量：

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

### `DPID` 和 `DPUUID`

Audience Manager会比较合并后的用户ID，并将其与 `DPID` 我们系统 `DPUUID` 中的相应用户ID进行匹配。 如果ID不存在，Audience Manager将创建新的用户ID并将其同步到组 `DPID/DPUUID` 合。 Audience Manager匹配或创建用户ID( `UUID`[!DNL JSON] )后，会在客户端域（第一方Cookie）或其他本地存储中对Cookie的响应中返回该ID。

使用v6.1或更早版本时， [!UICONTROL DIL] 调用此函数。 但是，已弃用此函数，而改用从中获取的 [!UICONTROL declared IDs] 新版本 [!UICONTROL Adobe Experience Platform Identity Service]。

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
>注意，您需要以编程方式开发提供和键的ID值的 `d_dpuuid` 代 `d_dpid` 码。

### 在DIL实例化后传入ID

>[!NOTE]
>
>如果您使用其 [!DNL API] 他组合进行 `declaredID` 呼叫，则新组合将仅用于该呼叫。 进一步的常规活动调用将使用原始 `DIL.create``declaredID` 组合。

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 请求／响应示例 {#request-response-examples}

此请求会向Audience Manager发送数据提供者和用户ID:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

该响应会返回写入页面域中的第一方Cookie的Audience Manager ID(例如 `UUID`)。

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 不定位和退出呼叫 {#do-not-target}

该过 [!UICONTROL declared ID] 程支持网站访客偏好，以便根据您的网站选择退出Audience Manager定位。 当Audience Manager收到退出请求时，将返 [!UICONTROL DCS] 回空对象而 [!DNL JSON] 非Audience Manager用户ID。

>[!MORELIKETHIS]
>
>* [CID替换DPID和DPUUID](../reference/cid.md)

