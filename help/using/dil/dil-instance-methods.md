---
description: 利用实例级的DIL API，您可以以编程方式创建和使用Audience Manager对象。实例级方法增强了类级方法所建立的API功能。
keywords: 创建特征；创建特征
seo-description: 利用实例级的DIL API，您可以以编程方式创建和使用Audience Manager对象。实例级方法增强了类级方法所建立的API功能。
seo-title: 实例级DIL方法
solution: Audience Manager
title: 实例级DIL方法
uuid: a5147bb-51d5-41d4-a78 a-e550 f7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Instance-level DIL Methods{#instance-level-dil-methods}

The instance-level [!UICONTROL DIL] APIs let you programmatically create and work with Audience Manager objects. 实例级方法增强了类级方法所建立的API功能。

## Getting started with Instance-level DIL Methods {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

When working with the instance-level [!UICONTROL DIL] APIs:

* 访问需要一个合作伙伴名称和容器命名空间ID(NSID)。要获取此信息，请与Audience Manager客户经理联系。
* Replace any sample *italicized* text in the API documentation with value, ID, or other variable as required by the method you&#39;re working with.

<!-- 

c_instance_start.xml

 -->

## signals {#signals}

向待定请求的查询字符串添加客户和平台级别映射。

<!-- 

r_dil_signals.xml

 -->

**函数签名：**`signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* 您可以对此方法进行其他API调用。
>* If the Adobe Experience Cloud JavaScript library is on the page, `submit()` waits for the Cloud to set a cookie before sending a request.


**保留的请求密钥**

保留以下请求密钥，不能通过此方法覆盖：

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `obj` | 对象 | 表示平台级映射的键值对的对象。参数将字符串和数组作为属性值接受对象中的属性值。 |
| `prefix` | 字符串 | 可选。每个对象键前缀的字符串值(替换原始密钥)。 |
| `return` | DIL. api | 返回当前DIL实例的API对象。 |

**响应**

Returns the API object of the current [!UICONTROL DIL] instance.

**示例代码**

<pre><code>var datalb= DIL. create({
合作伙伴：'<i>parterName</i>'
containernSite： <i>containernSID</i> })；

//方法var obj={key1：1，键2：2}；
DataLibb. api.信号(obj，'c_'). mit()；

//Method DataLibb. api.信号({c_ zdo：54321}). mit()；

//方法//将“c_ key= a&amp; c_ key=2&amp; c_ key=3”发送到Audience Manager 
var obj={key：['a'、'b'、'c']}；
DataLibb. api.信号(obj，'c_'). mit()；</code>
</pre>

>[!MORE_ LIKE_ This]
>
>* [关键变量的名称要求](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

将SID添加到待定请求的查询字符串。

<!-- 

r_dil_traits.xml

 -->

**函数签名：**`traits:function (sids){}`

>[!NOTE]
>
>您可以对此方法进行其他API调用。

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `sids` | 数组 | 特征区段ID在数组中。 |

**响应**

Returns the API object of the current [!UICONTROL DIL] instance.

**示例代码**

<pre><code>var PartnerObject= DIL. create({
合作伙伴：“<i>合作伙伴姓名</i>”，
containernSite： <i>NSID</i> })；
PartnerObject. api. traits(<i>[123，456，789]</i>)；</code>
</pre>

## logs {#logs}

在待定请求中添加数据以记录文件。

<!-- 

r_dil_logs.xml

 -->

**函数签名：**`logs: function {key1:value1, key2:value2}`

**响应**

Returns the API object of the current [!UICONTROL DIL] instance.

**示例代码**

<pre><code>var PartnerObject= DIL. create({
合作伙伴：<i>“合作伙伴</i>”，
containernSite： <i>NSID</i> })；
PartnerObject. api. logs({
文件：“dil. js”，
消息：“这是第一个请求”})；</code>
</pre>

## submit {#submit}

Submits all pending data to Audience Manager for the [!UICONTROL DIL] instance.

<!-- 

r_dil_submit.xml

 -->

**函数签名：**`submit: function () {}`

>[!NOTE]
>
>您可以对此方法进行其他API调用。Also, [!UICONTROL DIL] writes encoded data to a destination cookie. For example, spaces are encoded as `%20` and semicolons as `%3B`.

**响应**

Returns the API object of the current [!UICONTROL DIL] instance.

**示例代码**

<pre><code>var datalb= DIL. create({
合作伙伴：“<i>parterName</i>”，
containernSite： <i>containernSID</i> })；

DataLibb. api. traits([<i>123,456，789</i>]). 
log({
文件：“dil. js”，
消息：“这是第一个请求”}).信号({
c_ zdo： <i>1111</i> 
d_ DMA：'<i>default</i>'}). 
mit()；</code>
</pre>

>[!MORE_ LIKE_ This]
>
>* [关键变量的前缀要求](../features/traits/trait-variable-prefixes.md)


## afterResult {#afterresult}

在默认目标发布回调之后执行的函数。

<!-- 

r_dil_after_result.xml

 -->

**函数签名：**`afterResult: function (fn) {}`

>[!NOTE]
>
>您可以对此方法进行其他API调用。

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `fn` | 函数 | 在JSON由处理目标发布的默认回调处理后要执行的函数。 |

**响应**

Returns an API object of the current [!UICONTROL DIL] instance.

**示例代码**

<pre><code>var datalb= DIL. create({
合作伙伴：“<i>parterName</i>”，
containernSite： <i>containernSID</i> })；

DataLibb. api.信号({
c_ zdo： <i>54321</i> 
d_ DMA：'<i>default</i>'}). 
afterResult(function(json){
使用服务器返回的JSON数据进行一些操作。 
}).submit();
</code></pre>

## clearData {#cleardata}

清除待定请求中的所有数据。

<!-- 

r_dil_clear_data.xml

 -->

**函数签名：**`clearData: function () {}`

>[!NOTE]
>
>您可以对此方法进行其他API调用。

**响应**

Returns the API object of the current [!UICONTROL DIL] instance.

**示例代码**

<pre><code>var datalb= DIL. create({
合作伙伴：“<i>parterName</i>”，
containernSite： <i>containernSID</i> })；

DataLibb. api. traits([<i>123,456，789</i>]). log({
文件：'dil. js'
消息：“这是第一个请求”}).信号({
c_ zdo： <i>1111</i> 
d_ DMA：'<i>default</i>'})；

//Reset待定数据Datalb. 
clearData()；</code>
</pre>

## customQueryParams {#customqueryparams}

向待定请求中添加未显式定义的自定义查询参数。

<!-- 

r_dil_custom_query_params.xml

 -->

**函数签名：**`customQueryParams: function (obj) {}`

>[!NOTE]
>
>您可以对此方法进行其他API调用。

**保留的请求密钥**

保留以下请求密钥，不能通过此方法覆盖：

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**响应**

返回当前DIL实例的API对象。

**示例代码**

<pre><code>var PartnerObject= DIL. create({
合作伙伴：<i>“合作伙伴</i>”，
containernSite： <i>NSID</i> })；
PartnerObject. api. customqueryParams({{
nid：54231，
nype：'default'})；</code>
</pre>

## getContainerNSID {#getcontainernsid}

Returns the value of the container NSID for the [!UICONTROL DIL] instance. 适用于调试和疑难解答。

<!-- 

r_dil_get_container_nsid.xml

 -->

**函数签名：**`dil.api.getContainerNSID: function () {}`

**示例代码**

<pre><code>var datalb= DIL. create({
合作伙伴：“<i>parterName</i>”，
containernSite： <i>containernSID</i> })；

//Verify容器NSID 
var nsid= DataLibb. api. getContainernSsid()；</code>
</pre>

## getEventLog {#geteventlog}

将时间顺序排序的事件日志数据返回为一系列字符串。适用于调试和疑难解答。

<!-- 

r_dil_get_event_log.xml

 -->

**函数签名：**`dil.api.getEventLog: function () {}`

**示例代码**

<pre><code>var datalb= DIL. create({
合作伙伴：“<i>parterName</i>”，
containernSite： <i>containernSID</i> })；

DataLibb. api. traits([<i>123，456，789</i>]). log({
文件：“dil. js”，
消息：“这是第一个请求”})；.信号({
c_ zdo： <i>1111</i> 
d_ DMA：'<i>default</i>'})；. mit()；

nog log for messages 
var log= DataLibb. api. getEventLog()；
if(log&amp;&amp; log. length){
alert(log. join('\ n'))；
}其他{
alert('No log messages')；
}}</code>
</pre>

## getPartner {#getpartner}

Returns the partner name for a [!UICONTROL DIL] instance. 适用于调试和疑难解答。

<!-- 

r_dil_get_partner.xml

 -->

**函数签名：**`dil.api.getPartner: function () {}`

**示例代码**

<pre><code>var datalb= DIL. create({
合作伙伴：'<i>parterName</i>'
containernSite： <i>containernSID</i> })；

//Verify合作伙伴名称var合作伙伴= 
DataLibb. api. getPartner()；</code>
</pre>

## getState {#getstate}

Returns the state of the current [!UICONTROL DIL] instance. 适用于调试和疑难解答。

<!-- 

r_dil_get_state.xml

 -->

**函数签名：**`dil.api.getState: function () {}`

**示例代码**

<pre><code>var datalb= DIL. create({
合作伙伴：“<i>parterName</i>”，
containernSite： <i>containernSID</i> })；

DataLibb. api. traits([<i>123，456，789</i>]). log({
文件：“dil. js”，
消息：“这是第一个请求”})；.信号({
c. zdo： <i>1111</i> 
d_ DMA：'<i>default</i>'})；. mit()；

var state= dataAlb. api. getState()；

/*状态状态的对象轮廓={
升级请求：{<i>待定数据用于调用服务器</i>}，
otrosestInfo：{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{
FiringQueue：[]，
frefied：[]，
触发：false，
错误：[]，
ReservedKeys：{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{
sid：true，
pdata：true，
日志数据：true，
回调：true，
PostCallBackFn：true，
useImageRequest：true，
}
FirstRequestThasfied：false，
num_ of_ jsonp_ response：0，
num_ of_ jsonp_ errors：0，
num_ of_ img_ responses：0，
num_ of_ img_ errors：0
}
目标发布者信息：{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{
TROKET_ START：3000，
ThrottleTimerSet：false，
id：“destination_ publishing_ iframe_'+ partner+'_'+ containernssid，
url：(常量. isHTTPS？https://'：'https://fast.')+合作伙伴+'.demdex.net/dest3.html?d_nsid='
+ containernSsid+'#'+ encodeURIComponent(document. location. href)，
iframe：null，
iFrameHasLoaded：false，
SendingMessages：false，
消息：[]，
MessagesendingInterval：常量. POST_ MESSAGE_ Enabled？15: 100, 
               //Recommend 100ms for IE 6 &amp; 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

由两个功能组成，它们允许数据合作伙伴在自己和Audience Manager之间交换和同步用户ID。

<!-- 

r_dil_idsync.xml

 -->

**函数签名：**

Works with [!UICONTROL DIL] versions 2.10 and 3.1 or higher.

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代码 </th> 
   <th colname="col2" class="entry"> 同步用户 ID </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil. Instance. api. idSync(initConfig) </code> </td> 
   <td colname="col2"> <p>不同数据合作伙伴和Audience Manager之间。例如，合作伙伴x将使用此功能将用户ID与合作伙伴y同步，然后将其发送到Audience Manager。 </p> <p> <p><b>重要：</b> 此方法已弃用。Please use the <code> idSyncByURL </code> method of the Experience Cloud ID Service instance. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil. Instance. api. aiasSync(initConfig) </code> </td> 
   <td colname="col2"> <p>当您知道用户ID并希望将其发送到Audience Manager时。 </p> <p> <p><b>重要：</b> 此方法已弃用。Please use the <code> idSyncByDataSource </code> method of the Experience Cloud ID Service instance. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**IdSync Elements**

`idSync` 可由以下各项组成：

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

* **`%TIMESTAMP%`：** 生成时间戳(以毫秒为单位)。用于缓存无效的情况。
* **`%DID%`：** 插入用户的Audience Manager ID。
* **`%HTTP_PROTO%`：** 设置页面协议( `http` 或 `https`)。

**响应**

Both functions return `Successfully queued` if successful. 如果失败，则将返回错误消息字符串。

**示例代码**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">//使用宏触发url的url替换了DilinStation. 
api. idSync({同步)
dpid：'23'，//必须是字符串
url：'//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net%2Fibs%3Adid%3D420%dpuid%3D%7B%7Buid%7D%7D'，
DetailTestLive：20160//可选，默认为20160分钟(14天)})；</code>
</pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">//触发“https:/https:'+”//dpm.demdex.net/ibs:dpid=&lt; dpid&gt;&amp; dpuid=&lt; dpuuid&gt;'Dicklocation. 
api. aiasSync({
dpid：'23'，//必须是字符串
dpuid：'98765'，//必须是字符串
DetailTestLive：20160//可选，默认为20160分钟(14天)})；</code>
</pre>

>[!MORE_ LIKE_ This]
>
>* [Experience Cloud ID服务中的同步功能](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## result {#result}

将一个回调(接收JSON)添加到待处理的请求。

<!-- 

r_dil_result.xml

 -->

**函数签名：**`result: function (callback) {}`

此回调替换处理目标发布的默认回调。

>[!NOTE]
>
>您可以对此方法进行其他API调用。

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `callback` | 函数 | JSONP回调执行的JavaScript函数。 |

**响应**

Returns the API object of the current [!UICONTROL DIL] instance.

**示例代码**

<pre><code>var datalb= DIL. create({
合作伙伴：“<i>parterName</i>”，
containernSite： <i>containernSID</i> })；

DataLibb. api. traits([<i>123，456，789</i>]). result(json){
可能使用从服务器返回的JSON数据来进行某些操作。 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` 是一个布尔参数，用于控制 [!UICONTROL DIL] 如何调用 [!UICONTROL Data Collection Servers (DCS)] 和Akamai。

<!-- 

dil-secure-data-collection.xml

 -->

* When `secureDataCollection= true` (default), [!UICONTROL DIL] always makes secure, HTTPS calls.

* When `secureDataCollection= false`, [!UICONTROL DIL] makes either HTTP or HTTPS calls by following the security protocol set by the page.

>[!IMPORTANT]
>
>Set `secureDataCollection= false` if you use visitorAPI.js and [!UICONTROL DIL] on the same page. 请参阅下面的代码示例。

<pre><code class="js">var dilinStation= DIL. create({
…
SecureDataCollection：false})；</code>
</pre>

>[!MORE_ LIKE_ This]
>
>* [DIL创建](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` 是一个布尔值true/false参数，用于控制浏览器从其他域请求资源的方式。

<!-- 

dil-use-cors-only.xml

 -->

**概述**

`useCORSOnly` 默认为false。Flex表示浏览器可以使用CORS或JSONP执行资源检查。However, [!UICONTROL DIL] always tries to request resources with CORS first. 它会在不支持 CORS 的早期浏览器中还原为 JSONP。If you need to force the browser to use CORS only, such as with sites that have high-security requirements, set `useCORSOnly:true`.

**代码示例**

<pre><code class="js">var dilinStation= DIL. create({
…
useCorsOnly：true})；</code>
</pre>

>[!IMPORTANT]
>
>* We recommend that you set `useCORSOnly: true` only when you&#39;re sure that your site visitors have browsers that support this feature.
>* When `useCORSOnly: true`, [!UICONTROL DIL] will not make ID calls from Internet Explorer version 9 or older.
>



>[!MORE_ LIKE_ This]
>
>* [DIL创建](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Experience Cloud ID服务：仅限用户](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [Experience Cloud ID 服务中的 CORS 支持](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## useImageRequest {#useimagerequest}

Changes the request type to image `<img>` from script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**函数签名：**`useImageRequest: function () {}`

>[!NOTE]
>
>您可以对此方法进行其他API调用。

**响应**

Returns an API object of the current [!UICONTROL DIL] instance.

**示例代码**

<pre><code>var datalb= DIL. create({
合作伙伴：“<i>parterName</i>”，
containernSite： <i>containernSID</i> })；

DataLibb. api. traits([<i>123，456，789</i>]). useImageRequest(). mit()；</code>
</pre>

