---
description: 声明的ID的工作方式、设置过程、代码示例和变量。
keywords: id sync
seo-description: 声明的ID的工作方式、设置过程、代码示例和变量。
seo-title: 声明的 ID
solution: Audience Manager
title: 声明的 ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
translation-type: tm+mt
source-git-commit: 29708d5fc528ac9da08f4c5a7f2bcaa11b240d8b
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 10%

---


# [!UICONTROL Declared IDs] {#declared-ids}

[!UICONTROL declared IDs]的工作方式、设置过程、代码示例和变量。

## [!UICONTROL Declared ID] 定位 {#declared-id-targeting}

不使用或接受永久存储机制的设备或浏览器（如第三方[!DNL cookies]）的用户ID与[!DNL Audience Manager]进行交换和同步。

## [!UICONTROL Declared ID]定位{#declared-id-targeting-purpose}的用途

某些浏览器和大多数移动设备不接受第三方[!DNL cookies]。 这使得很难保留有关站点访客的信息或分配永久ID。 要解决此问题，[!DNL Audience Manager]使用[!UICONTROL DIL]让您在事件调用中传入[!UICONTROL declared IDs]。 此外，[!UICONTROL declared ID]可以充当适用于[!DNL Experience Cloud]中所有解决方案的同一用户的通用ID。 下表描述了ID定位／匹配过程：

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 过程 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>事件呼叫</b> </td> 
   <td colname="col2"> <p>要使用，您需要页面上的<span class="wintitle">DIL</span>和<a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external">Adobe Experience Platform标识服务</a>代码。 <span class="wintitle"> DIL </span> 通 <span class="wintitle"> 过 </span> Adobe Experience Platform身份服 <code> setVisitorID </code> 务提供的 <span class="keyword"> 函数获取声 </span> 明的ID，并 <span class="keyword"> 将其传递给 </span>Audience Manager。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>匹配ID</b> </td> 
   <td colname="col2"> <p>Audience Manager尝试将客户端和访客ID与系统中的相应ID匹配。 如果不存在匹配的ID,Audience Manager将创建新ID并将其与客户端和访客ID关联。 </p> <p> <p>注意： 如果您的ID映射到多个Audience ManagerID，则使用最新映射。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>返回ID</b> </td> 
   <td colname="col2"> <p>Audience Manager将其同步ID写入客户端域或应用程序中的第一方cookie(或其他可寻址存储空间)。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>后续事件调用</b> </td>
   <td colname="col2"> <p>其他事件调用从客户端的域读取Audience ManagerID，并将其发送给Audience Manager。 </p> </td>
  </tr> 
 </tbody>
</table>

