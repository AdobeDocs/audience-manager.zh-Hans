---
description: 实例级别的DILAPI允许您以编程方式创建和使用Audience Manager对象。 实例级方法增强了由类级方法建立的API功能。
keywords: 创建特征；创建特征
seo-description: The instance-level DIL APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.
seo-title: Instance-level DIL Methods
solution: Audience Manager
title: 实例级别 DIL 方法
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL Implementation
exl-id: 0342439d-708e-461c-b155-a3ee423f5437
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '1153'
ht-degree: 13%

---

# 实例级别 DIL 方法{#instance-level-dil-methods}

>[!WARNING]
>
>自2023年7月起，Adobe已停止开发电子烟产品。 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 扩展。
><br><br>
>现有客户可以继续使用其 [!DNL DIL] 实现。 但是，Adobe将不会开发 [!DNL DIL] 超越了这一点。 建议客户评估 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 长期数据收集策略。
><br><br>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而是。

实例级别 [!UICONTROL DIL] API允许您以编程方式创建和使用Audience Manager对象。 实例级方法增强了由类级方法建立的API功能。

## 实例级别DIL方法快速入门 {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

使用实例级别时 [!UICONTROL DIL] API：

* 访问需要合作伙伴名称和容器命名空间ID (NSID)。 请联系您的Audience Manager客户经理以获取此信息。
* 替换任何示例 *斜体* API文档中的文本，其中包含值、ID或您使用的方法所需的其他变量。

<!-- 

c_instance_start.xml

 -->

## 信号 {#signals}

将客户级别和平台级别映射添加到待处理请求的查询字符串。

<!-- 

r_dil_signals.xml

 -->

**函数签名：** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* 您可以将其他API调用链接到此方法。
>* 如果页面上有Adobe Experience Cloud JavaScript库， `submit()` 会等待云在发送请求之前设置Cookie。

**保留的请求键**

以下请求键已保留，不能被此方法覆盖：

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `obj` | 对象 | 表示平台级别映射的键值对的对象。 参数接受字符串和数组作为对象中的属性值。 |
| `prefix` | 字符串 | 可选。前缀为每个对象键的字符串值（替换原始键）。 |
| `return` | DIL.api | 返回当前DIL实例的API对象。 |

**响应**

返回当前的API对象 [!UICONTROL DIL] 实例。

**示例代码**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
// Method 1 
var obj = { key1 : 1, key2 : 2 }; 
dataLib.api.signals(obj, 'c_').submit(); 
 
// Method 2 
dataLib.api.signals({c_zdid: 54321}).submit(); 
 
// Method 3 
// Will send 'c_key=a&c_key=2&c_key=3' to Audience Manager 
var obj = { key : ['a', 'b', 'c'] }; 
dataLib.api.signals(obj, 'c_').submit(); 
</code></pre>

## traits {#traits}

向挂起的请求的查询字符串添加SID。

<!-- 

r_dil_traits.xml

 -->

**函数签名：** `traits:function (sids){}`

>[!NOTE]
>
>您可以将其他API调用链接到此方法。

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `sids` | 数组 | 数组中的特征区段ID。 |

**响应**

返回当前的API对象 [!UICONTROL DIL] 实例。

**示例代码**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## 日志 {#logs}

将数据添加到待处理请求中的日志文件。

<!-- 

r_dil_logs.xml

 -->

**函数签名：** `logs: function {key1:value1, key2:value2}`

**响应**

返回当前的API对象 [!UICONTROL DIL] 实例。

**示例代码**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});
</code></pre>

## submit {#submit}

将所有待处理数据提交到Audience Manager [!UICONTROL DIL] 实例。

<!-- 

r_dil_submit.xml

 -->

**函数签名：** `submit: function () {}`

>[!NOTE]
>
>您可以将其他API调用链接到此方法。 另外， [!UICONTROL DIL] 将编码数据写入目标Cookie。 例如，空格将编码为 `%20` 和分号为 `%3B`.

**响应**

返回当前的API对象 [!UICONTROL DIL] 实例。

