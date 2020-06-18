---
description: 声明的ID的工作方式、设置过程、代码示例和变量。
keywords: id sync
seo-description: 声明的ID的工作方式、设置过程、代码示例和变量。
seo-title: 声明的ID
solution: Audience Manager
title: 声明的ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1230'
ht-degree: 3%

---


# 声明的ID {#declared-ids}

声明的ID的工作方式、设置过程、代码示例和变量。

## 声明 ID 定位 {#declared-id-targeting}

在不使用或接受 [!DNL Audience Manager] 永久存储机制的设备或浏览器（如第三方Cookie）上交换用户ID并进行同步。

<!-- declared_id_about.xml -->

## 声明ID定位的目的 {#declared-id-targeting-purpose}

某些浏览器和大多数移动设备不接受第三方cookie。 这使得很难保留有关站点访客的信息或分配永久ID。 要解决此问题， [!DNL Audience Manager] 请 [!UICONTROL DIL] 使用允许您通过 [!UICONTROL declared IDs] 事件呼叫。 此外， [!UICONTROL declared ID] 可以充当通用ID，该ID适用于中所有解决方案的同一用户 [!DNL Experience Cloud]。 下表描述了ID定位／匹配过程：

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
   <td colname="col2"> <p>要正常工作，您需 <span class="wintitle"> 要页 </span> 面上的 <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> DIL和 </a> Adobe Experience Platform标识服务代码。 <span class="wintitle"> DIL </span> 从Adobe Experience Platform身 <span class="wintitle"> 份服务提供的 </span> 函数中获取声 <code> setVisitorID </code> 明的ID，并 <span class="keyword"> 将其传递到 </span><span class="keyword"></span>Audience Manager。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>匹配ID</b> </td> 
   <td colname="col2"> <p>Audience Manager尝试将客户端和访客ID与系统中的相应ID匹配。 如果不存在匹配的ID,Audience Manager将创建新ID并将其与客户端和访客ID关联。 </p> <p> <p>注意：  如果您的ID映射到多个Audience ManagerID，则使用最新映射。 </p> </p> </td> 
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

