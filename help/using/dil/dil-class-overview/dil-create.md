---
description: 创建特定于合作伙伴的DIL实例。
seo-description: 创建特定于合作伙伴的DIL实例。
seo-title: DIL 创建
solution: Audience Manager
title: DIL 创建
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 11%

---


# DIL创建方法{#dil-create}

## DIL 创建 {#dil-create-new}

创建特定于合作伙伴的 [!UICONTROL DIL] 实例。

**函数签名：** `DIL.create: function (initConfig) {}`

**initConfig元素**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>属 `visitorService` 性始终 *是必* 需的。 此处列出的其他属性是可选的，除非另有说明。

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
   <td colname="col3"> <p>此属性可设置由 <span class="keyword">Audience Manager</span> 用来进行 ID 同步的容器 ID。如果DIL <code> containerNSID </code> 部署在多 <span class="wintitle"> 个 </span> 站点之间，则进行设置。 这些站点中的每个站点都有自己的容器ID和ID同步。 当您只有1个站点时，默认容器ID为0，您无需正确设置。 请与顾问联系，获取您的网站及其列表ID的容器。 </p> <p>在Adobe Experience Platform <a href="https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html" format="https" scope="external"> 身份服 </a>务中，该财 <code> idSyncContainerID </code> 产对应 <code> containerNSID </code> 于DIL <span class="wintitle"></span>。 如果您正在多个站点中使 <span class="wintitle"> 用 </span> DIL <i>和</i> ID服务，请注意以下事项： </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">对于每个站点，在和上设置相同的容器 <code> containerNSID </code> ID <code> idSyncContainerID </code>。 </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">DIL <span class="wintitle"> 和 </span> ID服务都将尝试将ID同步发送到我们的数据收集iFrame。 但是，iFrame可确保 <span class="wintitle"> DIL </span> 不会触发ID同步。 这可防止重复。 </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">只有 <span class="wintitle"> DIL </span> 会向URL目标 <a href="../../features/destinations/destinations.md"> 发送数据 </a>。 </li> 
     </ul> </p> <p>另请参 <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> 阅idSyncContainerID </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> 用于传递： </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>:按Audience Manager分配给您的数据合作伙伴 <span class="keyword"> ID </span>。 </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>:您的用户唯一ID。 </li> 
    </ul> <p> <p>重要： 仅对您的ID使用未编码值。 编码将创建多次编码的标识符。 </p> </p> <p> <p>注意： 如果您使用 <a href="https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform身 </a>份服务，请使用方法 <code> setCustomerIDs </code> 设置客户ID，而不 <span class="wintitle"> 是DIL </span>。 See <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> 如果为true，则将执行所有请求(IFRAME、事件调用、ID同步和目标)，直到事件 <code> Page Load </code> 触发。 默认值为 <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> false 默认情况下，即 <span class="keyword"> Audience Manager </span> 在合作伙伴的域中设置cookie（设置第一方cookie）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>重要： DIL版本8.0(2018 <span class="wintitle"> 年8 </span> 月发布)已弃用此元素。 请改用 <code> visitor.disableIdSyncs </code> Adobe Experience Platform <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> 身份 </a> 服务中的函数。 </p> </p> <p> 如果 <code> true </code>，则不会将发布IFRAME的目标连接到DOM或触发目标。 默认值为 <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>重要： DIL版本8.0(2018 <span class="wintitle"> 年8 </span> 月发布)已弃用此元素。 请改用 <code> visitor.disableIdSyncs </code> Adobe Experience Platform <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> 身份 </a> 服务中的函数。 </p> </p> <p>禁用 ID 同步。在使用DILv6.2+和访客ID服务时，必须禁用ID同步。 函 <code> visitorService </code> 数（请参见下面的示例代码）负责此操作。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> 设置为 <code> true </code> 为页面上的所有DIL <span class="wintitle"></span> 实例启用错误报告。 仅适用于布 <code> true </code> 尔。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>重要： DIL版本8.0(2018 <span class="wintitle"> 年8 </span> 月发布)已弃用此元素。 请改用 <code> visitor.idSyncSSLUseAkamai </code> Adobe Experience Platform <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> 身份 </a> 服务中的函数。 </p> </p> <p> 指定目标发布模板是否应当使用 Akamai 进行 HTTPS 连接。针对每个合作伙伴启用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>将值从一个键值对关联到另一个键值对。 请参 <a href="../../dil/dil-use-cases.md#map-key-values"> 阅将键值映射到其他键 </a>。 随v2.4一起发布。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>必需. </p> <p>键 <code> namespace </code> 值对包含您的Experience Cloud <span class="keyword"> 组 </span> 织ID。 如果您没有此ID，则可以在Experience Cloud仪表板的“管 <span class="wintitle"> 理” </span> 部分找到 <span class="keyword"> 该 </span> ID。 您需要管理员权限才能视图此仪表板。 请参阅产 <a href="../../faq/faq-features.md"> 品功能常见问题解答和 </a> 管理- <a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> 用户管理和常见问题解答 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>必需. </p> <p> 合作伙伴名称，由 <span class="keyword"> Audience Manager </span>提供。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> 删除脚本和回呼。 默认值为 <code> False </code>. 仅应用于当 <span class="wintitle"> 前DIL </span> 实例。 随v3.3一起发布。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>使用从Audience Manager返回的唯一用户ID设置 <span class="keyword"> Cookie </span>。 请参 <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> 阅uidCookie属 </a>性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>DIL <span class="wintitle"> 6. </span> 2或更高版本必需。 </p> <p> DIL依赖 <code> setCustomerIDs </code> Adobe Experience Platform身份 <span class="wintitle"> 服务中的 </span> 函数将声明的ID传递 <span class="keyword"> 到Audience Manager </span>。 See <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a> for more information. </p> </td> 
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

成功的响应会返回 [!UICONTROL DIL] 实例。 如果您的代码配置不当或遇到错误，尝试失败会返回错误对象（未引发）。

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
| `domain` | 设置了cookie的域，例如 `'adobe.com'` ( `'.'+document.domain` 默认)。 |
| `secure` | 设置仅通过HTTPS连接发送数据的标志。 |

## visitorService属性 {#visitor-service-props}

定义变量使用的 `visitorService` 属性。 此变量是方法的一 `DIL.create` 部分。

`visitorService` 具有以下属性：

| 名称 | 类型 | 描述 |
|---|---|---|
| `namespace` | 字符串 | 必需。表示Experience Cloud组织ID。 这是Experience Cloud核心服务功能所需的。 与用于实例化访客ID功能的参数相同。 |

**代码示例:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
