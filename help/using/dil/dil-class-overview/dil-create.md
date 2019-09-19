---
description: 创建特定于合作伙伴的DIL实例。
seo-description: 创建特定于合作伙伴的DIL实例。
seo-title: DIL创建
solution: Audience Manager
title: DIL创建
uuid: 6e054600-703c-4a97-af2a-8207c50013db
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL创建方法{#dil-create}

## DIL创建 {#dil-create-new}

创建特定于合作伙伴的 [!UICONTROL DIL] 实例。

**** 函数签名： `DIL.create: function (initConfig) {}`

**initConfig元素**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>该属 `visitorService` 性始终 *是必需* 。 除非另有指明，此处列出的其他属性是可选的。

`initConfig` 接受以下元素：

<table id="table_1334973505F54B238127FED9845B16C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名称 </th> 
   <th colname="col2" class="entry"> 类型 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> containerNSID </code> </p> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>此属性可设置由 <span class="keyword">Audience Manager</span> 用来进行 ID 同步的容器 ID。如果已跨多个 <code> 站点部 </code> 署DIL，则应设 <span class="wintitle"> 置容 </span> 器NSID。 每个站点都将具有自己的容器ID和ID同步。 当您只有1个站点时，默认情况下容器ID为0，您无需正确设置它。 请联系您的顾问以获取站点及其容器ID的列表。 </p> <p>在 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID服务中，属性 </a>idSyncContainerID与 <code> DIL </code> 中的容器 <code> NSID相对应 </code><span class="wintitle"></span>。 如果您在多个站点上使用 <span class="wintitle"> DIL </span> 和 <i>ID服务</i> ，请注意以下事项： </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">对于每个站点，在容器NSID和idSyncContainerID上设 <code> 置相同的 </code> 容器 <code> ID </code>。 </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">DIL和 <span class="wintitle"> ID服 </span> 务都将尝试将ID同步发送到我们的数据收集iFrame。 但是，iFrame可确保 <span class="wintitle"> DIL </span> 不会触发ID同步。 这可以防止重复。 </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">只有 <span class="wintitle"> DIL才 </span> 会将数据发送到 <a href="../../features/destinations/destinations.md"> URL目标 </a>。 </li> 
     </ul> </p> <p>另请参 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsyncontainerid.html" format="https" scope="external"> 阅idSyncContainerID </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> 
    <draft-comment> 
     <p>在每次活 <a href="../../features/declared-ids.md"> 动调用中将 </a> Declared ID变量发送到 <span class="keyword"> Audience Manager </span>。 </p> 
    </draft-comment> <p> <code> delcandedId </code> 用于传递以下任一项： </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>:Audience manager分配给您的数据合作伙伴 <span class="keyword"> ID </span>。 </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>:您的用户唯一ID。 </li> 
    </ul> <p> <p>重要说明： 仅对您的ID使用未编码的值。 编码将创建双重编码标识符。 </p> </p> <p> <p>注意： 如果您使用 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID服务， </a>请使用setCustomerIDs方法设置客户ID，而不 <code> 是使用 </code> DIL <span class="wintitle"></span>。 See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> 如果为true，则将执行所有请求（IFRAME、事件调用、ID同步和目标），直到“页面加载”事 <code> 件 </code> 触发。 Default is <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> false 默认情况下，这意味 <span class="keyword"> 着Audience Manager </span> 在合作伙伴的域中设置Cookie（设置第一方Cookie）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>重要说明： DIL版本8.0(2018年8月发 <span class="wintitle"> 布) </span> 已弃用此元素。 请改用 <code> Experience Cloud ID服 </code> 务中 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"></a> 的visitor.disableIdSyncs函数。 </p> </p> <p> 如 <code> 果为 </code>true，则不会将目标发布IFRAME附加到DOM或触发目标。 Default is <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>重要说明： DIL版本8.0(2018年8月发 <span class="wintitle"> 布) </span> 已弃用此元素。 请改用 <code> Experience Cloud ID服 </code> 务中 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"></a> 的visitor.disableIdSyncs函数。 </p> </p> <p>禁用 ID 同步。在使用DIL v6.2+和访客ID服务时，必须禁用ID同步。 visitor <code> Service </code> 函数（请参阅下面的示例代码）负责此操作。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> 设置为 <code> true可 </code> 为页面上的所有 <span class="wintitle"> DIL实 </span> 例启用错误报告。 仅与Boolean <code> true </code> 一起使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>重要说明： DIL版本8.0(2018年8月发 <span class="wintitle"> 布) </span> 已弃用此元素。 请改用 <code> Experience Cloud ID服务中的visitor.idSyncSSLUseAkamai </code> 函 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idSyncSSLUseAkamai.html" format="https" scope="external"></a> 数。 </p> </p> <p> 指定目标发布模板是否应当使用 Akamai 进行 HTTPS 连接。针对每个合作伙伴启用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 映射 </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>将值从一个键值对关联到另一个键值对。 请参 <a href="../../dil/dil-use-cases.md#map-key-values"> 阅将键值映射到其他键 </a>。 随v2.4一起发布。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>必需. </p> <p>命名 <code> 空间 </code> 键值对包含您的 <span class="keyword"> Experience Cloud组 </span> 织ID。 如果您没有此ID，则可以在Experience cloud仪表板的“管 <span class="wintitle"> 理” </span> 部分找到 <span class="keyword"> 该ID </span> 。 您需要管理员权限才能查看此功能板。 请参阅产 <a href="../../faq/faq-features.md"> 品功能常见问题解答和 </a> 管理- <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> 用户管理和常见问题解答 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 合作伙伴 </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>必需. </p> <p> 由 <span class="keyword"> Audience manager提供的合作伙伴名 </span>称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> 删除脚本和回调。 Default is <code> False </code>. 仅适用于当 <span class="wintitle"> 前DIL </span> 实例。 随v3.3一起发布。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>使用从 <span class="keyword"> Audience Manager返回的唯一用户ID设置Cookie </span>。 请参阅 <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie属 </a>性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>DIL 6.2或 <span class="wintitle"> 更高版 </span> 本必需。 </p> <p> DIL依靠 <code> Experience Cloud ID服务 </code> 中的setCustomerID功能 <span class="wintitle"> 将声明的ID传递到 </span> Audience Manager <span class="keyword"></span>中。 See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例代码**

示例调 [!UICONTROL DIL] 用可能类似于以下内容：

```js
var partnerObject1 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-ORGANIZATION-ID-HERE" 
  }, 
  containerNSID: 3, 
  uuidCookie:{ 
    name:'ad_uuid', 
    days:200, 
    path:'/test', 
    domain:'adobe.com', 
    secure:true 
  } 
}); 
 
var partnerObject2 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-MCORG-ID-HERE" 
  }, 
  containerNSID: 3 
}); 
```

成功的响应会返回该 [!UICONTROL DIL] 实例。 如果您的代码配置不当或每当遇到错误时，尝试失败会返回错误对象（未引发）。

## uuidCookie属性 {#uuidcookie-props}

定义变量使用的 `uuidCookie` 属性。 此变量是方法的一 `DIL.create` 部分。

`uuidCookie` 具有以下属性：

<!-- 

r_dil_uuid_cookie.xml

 -->

| 名称 | 描述 |
|---|---|
| `name` | The cookie name ( `aam_did` is default). |
| `days` | Cookie生命周期（默认为100天）。 |
| `path` | Cookie路径，例如 `'/test'` ( `/` 默认)。 |
| `domain` | 设置Cookie的域，例如 `'adobe.com'` ( `'.'+document.domain` 默认)。 |
| `secure` | 设置仅通过HTTPS连接发送数据的标志。 |

## visitorService属性 {#visitor-service-props}

定义变量使用的 `visitorService` 属性。 此变量是方法的一 `DIL.create` 部分。

`visitorService` 具有以下属性：

| 名称 | 类型 | 描述 |
|---|---|---|
| `namespace` | 字符串 | 必需。表示Experience Cloud组织ID。 这是Experience Cloud核心服务功能所需的。 用于实例化访客ID功能的相同参数。 |

**代码示例：**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