**示例代码**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([ 
<i>123,456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}).submit();
</code></pre>

## afterResult {#afterresult}

在默认目标发布回调之后执行的函数。

<!-- 

r_dil_after_result.xml

 -->

**函数签名：** `afterResult: function (fn) {}`

>[!NOTE]
>
>您可以将其他API调用链接到此方法。

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `fn` | 函数 | 处理目标发布的默认回调处理JSON后要执行的函数。 |

**响应**

返回当前的API对象 [!UICONTROL DIL] 实例。

**示例代码**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.signals({ 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
}).afterResult(function(json){ 
     //Do something with the JSON data returned from the server. 
}).submit();
</code></pre>

## clearData {#cleardata}

清除待处理请求中的所有数据。

<!-- 

r_dil_clear_data.xml

 -->

**函数签名：** `clearData: function () {}`

>[!NOTE]
>
>您可以将其他API调用链接到此方法。

**响应**

返回当前的API对象 [!UICONTROL DIL] 实例。

**示例代码**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ 
     file: 'dil.js' 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

将数据收集服务器未明确定义的自定义查询参数添加到挂起的请求中。

<!-- 

r_dil_custom_query_params.xml

 -->

**函数签名：** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>您可以将其他API调用链接到此方法。

**保留的请求键**

以下请求键已保留，不能被此方法覆盖：

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**响应**

返回当前DIL实例的API对象。

**示例代码**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.customQueryParams({ 
     nid: 54231, 
     ntype: 'default' 
}); 
</code></pre>

## getContainerNSID {#getcontainernsid}

返回以下项的容器NSID的值： [!UICONTROL DIL] 实例。 对于调试和故障排除很有用。

<!-- 

r_dil_get_container_nsid.xml

 -->

**函数签名：** `dil.api.getContainerNSID: function () {}`

**示例代码**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

以字符串数组形式返回按时间顺序排序的事件日志数据。 对于调试和故障排除很有用。

<!-- 

r_dil_get_event_log.xml

 -->

**函数签名：** `dil.api.getEventLog: function () {}`

**示例代码**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});.signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) { 
     alert(log.join('\n')); 
}else{ 
     alert('No log messages'); 
}
</code></pre>

## getPartner {#getpartner}

返回伙伴名称 [!UICONTROL DIL] 实例。 对于调试和故障排除很有用。

<!-- 

r_dil_get_partner.xml

 -->

**函数签名：** `dil.api.getPartner: function () {}`

**示例代码**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

返回当前状态 [!UICONTROL DIL] 实例。 对于调试和故障排除很有用。

<!-- 

r_dil_get_state.xml

 -->

**函数签名：** `dil.api.getState: function () {}`

