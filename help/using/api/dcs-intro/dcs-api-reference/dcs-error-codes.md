---
description: 由按代码ID以数字顺序列出的数据收集服务器(DCS)生成的错误代码和消息。
seo-description: 由按代码ID以数字顺序列出的数据收集服务器(DCS)生成的错误代码和消息。
seo-title: DCS 错误代码、消息和示例
solution: Audience Manager
title: DCS 错误代码、消息和示例
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
translation-type: tm+mt
source-git-commit: 8478a28cd1b18d878d6938d77ee4f975deb524ef

---


# DCS 错误代码、消息和示例 {#dcs-error-codes-messages-and-examples}

由代码ID以数字顺序列 [!UICONTROL Data Collection Servers] 出的([!UICONTROL DCS])生成的错误代码和消息。

In the tables below, *italics* represents a variable placeholder.

## 系统错误代码 {#system-error-codes}

<table id="table_43F4321BEA6A4D1BBDFE2E9FB4402914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代码ID </th> 
   <th colname="col2" class="entry"> 错误消息 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>0 </p> </td> 
   <td colname="col2"> <p>未指定错误 </p> </td> 
   <td colname="col3"> <p>这是一个全部捕获错误，它处理其他错误处理程序未覆盖的事件。 很难对此错误进行故障诊断。 它可能由各种未知的操作或事件引起。 </p> <p>如果收到此错误，请再次尝试 <span class="wintitle"> DCS</span> 请求。 如果问题仍然存在，请与Adobe代表联系。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>找不到主机名的配置： <code><i>hostname</i></code> </p> </td> 
   <td colname="col3"> <p>我们的合作伙伴供应团队尚未设置请求中发送的主机名。 如果您看到此错误消息，请与Adobe代表联系。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>无效 <code> d_orgid</code> 的值（找不到此组织ID的配置）: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>组织ID不正确。 </p> <p>检查您的ID并再次尝试请求。 如果您不知道或没有组织ID，请参阅 <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> Experience Cloud Administration中的“管理页面”部分</a> ，以了解如何查找它。 </p> </td> 
  </tr>
 </tbody>
</table>

## 集成错误代码 {#integration-error-codes}

<table id="table_EFF06FB3D045459BA7802872AF22DF79"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代码ID </th> 
   <th colname="col2" class="entry"> 消息 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>100 </p> </td> 
   <td colname="col2"> <p>无法检索请求的主机名 </p> </td> 
   <td colname="col3"> <p>API调用未在请求中发送主机HTTP头。 </p> <p>将主机头添加到呼叫中，然后重试。 注意，大多数浏览器和API客户端都是自动执行此操作的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>101 </p> </td> 
   <td colname="col2"> <p>传入的Experience Cloud ID无效 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>DCS调 <span class="wintitle"> 用包含无</span> 效的Experience Cloud <span class="keyword"></span> ID。 </p> <p>检查 <code> d_mid=</code> 标题字符串中的键值对。 确保您正在传递正确的 <span class="keyword"> Experience Cloud</span> ID，然后重试请求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>102 </p> </td> 
   <td colname="col2"> <p>请求中传递的aam ID无效 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>DCS调 <span class="wintitle"> 用包含无</span> 效的Audience Manager <span class="keyword"></span> ID。 </p> <p>检查 <code> d_uuid=</code> 标题字符串中的键值对。 确保您传入了正确的 <span class="keyword"> Audience Manager</span> ID，然后再次尝试请求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>104 </p> </td> 
   <td colname="col2"> <p>所有客户ID无效 </p> </td> 
   <td colname="col3"> <p>您的电话联系中的所有客户ID都无效。 检查您的ID，然后重试。 </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p>109</p> </td> 
   <td colname="col2"> <p>合作 <code>HTTP referer</code> 伙伴不允许引用 <code>Partner ID</code> </p> </td> 
   <td colname="col3"> <p>调用中的合作伙伴ID不允许调用上的[!DNL HTTP Referer]头。 检查[!DNL HTTP referer]头是否正确。</p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>111 </p> </td> 
   <td colname="col2"> <p>收到 <span class="wintitle"> 的IMS令牌</span> 无效 </p> </td> 
   <td colname="col3"> <p>返回Audience Manager - Adobe Target集成。 当对包含无效IMS令牌的DCS进行调用时，将引发错误。 令牌可能格式错误、已过期，或者用户可能未获得访问所需资源的授权。 </p> </td>
  </tr>
 </tbody>
</table>