要开始，您需要配置ID [!DNL Experience Cloud] 服务， [!UICONTROL DIL] 并在站点上要用于数据收集的页面之间进行配置。 请参 [阅DIL创建](../dil/dil-class-overview/dil-create.md#dil-create)[和声明ID变量](../features/declared-ids.md#declared-id-variables)。

## 退出呼叫 {#opt-out-calls}

该过 [!UICONTROL declared ID] 程将遵守网站访客首选项，以选择 [!DNL Audience Manager] 退出网站定位。 当收 [!DNL Audience Manager] 到退出请求时，由 [!DNL JSON] 返回的包 [!DNL DCS] 含错误代码171，消息为“遇选择退出到标记”，而不是 [!DNL Audience Manager] 用户ID。

* [!DNL Audience Manager] 可以在中 [!UICONTROL declared ID] 加入退出选项 [!DNL Audience Manager] 并 [!UICONTROL UUID] 进行退 [!DNL URL]出
* 退 [!UICONTROL declared ID] 出选项按每个合作伙伴存储在[!UICONTROL用户档案[!UICONTROL PCS]缓存服务器()中。 没有平台级别的退出使用 [!UICONTROL declared IDs]。 此外， [!DNL Audience Manager] 选择用户从边缘上的特定区域退出(选择退出不会跨越 [!DNL DCS] 区域)。

有关 [选择退出数据收](../overview/data-security-and-privacy/data-privacy.md) 集的更多信息，请参阅数据隐私。

## 声明的ID退出示例 {#opt-out-examples}

您可以使 [!UICONTROL declared ID] 用和键值对发出 `d_cid` 退 `d_cid_ic` 出请求。 旧参数(如 `d_dpid` 和 `d_dpuuid` 仍可用)被视为已弃用。 请参阅 [CID 取代 DPID 和 DPUUID](../reference/cid.md)。In the examples, *italics* indicates a variable placeholder.

### 使用CID和CID_IC选择退出

有关说明和语法，请参 [阅URL变量和Declared ID的语法](../features/declared-ids.md#variables-and-syntax)。

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用 </th> 
   <th colname="col2" class="entry"> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>数据提供程序ID和用户ID。 </p> </td> 
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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>将存储合作伙伴级别的退出选项，以将此+对 <code> dpid </code> 的最 <code> dpuuid </code> 新映射到AAM UUID。 如果以前没有任何映射，Audience Manager将检查请求在cookie中是否包含AAM UUID，如果包含，则使用该AAM UUID存储退出。 否则，Audience Manager将生成新的AAM UUID并在其下存储退出。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> explicit <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> 始终优先。 如果 <code> dpid </code> + <code> dpuuid </code> 组合映射到另一个AAM UUID，则选择退出存储在请求()中传递的AAM UUID <code> d_uuid </code>下。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 声明ID的变量和语法 {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

下表列表了传入数据提供者ID和用户ID或集 [!DNL Audience Manager] 成代码（如果使用）的键值对。 Note, *italics* indicates a variable placeholder. 已添加空格，使这些内容更易于阅读。

在每个键值对中：

* 符号 `=` 将键与其相关值分开。
* 非打印字 [!DNL ASCII] 符 `%01` 分隔这些值。

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
   <td colname="col2"> <p>在单个键值对中包含数据提供程序ID和关联的唯一用户ID。 <code> d_cid </code> 替换 <code> d_dpid </code> 和 <code> d_dpuuid </code>，后者被视为已弃用，但仍受支持。 请参阅 <a href="../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>在单个键值对中包含集成代码和关联的唯一用户ID。 <code> d_cid_ic </code> 替换 <code> d_dpid </code> 和 <code> d_dpuuid </code>（已弃用，但仍受支持）。 请参阅 <a href="../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例事件调用 {#sample-event-calls}

如果给定这些键值对及其所需的语法，您将进行事件调用，如下所示。

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 事件呼叫包括 </th> 
   <th colname="col2" class="entry"> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>数据提供程序ID和用户ID。 </p> </td> 
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

## DIL使用Adobe Experience Platform标识服务传递声明的ID {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

与Adobe Experience Platform标 [识服务一起使用](https://docs.adobe.com/content/help/en/id-service/using/home.html)，您不再需要随已弃用 [!UICONTROL declared IDs] 的变量和变 `dpid` 量一起 `dpuuid` 传递。 相反，当前版本 [!UICONTROL DIL] 依赖函 `visitorService` 数从中 [!UICONTROL declared IDs] 的函 `setCustomerIDs` 数获取 [!UICONTROL Adobe Experience Platform Identity Service]。 For more information, see [Customer IDs and Authentication States](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). 如下所 `visitorService` 示， `DIL.create` 您将拨入。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

在键 `namespace` 值对中， `MCORG` 是您的 [!DNL Experience Cloud] 组织ID。 如果您没有此ID，您可以在仪表板的 [!UICONTROL Administration] 部分找到 [!DNL Experience Cloud] 它。 您需要管理员权限才能视图此仪表板。 See [Administration: Core Services](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## 已弃用的函数 {#deprecated-functions}

使用最新版 [!UICONTROL DIL] 本(6.2+)，您无需使用这些键值对即可传入 [!UICONTROL declared IDs]。 这是因为现 [!UICONTROL DIL] 在依赖于上 `visitorService` 面代码示例中显示的函数。 此函数 [!UICONTROL declared IDs] 来自 [!UICONTROL Adobe Experience Platform Identity Service]。 但是，我们在此引用这些变量以用于历史和传统用途。 有关如何配置以从中获取 `DIL.create` 的示例，请参 [!UICONTROL declared ID] 阅下面的代 [!UICONTROL Visitor ID Service]码。
下表描述了对象使用的旧变 `declaredId` 量：

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

[!DNL Audience Manager] 将合并后的用户ID与 `DPID` 我们 `DPUUID` 系统中的相应用户ID进行比较和匹配。 如果ID不存在，则创 [!DNL Audience Manager] 建新的用户ID并将其同步到 `DPID/DPUUID` 组合。 匹 [!DNL Audience Manager] 配或创建用户ID( `UUID`)后，在响应客户端域(第 [!DNL JSON] 一方cookie)或其他本地存储中的cookie时返回该ID。

使用v6.1或更早版本时 [!UICONTROL DIL] 调用此函数。 但是，已弃用此函数，而改用从中获取的 [!UICONTROL declared IDs] 新版本 [!DNL Adobe Experience Platform Identity Service]。

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
>您需要以编程方式开发提供和键ID值 `d_dpuuid` 的代 `d_dpid` 码。

### 在DIL实例化后传入ID

>[!NOTE]
>
>如果您使用 [!DNL API] 不同的组 `declaredID` 合进行呼叫，则新组合将仅用于该呼叫。 进一步的常规事件调用将使用原始 `DIL.create` 组 `declaredID` 合。

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 请求／响应示例 {#request-response-examples}

此请求将数据提供程序和用户ID发送到 [!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

该响应返回写入到页面域中 `UUID`第一方cookie的Audience ManagerID（例如）。

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 不Target和选择退出呼叫 {#do-not-target}

该过 [!UICONTROL declared ID] 程将遵守网站访客首选项，以选择 [!DNL Audience Manager] 退出网站定位。 当 [!DNL Audience Manager] 收到退出请求时，将返 [!DNL DCS] 回一个空 [!DNL JSON] 对象而不是 [!DNL Audience Manager] 用户ID。

>[!MORELIKETHIS]
>
>* [CID替换DPID和DPUUID](../reference/cid.md)

