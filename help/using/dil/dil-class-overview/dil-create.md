---
description: 创建特定于合作伙伴的DIL实例。
seo-description: 创建特定于合作伙伴的DIL实例。
seo-title: DIL创建
solution: Audience Manager
title: DIL创建
uuid: 6e05460-703c-4a97-af2 a-8207c50013 db
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL create method{#dil-create}

## DIL create {#dil-create-new}

Creates a partner-specific [!UICONTROL DIL] instance.

**函数签名：**`DIL.create: function (initConfig) {}`

**initConfig Elements**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>`visitorService`*始终* 需要该属性。除非另有指明，否则此处列出的其他属性为可选属性。

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
   <td colname="col3"> <p>此属性可设置由 <span class="keyword">Audience Manager</span> 用来进行 ID 同步的容器 ID。<code></code> 如果您在多个站点中部署 <span class="wintitle"> DIL </span> ，则可以设置ContainerSID。每个站点都有自己的容器ID和ID同步。只有个站点时，默认情况下容器ID为0，您无需正确设置此设置。请联系您的顾问，获取站点及其容器ID的列表。 </p> <p>In the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID service </a>, the property <code> idSyncContainerID </code> corresponds to <code> containerNSID </code> in <span class="wintitle"> DIL </span>. Note the following if you're using <span class="wintitle"> DIL </span> <i>and</i> the ID service across multiple sites: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">For each site, set the same container IDs on <code> containerNSID </code> and <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF"><span class="wintitle"> DIL </span> 和ID服务都会尝试将ID同步到我们的数据收集iFrame。However, the iFrame ensures that <span class="wintitle"> DIL </span> won't fire an ID sync. 这可以防止复制。 </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Only <span class="wintitle"> DIL </span> sends data to a <a href="../../features/destinations/destinations.md"> URL destination </a>. </li> 
     </ul> </p> <p>See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 声明ID </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> 
    <draft-comment> 
     <p>Sends the <a href="../../features/declared-ids.md"> Declared ID variables </a> on every event call to <span class="keyword"> Audience Manager </span>. </p> 
    </draft-comment> <p> <code> delaCardId </code> 用于传入： </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>： <span class="keyword"> Audience Manager为您分配的数据合作伙伴ID </span>。 </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuid </code>：用户的唯一ID。 </li> 
    </ul> <p> <p>重要：仅对ID使用未编码的值。编码将创建双编码标识符。 </p> </p> <p> <p>Note:  If you use the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID Service </a>, set customer IDs with the <code> setCustomerIDs </code> method instead of <span class="wintitle"> DIL </span>. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAlluntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> If true, defers all requests (IFRAME, event calls, ID sync, and destinationing) from executing until the <code> Page Load </code> event fires. Default is <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disable声明DouuIDCookie </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> false by default, which means <span class="keyword"> Audience Manager </span> sets a cookie in the partner's domain (sets a first party cookie). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <code> visitor.disableIdSyncs </code> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> function </a> in the Experience Cloud ID Service instead. </p> </p> <p> If <code> true </code>, will not attach the destination publishing IFRAME to the DOM or fire destinations. Default is <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <code> visitor.disableIdSyncs </code> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> function </a> in the Experience Cloud ID Service instead. </p> </p> <p>禁用 ID 同步。您必须在使用DIL v6.2+和访问者ID服务时禁用ID。<code> togortorService </code> 函数(请参阅下面的示例代码)处理此操作。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enabErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> Set to <code> true </code> to enable error reporting for all <span class="wintitle"> DIL </span> instances on the page. Works with Boolean <code> true </code> only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> <p>Important:  This element has been deprecated with <span class="wintitle"> DIL </span> version 8.0 (released August 2018). Use the <code> visitor.idSyncSSLUseAkamai </code> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idSyncSSLUseAkamai.html" format="https" scope="external"> function </a> in the Experience Cloud ID Service instead. </p> </p> <p> 指定目标发布模板是否应当使用 Akamai 进行 HTTPS 连接。针对每个合作伙伴启用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 映射映射 </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>将值从一个键-值对关联到另一个键值对。See <a href="../../dil/dil-use-cases.md#map-key-values"> Map Key Values to Other Keys </a>. 随v2.4一起发布。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>必需. </p> <p><code> 命名空间 </code> 键-值对包含 <span class="keyword"> Experience Cloud </span> 组织ID。If you don't have this ID, you can find it in the <span class="wintitle"> Administration </span> section of the <span class="keyword"> Experience Cloud </span> dashboard. 您需要管理员权限才能查看此控制板。See the <a href="../../faq/faq-features.md"> Product Features and Functions FAQ </a> and <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> Administration - User Management and FAQ </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 合作伙伴 </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>必需. </p> <p> <span class="keyword"> Audience Manager提供的合作伙伴名称 </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptSandCallback </code> </p> </td> 
   <td colname="col2"> <p>布尔值 </p> </td> 
   <td colname="col3"> <p> 删除脚本和回调。Default is <code> False </code>. Applies to the current <span class="wintitle"> DIL </span> instance only. 在v3.3中发布。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID Cookie </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>Sets a cookie with the unique user ID returned from <span class="keyword"> Audience Manager </span>. See <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie Properties </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> VisitorService </code> </p> </td> 
   <td colname="col2"> <p>对象 </p> </td> 
   <td colname="col3"> <p>Required with <span class="wintitle"> DIL </span> 6.2 or greater. </p> <p> DIL relies on the <code> setCustomerIDs </code> function in the <span class="wintitle"> Experience Cloud ID Service </span> to pass declared IDs into <span class="keyword"> Audience Manager </span>. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例代码**

A sample [!UICONTROL DIL] call could look similar to the following:

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

A successful response returns the [!UICONTROL DIL] instance. 如果您的代码配置不当或遇到错误，则失败的尝试会返回错误对象(不引发)。

## uuidCookie Properties {#uuidcookie-props}

Defines the properties used by the `uuidCookie` variable. This variable is part of the `DIL.create` method.

`uuidCookie` 具有以下属性：

<!-- 

r_dil_uuid_cookie.xml

 -->

| 名称 | 描述 |
|---|---|
| `name` | The cookie name ( `aam_did` is default). |
| `days` | Cookie终身(默认为100天)。 |
| `path` | Cookie path, e.g., `'/test'` ( `/` is default). |
| `domain` | The domain the cookie is set in, e.g., `'adobe.com'` ( `'.'+document.domain` is default). |
| `secure` | 设置一个标志，以仅通过HTTPS连接发送数据。 |

## visitorService Properties {#visitor-service-props}

Defines the properties used by the `visitorService` variable. This variable is part of the `DIL.create` method.

`visitorService` 具有以下属性：

| 名称 | 类型 | 描述 |
|---|---|---|
| `namespace` | 字符串 | 必需。表示Experience Cloud组织ID。这是Experience Cloud核心服务功能所必需的。用于实例化访客ID功能的相同参数。 |

**代码示例：**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