**示例代码**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message:'This is the first request' 
});.signals({ 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = { 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:{ 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: { 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          }, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     }, 
     destinationPublishingInfo: { 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          + containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

由两个功能组成，允许数据合作伙伴相互之间和Audience Manager交换并同步用户ID。

<!-- 

r_dil_idsync.xml

 -->

**函数签名：**

适用于 [!UICONTROL DIL] 版本2.10和3.1或更高版本。

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代码 </th> 
   <th colname="col2" class="entry"> 同步用户 ID </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.idSync(initConfig) </code> </td> 
   <td colname="col2"> <p>在不同的数据合作伙伴和Audience Manager之间。 例如，合作伙伴x将使用此项将用户ID与合作伙伴y同步，然后将其发送给Audience Manager。 </p> <p> <p><b>重要提示：</b>  此方法已弃用。 请使用 <code> idSyncByURL </code> Adobe Experience Platform Identity Service实例的方法。 </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>当您已经知道用户ID并想要将其发送给Audience Manager时。 </p> <p> <p><b>重要提示：</b>  此方法已弃用。 请使用 <code> idSyncByDataSource </code> Adobe Experience Platform Identity Service实例的方法。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync元素**

`idSync` 可以包含以下内容：

<table id="table_5343BE784E694C67B09A0A8878CF8001"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名称 </th> 
   <th colname="col2" class="entry"> 类型 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> 字符串 </td> 
   <td colname="col3"> <p>Audience Manager 分配的数据提供程序 ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> 字符串 </td> 
   <td colname="col3"> <p>用户的唯一数据提供程序 ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> minutesToLive </code> </td> 
   <td colname="col2"> 数值 </td> 
   <td colname="col3"> <p><i>（可选）</i>设置 Cookie 过期时间。必须为整数。默认值为 20160 分钟（14 天）。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> url </code> </td> 
   <td colname="col2"> 字符串 </td> 
   <td colname="col3"> <p>目标 URL。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**宏**

`idSync` 接受以下宏：

* **`%TIMESTAMP%`：** 生成时间戳（以毫秒为单位）。 用于缓存无效的情况。
* **`%DID%`：** 插入用户的Audience ManagerID。
* **`%HTTP_PROTO%`：** 设置页面协议( `http` 或 `https`)。

**响应**

这两个函数都将返回 `Successfully queued` 如果成功。 如果失败，则将返回错误消息字符串。

**示例代码**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync({ 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync({ 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

## 结果 {#result}

向待处理请求添加回调（接收JSON）。

<!-- 

r_dil_result.xml

 -->

**函数签名：** `result: function (callback) {}`

此回调替换了处理目标发布的默认回调。

>[!NOTE]
>
>您可以将其他API调用链接到此方法。

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `callback` | 函数 | JSONP回调执行的JavaScript函数。 |

**响应**

返回当前的API对象 [!UICONTROL DIL] 实例。

**示例代码**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json){ 
     //Do something, possibly with the JSON data returned from the server. 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` 是一个布尔参数，它控制如何 [!UICONTROL DIL] 调用 [!UICONTROL Data Collection Servers (DCS)] 和Akamai。

<!-- 

dil-secure-data-collection.xml

 -->

* 时间 `secureDataCollection= true` （默认）， [!UICONTROL DIL] 始终进行安全的HTTPS调用。

* 时间 `secureDataCollection= false`， [!UICONTROL DIL] 按照页面设置的安全协议进行HTTP或HTTPS调用。

>[!IMPORTANT]
>
>设置 `secureDataCollection= false` 如果您使用visitorAPI.js和 [!UICONTROL DIL] 在同一页面上。 请参阅下面的代码示例。

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     secureDataCollection: false 
});
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` 是一个布尔值true/false参数，可控制浏览器如何从其他域请求资源。

<!-- 

dil-use-cors-only.xml

 -->

**概述**

`useCORSOnly` 默认为false。 False表示浏览器可以使用CORS或JSONP执行资源检查。 但是， [!UICONTROL DIL] 始终尝试先使用CORS请求资源。 它会在不支持 CORS 的早期浏览器中还原为 JSONP。如果您需要强制浏览器仅使用CORS（例如，对安全性要求较高的站点），请设置 `useCORSOnly:true`.

**代码示例**

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     useCORSOnly: true 
});
</code></pre>

>[!IMPORTANT]
>
>* 我们建议您设置 `useCORSOnly: true` 仅当您确定网站访客拥有支持此功能的浏览器时。
>* 时间 `useCORSOnly: true`， [!UICONTROL DIL] 不会从Internet Explorer 9或更低版本进行ID调用。
>

## useImageRequest {#useimagerequest}

将请求类型更改为图像 `<img>` 从脚本 `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**函数签名：** `useImageRequest: function () {}`

>[!NOTE]
>
>您可以将其他API调用链接到此方法。

**响应**

返回当前的API对象 [!UICONTROL DIL] 实例。

**示例代码**

<pre><code>
var dataLib = DIL.create({ 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [关键变量的名称要求](../features/traits/trait-key-name-requirements.md)
>* [关键变量的前缀要求](../features/traits/trait-variable-prefixes.md)
>* [Adobe Experience Platform Identity服务中的同步函数](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/idsync.html)
>* [DIL 创建](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Adobe Experience Platform Identity服务：UseCORSOnly](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [Adobe Experience Platform Identity服务中的CORS支持](https://experienceleague.adobe.com/docs/id-service/using/reference/cors.html)
