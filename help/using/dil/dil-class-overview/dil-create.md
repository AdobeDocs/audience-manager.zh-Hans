---
description: 创建特定于合作伙伴的DIL实例。
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL创建
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 4%

---

# DIL创建方法{#dil-create}

>[!WARNING]
>
>从2023年7月开始，Adobe已停止开发[!DNL Data Integration Library (DIL)]和[!DNL DIL]扩展。
>
>现有客户可以继续使用其[!DNL DIL]实施。 但是，Adobe在此之后不会开发[!DNL DIL]。 建议客户评估[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)的长期数据收集策略。
>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应改用[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)。

## DIL创建 {#dil-create-new}

创建特定于合作伙伴的[!UICONTROL DIL]实例。

**函数签名：** `DIL.create: function (initConfig) {}`

**initConfig元素**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>`visitorService`属性是&#x200B;*始终*&#x200B;必需的。 此处列出的其他属性是可选的，除非另有说明。

`initConfig`接受以下元素：

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
   <td colname="col3"> <p>此属性设置<span class="keyword"> Audience Manager </span>使用的容器ID以进行ID同步。 如果您在多个网站上部署了<code> containerNSID </code> DIL <span class="wintitle">，则将设置</span>。 每个网站都有自己的容器ID和ID同步。 当您只有1个网站时，容器ID在默认情况下为0，您无需正确进行设置。 请联系您的顾问，以获取您的网站及其容器ID的列表。 </p> <p>在<a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>中，属性<code> idSyncContainerID </code>对应于<code> containerNSID </code> DIL <span class="wintitle">中的</span>。 如果您在多个网站上使用<span class="wintitle"> DIL </span> <i>和</i> ID服务，请注意以下事项： </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">对于每个网站，在<code> containerNSID </code>和<code> idSyncContainerID </code>上设置相同的容器ID。 </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF"><span class="wintitle"> DIL </span>和ID服务都将尝试将ID同步发送到我们的数据收集iFrame。 但是，iFrame会确保<span class="wintitle"> DIL </span>不会触发ID同步。 这样可以防止重复。 </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">仅<span class="wintitle"> DIL </span>将数据发送到<a href="../../features/destinations/destinations.md"> URL目标</a>。 </li> 
     </ul> </p> <p>另请参阅<a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code>用于传入： </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>： <span class="keyword"> Audience Manager </span>分配给您的数据合作伙伴ID。 </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>：您的用户唯一ID。 </li> 
    </ul> <p> <p>重要信息：请仅将未编码的值用于您的ID。 编码将创建双重编码的标识符。 </p> </p> <p> <p>注意：如果您使用<a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>，请使用<code> setCustomerIDs </code>方法而不是<span class="wintitle"> DIL </span>设置客户ID。 查看<a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external">客户ID和身份验证状态</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> 如果为true，则延迟执行所有请求（IFRAME、事件调用、ID同步和目标），直到触发<code> Page Load </code>事件。 默认值为<code> false </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> 默认为False，表示<span class="keyword"> Audience Manager </span>在合作伙伴的域中设置Cookie（设置第一方Cookie）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>重要信息：此元素已在<span class="wintitle"> DIL </span>版本8.0（2018年8月发布）中被弃用。 请改用Adobe Experience Platform Identity服务中的<code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external">函数</a>。 </p> </p> <p> 如果<code> true </code>，则不会将目标发布IFRAME附加到DOM或触发目标。 默认值为<code> false </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>重要信息：此元素已在<span class="wintitle"> DIL </span>版本8.0（2018年8月发布）中被弃用。 请改用Adobe Experience Platform Identity服务中的<code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external">函数</a>。 </p> </p> <p>禁用ID同步。 在使用DIL v6.2及更高版本和访客ID服务时，必须禁用ID同步。 <code> visitorService </code>函数（请参阅下面的示例代码）负责此操作。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> 设置为<code> true </code>可为页面上的所有<span class="wintitle">个DIL </span>实例启用错误报告。 仅适用于布尔值<code> true </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>重要信息：此元素已在<span class="wintitle"> DIL </span>版本8.0（2018年8月发布）中被弃用。 请改用Adobe Experience Platform Identity服务中的<code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external">函数</a>。 </p> </p> <p> 指定目标发布模板是否应使用Akamai进行HTTPS连接。 针对每个合作伙伴启用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>将值从一个键值对关联到另一个键值对。 查看<a href="../../dil/dil-use-cases.md#map-key-values">将键值映射到其他键</a>。 随v2.4发布。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>必需。 </p> <p><code> namespace </code>键值对包含您的<span class="keyword"> Experience Cloud </span>组织ID。 如果您没有此ID，则可以在<span class="wintitle"> Experience Cloud </span>仪表板的<span class="keyword">管理</span>部分中找到它。 您需要管理员权限才能查看此仪表板。 查看<a href="../../faq/faq-features.md">产品特性和功能常见问题解答</a>和<a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external">管理 — 用户管理和常见问题解答</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>必需。 </p> <p> 由<span class="keyword"> Audience Manager </span>提供的合作伙伴名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> 删除脚本和回调。 默认值为<code> False </code>。 仅适用于当前<span class="wintitle">的DIL </span>实例。 随v3.3发布。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>使用从<span class="keyword"> Audience Manager </span>返回的独特用户ID设置Cookie。 查看<a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie属性</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>对于<span class="wintitle"> DIL </span> 6.2或更高版本是必需的。 </p> <p> DIL依赖于<code> setCustomerIDs </code> Adobe Experience Platform Identity Service <span class="wintitle">中的</span>函数将声明的ID传递到<span class="keyword"> Audience Manager </span>。 有关详细信息，请参阅<a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external">客户ID和身份验证状态</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例代码**

示例[!UICONTROL DIL]调用可能类似于以下内容：

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

成功的响应返回了[!UICONTROL DIL]实例。 如果代码配置不正确或遇到错误，则失败的尝试会返回错误对象（未引发）。

## uuidCookie属性 {#uuidcookie-props}

定义`uuidCookie`变量使用的属性。 此变量是`DIL.create`方法的一部分。

`uuidCookie`具有以下属性：

<!-- 

r_dil_uuid_cookie.xml

 -->

| 名称 | 描述 |
|---|---|
| `name` | Cookie名称（`aam_did`是默认名称）。 |
| `days` | Cookie生命周期（默认为100天）。 |
| `path` | Cookie路径，例如`'/test'` （`/`是默认路径）。 |
| `domain` | 设置Cookie的域，如`'adobe.com'` （`'.'+document.domain`为默认设置）。 |
| `secure` | 设置仅通过HTTPS连接发送数据的标志。 |

## visitorService属性 {#visitor-service-props}

定义`visitorService`变量使用的属性。 此变量是`DIL.create`方法的一部分。

`visitorService`具有以下属性：

| 名称 | 类型 | 描述 |
|---|---|---|
| `namespace` | 字符串 | 必需。表示Experience Cloud组织ID。 这是Experience Cloud核心服务功能所需的权限。 用于实例化访客ID功能的相同参数。 |

**代码示例：**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
