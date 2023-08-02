---
description: 创建特定于合作伙伴的DIL实例。
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL 创建
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 8%

---

# DIL创建方法{#dil-create}

>[!WARNING]
>
>自2023年7月起，Adobe已停止开发新能源。 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 扩展。
>
>现有客户可继续使用其 [!DNL DIL] 实现。 但是，Adobe将不会开发 [!DNL DIL] 超越这一步。 我们鼓励客户对 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 长期数据收集策略。
>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而是。

## DIL 创建 {#dil-create-new}

创建特定于合作伙伴的 [!UICONTROL DIL] 实例。

**函数签名：** `DIL.create: function (initConfig) {}`

**initConfig元素**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>此 `visitorService` 属性为 *始终* 必需。 此处列出的其他属性是可选的，除非另有说明。

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
   <td colname="col3"> <p>此属性可设置由 <span class="keyword">Audience Manager</span> 用来进行 ID 同步的容器 ID。您可以设置 <code> containerNSID </code> 如果您拥有 <span class="wintitle"> DIL </span> 跨多个站点部署。 每个网站都有自己的容器ID和ID同步。 当您只有1个网站时，容器ID在默认情况下为0，您无需正确进行设置。 请联系您的顾问，以获取您的网站及其容器ID的列表。 </p> <p>在 <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity服务 </a>，属性 <code> idSyncContainerID </code> 对应于 <code> containerNSID </code> 在 <span class="wintitle"> DIL </span>. 如果您使用的是 <span class="wintitle"> DIL </span> <i>和</i> 跨多个网站的ID服务： </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">对于每个网站，在上设置相同的容器ID <code> containerNSID </code> 和 <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">两者 <span class="wintitle"> DIL </span> 和ID服务将尝试将ID同步发送到我们的数据收集iFrame。 但是，iFrame可确保 <span class="wintitle"> DIL </span> 将不会触发ID同步。 这样可以防止重复。 </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">仅 <span class="wintitle"> DIL </span> 将数据发送到 <a href="../../features/destinations/destinations.md"> URL目标 </a>. </li> 
     </ul> </p> <p>另请参阅， <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> 用于传入： </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>：由分配给您的数据合作伙伴ID <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>：您的用户唯一ID。 </li> 
    </ul> <p> <p>重要信息：请仅将未编码的值用于您的ID。 编码将创建双重编码的标识符。 </p> </p> <p> <p>注意：如果您使用 <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity服务 </a>，使用设置客户ID <code> setCustomerIDs </code> 方法，而不是 <span class="wintitle"> DIL </span>. 请参阅 <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> 客户ID和身份验证状态 </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> 如果为true，则延迟执行所有请求（IFRAME、事件调用、ID同步和目标），直到 <code> Page Load </code> 事件触发。 默认值为 <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> false 默认情况下，这意味着 <span class="keyword"> Audience Manager </span> 在合作伙伴的域中设置Cookie（设置第一方Cookie）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>重要信息：此元素已被弃用， <span class="wintitle"> DIL </span> 版本8.0（2018年8月发布）。 使用 <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> 函数 </a> 在Adobe Experience Platform Identity Service中。 </p> </p> <p> 如果 <code> true </code>，不会将目标发布IFRAME附加到DOM或触发目标。 默认值为 <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>重要信息：此元素已被弃用， <span class="wintitle"> DIL </span> 版本8.0（2018年8月发布）。 使用 <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> 函数 </a> 在Adobe Experience Platform Identity Service中。 </p> </p> <p>禁用 ID 同步。在使用DILv6.2及更高版本和访客ID服务时，必须禁用ID同步。 此 <code> visitorService </code> 函数（请参阅下面的示例代码）负责此操作。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> 设置为 <code> true </code> 启用所有错误报告 <span class="wintitle"> DIL </span> 页面上的实例。 使用布尔值 <code> true </code> 仅限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>重要信息：此元素已被弃用， <span class="wintitle"> DIL </span> 版本8.0（2018年8月发布）。 使用 <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> 函数 </a> 在Adobe Experience Platform Identity Service中。 </p> </p> <p> 指定目标发布模板是否应当使用 Akamai 进行 HTTPS 连接。针对每个合作伙伴启用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>将值从一个键值对关联到另一个键值对。 请参阅 <a href="../../dil/dil-use-cases.md#map-key-values"> 将键值映射到其他键 </a>. 随v2.4发布。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>必需. </p> <p>此 <code> namespace </code> 键值对包含 <span class="keyword"> Experience Cloud </span> 组织ID。 如果您没有此ID，可以在 <span class="wintitle"> 管理 </span> 的部分 <span class="keyword"> Experience Cloud </span> 仪表板。 您需要管理员权限才能查看此仪表板。 请参阅 <a href="../../faq/faq-features.md"> 产品特性和功能常见问题解答 </a> 和 <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> 管理 — 用户管理和常见问题解答 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>必需. </p> <p> 合作伙伴名称由提供 <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> 删除脚本和回调。 默认值为 <code> False </code>. 应用于当前 <span class="wintitle"> DIL </span> 仅实例。 随v3.3发布。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>使用从返回的独特用户ID设置Cookie <span class="keyword"> Audience Manager </span>. 请参阅 <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie属性 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>必需，与 <span class="wintitle"> DIL </span> 6.2或更高版本。 </p> <p> DIL依赖于 <code> setCustomerIDs </code> 中的函数 <span class="wintitle"> Adobe Experience Platform Identity服务 </span> 将声明的ID传递到 <span class="keyword"> Audience Manager </span>. 请参阅 <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> 客户ID和身份验证状态 </a> 以了解更多信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例代码**

示例 [!UICONTROL DIL] 调用可能类似于以下内容：

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

成功的响应会返回 [!UICONTROL DIL] 实例。 如果代码配置不正确或遇到错误，则失败的尝试会返回错误对象（未引发）。

## uuidCookie属性 {#uuidcookie-props}

定义使用的属性 `uuidCookie` 变量。 此变量是 `DIL.create` 方法。

`uuidCookie` 具有以下属性：

<!-- 

r_dil_uuid_cookie.xml

 -->

| 名称 | 描述 |
|---|---|
| `name` | Cookie名称( `aam_did` 默认)。 |
| `days` | Cookie生命周期（默认为100天）。 |
| `path` | Cookie路径，例如 `'/test'` ( `/` 默认)。 |
| `domain` | Cookie设置的域，例如， `'adobe.com'` ( `'.'+document.domain` 默认)。 |
| `secure` | 设置仅通过HTTPS连接发送数据的标志。 |

## visitorService属性 {#visitor-service-props}

定义使用的属性 `visitorService` 变量。 此变量是 `DIL.create` 方法。

`visitorService` 具有以下属性：

| 名称 | 类型 | 描述 |
|---|---|---|
| `namespace` | 字符串 | 必需。表示Experience Cloud的组织ID。 这是Experience Cloud核心服务功能所需的权限。 用于实例化访客ID功能的相同参数。 |

**代码示例:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