## 退出错误代码 {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代码ID </th> 
   <th colname="col2" class="entry"> 消息 </th> 
   <th colname="col3" class="entry"> 描述 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>遇到ID的退出标记 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>客户已选择不接收基于兴趣的广告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>阻止的Cookie </p> </td> 
   <td colname="col3"> <p>当用户的浏览器阻止第三方Cookie时返回。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>通过 <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI遇到信任关系</a> </p> </td> 
   <td colname="col3"> <p>用户已通过NAI启动退出过程。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>合作伙伴阻止来自此国家／地区的请求 </p> </td> 
   <td colname="col3"> <p>DCS会根据IP地址阻止来 <span class="wintitle"></span> 自合作伙伴有意限制流量的国家的请求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>不允许来自此国家／地区的请求 </p> </td> 
   <td colname="col3"> <p>DCS会根据IP地址阻止来 <span class="wintitle"> 自</span> : </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">古巴(CU) </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">伊朗(IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">朝鲜(KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">苏丹(SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">叙利亚(SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 配置文件检索错误代码 {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代码ID </th> 
   <th colname="col2" class="entry"> 消息 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> 无法从ID的配置文件缓存读取特征： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当无法从内部存储读取用户配置文件时返回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> 无法从客户ID的配置文件缓存中读取设备ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当无法检索 <a href="../../../reference/ids-in-aam.md"> 配置文件链接</a> 合并规则的设备ID时返回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>无法读取设备ID的相关客户： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当无法从我 <a href="../../../reference/ids-in-aam.md"> 们的内部存储中为“上次验证”合并规则检索与设备ID关联的客户ID(UUID)</a> 时返回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> 无法读取设备群集的id: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>无法为此设备ID返回来自同一设备图形群集的链接设备ID。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>无法执行迁移，因为主设备的配置文件读取失败 </p> </td> 
   <td colname="col3"> <p>如果您收到此错误，我们可能会遇到数据存储(<span class="wintitle"> PCS</span>)的可伸缩性问题。 如果问题仍然存在，请与Adobe代表联系。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>无法执行从迁移到迁 <code><i>ID</i></code> 移， <code><i>ID</i></code>因为 <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>如果您收到此错误，我们可能会遇到数据存储(<span class="wintitle"> PCS</span>)的可伸缩性问题。 如果问题仍然存在，请与Adobe代表联系。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 集成警告代码 {#integration-warning-codes}

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代码ID </th> 
   <th colname="col2" class="entry"> 消息 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>300 </p> </td> 
   <td colname="col2"> <p>无效的客户ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>客户ID无效（数据源值缺失、集成代码缺失、数据源格式无效、客户ID被阻止、客户ID空白、未授权访问不属于合作伙伴的数据源）。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>超出客户ID的最大数量。 允许的最大 <code><i>maximum allowed</i></code>值。 找到 <code><i>maximum found</i></code>。</p> </td> 
   <td colname="col3"> <p>与跨设备数据源关联的客户ID数量超过每个请求允许的跨设备ID数量。 这些ID包括跨设备、移动或Cookie ID。 该限制当前设置为10。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>未授权的客户ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当客户ID数据源不归当前组织ID所有时返回。 如果您不知道或没有组织ID，请参阅组织和帐户链接中的“查找组织ID”部分，了解有关如何查找组织ID的信息 <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"></a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>阻止的客户ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当客户ID被识别为恶意ID并被列入黑名单时返回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>阻止的数据源ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当数据源ID被标识为恶意并被列入黑名单时返回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>已阻止声明的设备ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>设备ID已被识别为恶意ID并已列入黑名单。 如果我们在很短的时间内收到包含此设备ID的 <span class="wintitle"> DCS</span> 请求，就会发生这种情况。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>阻止的配置文件操作 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>由于ID已被识别为恶意ID并且已列入黑名单，因此读／写操作已被阻止。 请参阅错误代码306。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>客户ID <code><i>ID</i></code> 被丢弃，因为它超出了每个请求声明的客户ID的限制 </p> </td> 
   <td colname="col3"> <p>与错误301相关。 此错误指定了因超出限制而放弃的客户ID。 </p> <p>例如，如果在 <span class="wintitle"> DCS调用中声明了12个客户ID</span> ，其中两个将被丢弃。 为了传递被丢弃的客户ID，此错误将在响应中显示两次（对于每个被丢弃的客户ID显示一次）。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>客户ID已被放弃，因为它超出了给定命名空间的限制。 命名空间id <code><i>ID</i></code>为，客户id为 <code><i>ID</i></code>。 </p> </td> 
   <td colname="col3"> <p>如果在DCS调用中为同一命名空间(<code> DPID</code>)声明的客户ID超过3个，则返回 <span class="wintitle"> 此错误代码</span> 。 </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>在此示例 <span class="wintitle"> DCS请求中</span> ，有4个ID声明用于同一命名空间（集成代码为1）。 其中一个ID被丢弃，并返回错误310。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>请求包含无效参数 </p> </td> 
   <td colname="col3"> <p>当至少一个 <span class="wintitle"> URL参数未正确编码时</span> ,DCS将返回此错误代码。 在这种情况下， <span class="wintitle"> DCS</span> 会忽略整个请求。 </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>在上述示例请求中，序列 <code> %</code> 的编码不正确。 因此， <span class="wintitle"> DCS</span> 将忽略它。 </p> <p>正确编码的范例应如下： </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>请求包含无效的全局设备ID </p> </td> 
   <td colname="col3"> <p>当请 <span class="wintitle">求包含无效的全局设备ID时</span> ,DCS将返回此错误代码。 DCS会忽略无效ID，并引发312错误以及无效ID的特定错误。 有关正确 <a href="../../../features/global-data-sources.md" format="dita" scope="local">的设备广告ID格式和相</a> 应的全局数据源的详细信息，请参阅Audience Manager中的全局数据源和ID索引 <a href="../../../reference/ids-in-aam.md" format="dita" scope="local"></a> 。</p>
   <p>错误调用的示例： <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>说明： <span class="keyword">IDFA(DPID 20915)</span> 必须是大写ID。 请求中提供的ID为小写。</p>
   </td>
  </tr>

</tbody>
</table>

## 示例错误代码消息 {#sample-error-codes}

返 [!UICONTROL DCS] 回对象中或HTTP响 [!DNL JSON] 应字符串中的X-头中的错误代码和消息。

### 示例DCS错误代码和消息

```
{ 
   "errors":[ 
      { 
         "code":101,
         "msg":"Invalid Experience Cloud id passed in"
      },
      { 
         "code":102,
         "msg":"Invalid aam id passed in request"
      }
   ]
}
```

### X-Error

由X-标题捕获的错误代码会像这样显示在URL字符串中 `X-Error: 101,102`。

[竞争条件和错误处理](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)