要开始，您需要在要用于数据收集的站点的各个页面中配置[!DNL Experience Cloud] ID服务和[!UICONTROL DIL]。 请参阅[DILcreate](../dil/dil-class-overview/dil-create.md#dil-create)和[声明的ID变量](../features/declared-ids.md#declared-id-variables)。

## 退出呼叫{#opt-out-calls}

[!UICONTROL declared ID]流程接受网站访客偏好，选择退出网站的[!DNL Audience Manager]定位。 当[!DNL Audience Manager]收到退出请求时，由[!DNL DCS]返回的[!DNL JSON]包含错误代码171，其中消息为`Encountered opt out tag`，而不是[!DNL Audience Manager]用户ID。

* [!DNL Audience Manager] 可以在中 [!UICONTROL declared ID] 加入退出选项的 [!DNL Audience Manager] [!UICONTROL UUID] 旁边 [!DNL URL]。
* [!UICONTROL declared ID]退出按每个合作伙伴存储在[!UICONTROL Profile Cache Server]([!UICONTROL PCS])中。 没有使用[!UICONTROL declared IDs]的平台级退出。 此外，[!DNL Audience Manager]会选择用户从边缘上的特定区域退出（退出不会跨越[!DNL DCS]区域）。

有关选择退出数据收集的详细信息，请参阅[数据隐私](../overview/data-security-and-privacy/data-privacy.md)。

## [!UICONTROL Declared ID] 退出示例  {#opt-out-examples}

可以使用`d_cid`和`d_cid_ic`键值对发出[!UICONTROL declared ID]退出请求。 虽然旧版参数（如 `d_dpid` 和 `d_dpuuid`）仍然可用，但已考虑将其弃用。请参阅 [CID 取代 DPID 和 DPUUID](../reference/cid.md)。在示例中，*斜体*&#x200B;表示变量占位符。

### 选择退出（带有[!UICONTROL CID]和[!UICONTROL CID_IC]）

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

### 选择退出（[!UICONTROL DPID]、[!UICONTROL DPUUID]和[!UICONTROL UUID]）（已弃用）

这些方法仍然有效，但被认为已弃用。 此信息是为传统目的和参考提供的。 旧版选择退出包括：

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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>合作伙伴级别退出会存储为此<code> dpid </code> + <code> dpuuid </code>对的最新映射到AAM UUID。 如果以前没有映射，Audience Manager将检查请求在cookie中是否包含AAM UUID，如果包含，则使用它存储退出。 否则，Audience Manager将生成新的AAM UUID并在其下存储退出。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> +  <code> d_dpid </code> and explicit  <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> 始终优先。如果<code> dpid </code> + <code> dpuuid </code>组合映射到另一个AAM UUID，则选择退出存储在请求中传递的AAM UUID(<code> d_uuid </code>)下。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared IDs] {#variables-and-syntax}的变量和语法

下表列表了传递到[!DNL Audience Manager]数据提供程序ID和用户ID或集成代码（如果使用）的键值对。 注意，*斜体*&#x200B;表示变量占位符。 已添加空格，使这些内容更易于阅读。

在每个键值对中：

* `=`符号将键与其相关值分开。
* 非打印字符[!DNL ASCII]将分隔这些值。`%01`

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
   <td colname="col2"> <p>在单个键值对中包含数据提供程序ID和关联的唯一用户ID。 <code> d_cid </code> replace <code> d_dpid </code> 和 <code> d_dpuuid </code>，它们被视为已弃用，但仍受支持。请参阅 <a href="../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>在单个键值对中包含集成代码和关联的唯一用户ID。 <code> d_cid_ic </code> replace <code> d_dpid </code> 和 <code> d_dpuuid </code>，它们已弃用，但仍受支持。请参阅 <a href="../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例事件调用{#sample-event-calls}

如果给定这些键值对及其必需的语法，您将进行事件调用，如下所示。

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 事件呼叫包括 </th> 
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

## [!UICONTROL DIL] 使用 [!DNL Adobe Experience Platform Identity Service] to Pass  [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

当与[Adobe Experience Platform身份服务](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)一起使用时，您不再需要使用已弃用的`dpid`和`dpuuid`变量传入[!UICONTROL declared IDs]。 相反，[!UICONTROL DIL]的当前版本依赖`visitorService`函数从[!UICONTROL Adobe Experience Platform Identity Service]的`setCustomerIDs`函数获取[!UICONTROL declared IDs]。 有关详细信息，请参阅[客户ID和身份验证状态](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)。 您将调用`DIL.create`中的`visitorService`，如下所示。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

在`namespace`键值对中，`MCORG`是您的[!DNL Experience Cloud]组织ID。 如果您没有此ID，您可以在[!DNL Experience Cloud]仪表板的[!UICONTROL Administration]部分找到它。 您需要管理员权限才能视图此仪表板。 请参阅[管理：核心服务](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html)。

## 已弃用函数{#deprecated-functions}

对于[!UICONTROL DIL](6.2+)的最新版本，您无需使用这些键值对即可传入[!UICONTROL declared IDs]。 这是因为[!UICONTROL DIL]现在依赖于上面代码示例中显示的`visitorService`函数。 此函数从[!UICONTROL Adobe Experience Platform Identity Service]获取[!UICONTROL declared IDs]。 但是，我们在此引用这些变量以用于历史和传统用途。 有关如何配置`DIL.create`以从[!UICONTROL Visitor ID Service]获取[!UICONTROL declared ID]的示例，请参见下面的代码。
下表描述了`declaredId`对象使用的旧变量：

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

[!DNL Audience Manager] 将合并后的用户ID `DPID` 与我 `DPUUID` 们系统中的相应用户ID进行比较和匹配。如果ID不存在，[!DNL Audience Manager]将创建新的用户ID并将其同步到`DPID/DPUUID`组合。 在[!DNL Audience Manager]匹配或创建用户ID(`UUID`)后，它会在[!DNL JSON]响应中返回该ID，以响应客户端域（第一方[!DNL cookie]）或其他本地存储。[!DNL cookie]

使用[!UICONTROL DIL] v6.1或更早版本时调用此函数。 但是，已弃用此函数，而使用从[!DNL Adobe Experience Platform Identity Service]获取[!UICONTROL declared IDs]的新版本。

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

### 在[!UICONTROL DIL]实例化后传入ID

>[!NOTE]
>
>如果使用不同的`declaredID`组合进行[!DNL API]调用，则新组合将仅用于该调用。 进一步的常规事件调用将使用原始的`DIL.create` `declaredID`组合。

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 请求／响应示例{#request-response-examples}

请求将数据提供程序和用户ID发送到[!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

该响应返回写入到页面域中第一方cookie的Audience ManagerID（例如`UUID`）。

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 不目标和退出调用{#do-not-target}

[!UICONTROL declared ID]流程接受网站访客偏好，选择退出网站的[!DNL Audience Manager]定位。 当[!DNL Audience Manager]收到退出请求时，[!DNL DCS]返回空的[!DNL JSON]对象，而不是[!DNL Audience Manager]用户ID。

>[!MORELIKETHIS]
>
>* [CID 取代 DPID 和 DPUUID](../reference/cid.md)

