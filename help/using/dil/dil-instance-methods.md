---
description: 通过实例级DIL API，您可以有计划地创建和使用Audience manager对象。 实例级方法增强了类级方法所建立的API功能。
keywords: 创建特征；创建特征
seo-description: 通过实例级DIL API，您可以有计划地创建和使用Audience manager对象。 实例级方法增强了类级方法所建立的API功能。
seo-title: 实例级DIL方法
solution: Audience Manager
title: 实例级DIL方法
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 实例级DIL方法{#instance-level-dil-methods}

通过实例级API, [!UICONTROL DIL] 您可以有计划地创建和使用Audience manager对象。 实例级方法增强了类级方法所建立的API功能。

## 实例级DIL方法入门 {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

使用实例级API时： [!UICONTROL DIL]

* 访问需要合作伙伴名称和容器命名空间ID(NSID)。 请联系Audience manager客户经理以获取此信息。
* 根据您所 *使用的方法* ，将API文档中任何斜体文本示例替换为值、ID或其他变量。

<!-- 

c_instance_start.xml

 -->

## 信号 {#signals}

将客户和平台级映射添加到待处理请求的查询字符串。

<!-- 

r_dil_signals.xml

 -->

**** 函数签名： `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* 您可以将其他API调用链接到此方法。
>* 如果Adobe Experience Cloud javaScript库位于页面上， `submit()` 则在发送请求之前等待Cloud设置Cookie。


**保留请求密钥**

以下请求密钥是保留的，此方法无法覆盖：

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `obj` | 对象 | 表示平台级映射的键值对的对象。 参数将字符串和数组作为对象中的属性值接受。 |
| `prefix` | 字符串 | 可选。每个对象键前缀的字符串值（替换原始键）。 |
| `return` | DIL.api | 返回当前DIL实例的API对象。 |

**响应**

返回当前实例的API对 [!UICONTROL DIL] 象。

**示例代码**

<pre><code>
var dataLib = DIL.create({ partner:“<i>partnerName</i>”容器NSID:容 <i>器NSID</i> });
 
//方法1 var obj = { key1 :1, key2:2 };
dataLib.api.signals(obj, 'c_')。submit();
 
//方法2 dataLib.api.signals({c_zdid:54321})。submit();
 
//方法3 //将“c_key=a&amp;c_key=2&amp;c_key=3”发送给Audience Manager var obj = { key:['a', 'b', 'c'] };
dataLib.api.signals(obj, 'c_')。submit(); 
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [关键变量的名称要求](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

将SID添加到待定请求的查询字符串。

<!-- 

r_dil_traits.xml

 -->

**** 函数签名： `traits:function (sids){}`

>[!NOTE]
>
>您可以将其他API调用链接到此方法。

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `sids` | 数组 | 数组中的特征段ID。 |

**响应**

返回当前实例的API对 [!UICONTROL DIL] 象。

**示例代码**

<pre><code>
var partnerObject = DIL.create({ partner:'<i>partner name</i>', containerNSID: <i>NSID</i> });
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

向待处理请求中的日志文件添加数据。

<!-- 

r_dil_logs.xml

 -->

**** 函数签名： `logs: function {key1:value1, key2:value2}`

**响应**

返回当前实例的API对 [!UICONTROL DIL] 象。

**示例代码**

<pre><code>
var partnerObject = DIL.create({ partner:“<i>partner</i>”, containerNSID: <i>NSID</i> });
partnerObject.api.logs({文件：'dil.js'，消息：'这是第一个请求' });
</code></pre>

## submit {#submit}

将所有待处理数据提交到Audience Manager以便实 [!UICONTROL DIL] 例。

<!-- 

r_dil_submit.xml

 -->

**** 函数签名： `submit: function () {}`

>[!NOTE]
>
>您可以将其他API调用链接到此方法。 此外， [!UICONTROL DIL] 将编码数据写入目标cookie。 例如，空格编码为，分 `%20` 号编码为 `%3B`。

**响应**

返回当前实例的API对 [!UICONTROL DIL] 象。

**示例代码**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
dataLib.api.traits([<i>123,456, 789</i>])。logs({ file:'dil.js'，消息：'这是第一个请求' })。signals({ c_zdid: <i>111</i> d_dma:'<i>default</i>' })。submit();
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [关键变量的前缀要求](../features/traits/trait-variable-prefixes.md)


## afterResult {#afterresult}

在默认目标发布回调后执行的函数。

<!-- 

r_dil_after_result.xml

 -->

**** 函数签名： `afterResult: function (fn) {}`

>[!NOTE]
>
>您可以将其他API调用链接到此方法。

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `fn` | 函数 | JSON后要执行的函数由用于处理目标发布的默认回调处理。 |

**响应**

返回当前实例的API对 [!UICONTROL DIL] 象。

**示例代码**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
dataLib.api.signals({ c_zdid: <i>54321</i> d_dma:'<i>default</i>' })。afterResult(function(json){ //对从服务器返回的JSON数据执行某些操作。 
}).submit();
</code></pre>

## clearData {#cleardata}

清除待处理请求中的所有数据。

<!-- 

r_dil_clear_data.xml

 -->

**** 函数签名： `clearData: function () {}`

>[!NOTE]
>
>您可以将其他API调用链接到此方法。

**响应**

返回当前实例的API对 [!UICONTROL DIL] 象。

**示例代码**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
dataLib.api.traits([<i>123,456, 789</i>])。logs({文件：“dil.js”消息：'这是第一个请求' })。signals({ c_zdid: <i>111</i> d_dma:'<i>default</i>' });
 
//重置待处理的dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

将数据收集服务器未明确定义的自定义查询参数添加到暂挂请求中。

<!-- 

r_dil_custom_query_params.xml

 -->

**** 函数签名： `customQueryParams: function (obj) {}`

>[!NOTE]
>
>您可以将其他API调用链接到此方法。

**保留请求密钥**

以下请求密钥是保留的，此方法无法覆盖：

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
var partnerObject = DIL.create({ partner:“<i>partner</i>”, containerNSID: <i>NSID</i> });
partnerObject.api.customQueryParams({ nid:54231，类型：'default' }); 
</code></pre>

## getContainerNSID {#getcontainernsid}

返回实例的容器NSID的 [!UICONTROL DIL] 值。 对于调试和疑难解答很有用。

<!-- 

r_dil_get_container_nsid.xml

 -->

**** 函数签名： `dil.api.getContainerNSID: function () {}`

**示例代码**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
//验证容器NSID var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

以字符串数组的形式返回按时间顺序排序的事件日志数据。 对于调试和疑难解答很有用。

<!-- 

r_dil_get_event_log.xml

 -->

**** 函数签名： `dil.api.getEventLog: function () {}`

**示例代码**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
dataLib.api.traits([<i>123, 456, 789</i>])。logs({ file:'dil.js'，消息：'这是第一个请求' });.signals({ c_zdid: <i>111</i> d_dma:'<i>default</i>' });.submit();
 
//检查消息日志var log = dataLib.api.getEventLog();
if(log &amp;&amp; log.length){ alert(log.join('\n'));
}else{ alert（'无日志消息'）;
}</code></pre>

## getPartner {#getpartner}

返回实例的合作伙伴 [!UICONTROL DIL] 名称。 对于调试和疑难解答很有用。

<!-- 

r_dil_get_partner.xml

 -->

**** 函数签名： `dil.api.getPartner: function () {}`

**示例代码**

<pre><code>
var dataLib = DIL.create({ partner:“<i>partnerName</i>”容器NSID:容 <i>器NSID</i> });
 
//验证合作伙伴名称var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

返回当前实例的状 [!UICONTROL DIL] 态。 对于调试和疑难解答很有用。

<!-- 

r_dil_get_state.xml

 -->

**** 函数签名： `dil.api.getState: function () {}`

**示例代码**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
dataLib.api.traits([<i>123, 456, 789</i>])。logs({ file:'dil.js', message:'This is the first request' });.signals({ c.zdid: <i>111</i> d_dma:'<i>default</i>' });.submit();
 
var state = dataLib.api.getState();
 
/*状态状态的对象轮廓= { pendingRequest:{<i>待定数据，用于调用服务器</i>}, otherRequestInfo:{ firingQueue:[]，已触发：[]，触发：false，错误：[]，保留密钥：{ sids:true, pdata:true, logdata:true，回调：true, postCallbackFn:true, useImageRequest:true, }, firstRequestHasFired:false, num_of_jsonp_responses:0, num_of_jsonp_errors:0, num_of_img_responses:0, num_of_img_errors:0 },destinationPublishingInfo:{ THROTTLE_START:3000, throttleTimerSet:false, id:"destination_publishing_iframe_' + partner + '_' + containerNSID, url:(constants.isHTTPS › 'https://':'https://fast.')+ partner + '.demdex.net/dest3.html?d_nsid=' + containerNSID + '#' + encodeURIComponent(document.location.href), iframe:null, iframeHasLoaded:false, sendingMessages:false，消息：[], messageSendingInterval:常量。POST_MESSAGE_ENABLED › 15:100, //建议IE 6和7使用100ms，其他浏览器使用15msjson已处理：[ ] } */</code></pre>

## idSync {#idsync}

由两个功能组成，它们使数据合作伙伴能够在他们与Audience Manager之间交换和同步用户ID。

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
   <td colname="col2"> <p>不同数据合作伙伴和Audience Manager之间。 例如，合作伙伴x将使用它将用户ID与合作伙伴y同步，然后将其发送到Audience Manager。 </p> <p> <p><b></b> 重要说明： 此方法已弃用。 请使用Experience Cloud <code> ID服 </code> 务实例的idSyncByURL方法。 </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>当您已经知道用户ID并希望将其发送到Audience Manager时。 </p> <p> <p><b></b> 重要说明： 此方法已弃用。 请使用Experience Cloud <code> ID服务 </code> 实例的idSyncByDataSource方法。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync Elements**

`idSync` 可以由以下组成：

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

* **`%TIMESTAMP%`** :生成时间戳（以毫秒为单位）。 用于缓存无效的情况。
* **`%DID%`** :插入用户的Audience Manager ID。
* **`%HTTP_PROTO%`** :设置页面协议( `http` 或 `https`)。

**响应**

Both functions return `Successfully queued` if successful. 如果失败，则将返回错误消息字符串。

**示例代码**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
//将URL与宏替换为dilInstance.api.idSync({ dpid:'23', //必须为字符串url:'//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net %2Fibs%3Adpid%3D420%26dpuuid%3D%7Buid%7D7D',minutesToLive:20160 //可选，默认为20160分钟（14天）};
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
//触发'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&amp;dpuuid=&lt;dpuuid&gt;' dilInstance.api.aamIdSync({ dpid:'23', //必须是字符串dpuuid:'98765', // must be a string minutesToLive:20160 //可选，默认为20160分钟（14天）};
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [Experience Cloud ID服务中的同步功能](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## result {#result}

将回调（接收JSON）添加到待处理请求。

<!-- 

r_dil_result.xml

 -->

**** 函数签名： `result: function (callback) {}`

此回调替换处理目标发布的默认回调。

>[!NOTE]
>
>您可以将其他API调用链接到此方法。

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `callback` | 函数 | 由JSONP回调执行的JavaScript函数。 |

**响应**

返回当前实例的API对 [!UICONTROL DIL] 象。

**示例代码**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
dataLib.api.traits([<i>123, 456, 789</i>])。result(function(json){ //执行某些操作，可能使用从服务器返回的JSON数据。 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` 是一个布尔参数，它控制 [!UICONTROL DIL] 如何调用和 [!UICONTROL Data Collection Servers (DCS)] Akamai。

<!-- 

dil-secure-data-collection.xml

 -->

* (默 `secureDataCollection= true` 认)时，始 [!UICONTROL DIL] 终进行安全的HTTPS调用。

* 当 `secureDataCollection= false`时， [!UICONTROL DIL] 请按照页面设置的安全协议进行HTTP或HTTPS调用。

>[!IMPORTANT]
>
>如果 `secureDataCollection= false` 您使用visitorAPI.js并在同一页 [!UICONTROL DIL] 面上进行设置。 请参阅下面的代码示例。

<pre><code class="js">
var dilInstance = DIL.create({ ...
     secureDataCollection:false });
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [DIL创建](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` 是一个布尔值true/false参数，它控制浏览器如何从其他域请求资源。

<!-- 

dil-use-cors-only.xml

 -->

**概述**

`useCORSOnly` 默认为false。 False表示浏览器可以使用CORS或JSONP执行资源检查。 但是， [!UICONTROL DIL] 始终会尝试先向CORS请求资源。 它会在不支持 CORS 的早期浏览器中还原为 JSONP。如果您需要强制浏览器仅使用CORS（例如对于具有高安全性要求的站点），请设置 `useCORSOnly:true`。

**代码示例**

<pre><code class="js">
var dilInstance = DIL.create({ ...
     useCORSOnly:true });
</code></pre>

>[!IMPORTANT]
>
>* 我们建议您仅在确 `useCORSOnly: true` 定网站访客拥有支持此功能的浏览器时进行设置。
>* 当 `useCORSOnly: true`时， [!UICONTROL DIL] 将不从Internet explorer版本9或更早版本进行ID调用。
>



>[!MORE_LIKE_THIS]
>
>* [DIL创建](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Experience Cloud ID服务：UseCORSOnly](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [Experience Cloud ID 服务中的 CORS 支持](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## useImageRequest {#useimagerequest}

将请求类型从脚本更 `<img>` 改为图像 `<src>`。

<!-- 

r_dil_use_image_request.xml

 -->

**** 函数签名： `useImageRequest: function () {}`

>[!NOTE]
>
>您可以将其他API调用链接到此方法。

**响应**

返回当前实例的API对 [!UICONTROL DIL] 象。

**示例代码**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
dataLib.api.traits([<i>123, 456, 789</i>])。useImageRequest()。submit();
</code></pre>

