---
description: 由按代码ID以数字顺序列出的数据收集服务器(DCS)生成的错误代码和消息。
seo-description: 由按代码ID以数字顺序列出的数据收集服务器(DCS)生成的错误代码和消息。
seo-title: DCS 错误代码、消息和示例
solution: Audience Manager
title: DCS 错误代码、消息和示例
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1545'
ht-degree: 4%

---


# DCS 错误代码、消息和示例 {#dcs-error-codes-messages-and-examples}

代码ID以数字顺 [!UICONTROL Data Collection Servers] 序列[!DNL DCS]出的()生成的错误代码和消息。

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
   <td colname="col3"> <p>这是一个全部捕获错误，它处理其他错误处理程序未覆盖的事件。 很难对此错误进行故障诊断。 它可能由各种未知的操作或事件引起。 </p> <p>如果收到此错误，请再次尝 <span class="wintitle"> 试DCS</span> 请求。 如果问题仍然存在，请与Adobe代表联系。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>找不到主机名的配置： <code><i>hostname</i></code> </p> </td> 
   <td colname="col3"> <p>我们的合作伙伴供应团队尚未设置请求中发送的主机名。 如果您看到此错误消息，请与Adobe代表联系。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>无效 <code> d_orgid</code> 值（找不到此组织ID的配置）: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>组织ID不正确。 </p> <p>请检查您的ID，然后重试请求。 如果您不知道或没有组织ID，请参阅组织和帐户链接中的“管理页 <a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html" format="https" scope="external"> 面”部分</a> ，以了解如何查找它。 </p> </td> 
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
   <td colname="col3"> <p>API调用未在请求中发送主机HTTP头。 </p> <p>在呼叫中添加主机头，然后重试。 注意，大多数浏览器和API客户端都是自动执行此操作的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>101 </p> </td> 
   <td colname="col2"> <p>传入的Experience CloudID无效 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>DCS <span class="wintitle"> 调用</span> 包含无效的 <span class="keyword"> Experience Cloud</span> ID。 </p> <p>检查标 <code> d_mid=</code> 题字符串中的键值对。 请确保您正在传递正确的 <span class="keyword"> Experience Cloud</span> ID，然后重试请求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>102 </p> </td> 
   <td colname="col2"> <p>请求中传递的aam id无效 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>DCS <span class="wintitle"> 调用</span> 包含无效的 <span class="keyword"> Audience Manager</span> ID。 </p> <p>检查标 <code> d_uuid=</code> 题字符串中的键值对。 请确保您正在传递正确的 <span class="keyword"> Audience Manager</span> ID，然后重试请求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>104 </p> </td> 
   <td colname="col2"> <p>所有客户ID无效 </p> </td> 
   <td colname="col3"> <p>您呼叫中的所有客户ID都无效。 请检查您的ID，然后重试。 </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p>109</p> </td> 
   <td colname="col2"> <p>合作 <code>HTTP referer</code> 伙伴不允许引用者 <code>Partner ID</code> </p> </td> 
   <td colname="col3"> <p>呼 <code>HTTP referer</code> 叫上的标头不允许用于呼叫上的合作伙伴ID。 检查标题 <code>HTTP referer</code> 是否正确。</p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>111 </p> </td> 
   <td colname="col2"> <p>收到 <span class="wintitle"> 的IMS令牌</span> 无效 </p> </td> 
   <td colname="col3"> <p>返回Audience Manager-Adobe Target集成。 当对DCS进行调用（包含无效的IMS令牌）时，将引发错误。 令牌可能格式不正确、已过期，或者用户可能未获得访问所需资源的授权。 </p> </td>
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
   <td colname="col2"> <p>遇选择退出到id标记 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>客户已选择不接收基于兴趣的广告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>阻止的Cookie </p> </td> 
   <td colname="col3"> <p>当用户的浏览器阻止第三方Cookie时返回。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>通过NAI遇到信任关 <a href="https://www.networkadvertising.org/" format="http" scope="external"> 系</a> </p> </td> 
   <td colname="col3"> <p>用户已通过NAI启动退出过程。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>合作伙伴阻止来自此国家／地区的请求 </p> </td> 
   <td colname="col3"> <p>DCS根据IP地址阻止 <span class="wintitle"> 来自</span> （合作伙伴有意限制流量）国家／地区的请求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>不允许来自此国家／地区的请求 </p> </td> 
   <td colname="col3"> <p>DCS根据IP地址阻止 <span class="wintitle"> 来自</span> 下列国家／地区的请求： </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">古巴(CU) </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">伊朗(IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">朝鲜(KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">苏丹语(SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">叙利亚(SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 用户档案检索错误代码 {#profile-retrieval-error-codes}

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
   <td colname="col2"> <p> 无法从ID的用户档案缓存读取特征： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当无法从内部用户档案读取用户存储时返回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> 无法从用户档案缓存读取客户ID的设备ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当无法检索 <a href="../../../reference/ids-in-aam.md"> 用户档案链接</a> 合并规则的设备ID时返回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>无法读取设备ID的相关客户： <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当无法从 <a href="../../../reference/ids-in-aam.md"> 内部存储检索与设备ID关联的</a> “上次验证”合并规则的客户ID(UUID)时返回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> 无法读取设备群集的id: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>无法为此设备ID返回来自同一设备图形群集的链接设备ID。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>无法执行迁移，因为主设备用户档案读取失败 </p> </td> 
   <td colname="col3"> <p>如果您收到此错误，我们的数据存储(PCS)可能会遇到可伸缩<span class="wintitle"> 性问题</span>。 如果问题仍然存在，请与Adobe代表联系。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>无法执行从迁移 <code><i>ID</i></code> 到迁 <code><i>ID</i></code>移，因为用户档案读取失败 <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>如果您收到此错误，我们的数据存储(PCS)可能会遇到可伸缩<span class="wintitle"> 性问题</span>。 如果问题仍然存在，请与Adobe代表联系。 </p> </td> 
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
   <td colname="col2"> <p>客户ID无效 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>客户ID无效（数据源值缺失、集成代码缺失、数据源格式无效、客户ID被阻止、客户ID空白、未授权访问不属于合作伙伴的数据源尝试）。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>超出客户ID的最大数量。 允许的最大 <code><i>maximum allowed</i></code>值。 找到 <code><i>maximum found</i></code>。</p> </td> 
   <td colname="col3"> <p>与跨设备数据源关联的客户ID数量超过每个请求允许的跨设备ID数量。 这些ID包括跨设备、移动或Cookie ID。 此限制当前设置为10。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>未经授权的客户ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当客户ID数据源不归当前组织ID所有时返回。 如果您不知道或没有组织ID，请参阅组织和帐户链接中的“查找 <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> 您的组织ID”部分</a> ，了解如何查找它。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>阻止的客户ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当客户ID被识别为恶意ID并已添加到密钥列表时返回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>阻止的数据源ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当数据源ID被识别为恶意ID并已添加到密钥列表时返回 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>已阻止声明的设备ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>设备ID已被标识为恶意ID，并已添加到密钥列表。在短时间内收到包含此设备ID的极 <span class="wintitle"> 量</span> DCS请求时，可能会发生这种情况。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>阻止用户档案操作 <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>已阻止读／写操作，因为ID已被标识为恶意，并已添加到密文列表。请参阅错误代码306。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>客户ID <code><i>ID</i></code> 已被丢弃，因为它超过了每个请求声明的客户ID的限制 </p> </td> 
   <td colname="col3"> <p>与错误301相关。 此错误指定因超出限制而放弃的客户ID。 </p> <p>例如，如果DCS调用中声明了12个 <span class="wintitle"> 客户</span> ID，其中两个将被丢弃。 为了传递被丢弃的客户ID，此错误将在响应中显示两次（对于每个被丢弃的客户ID显示一次）。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>客户ID已被放弃，因为它超出了给定命名空间的限制。 命名空间ID <code><i>ID</i></code>是，客户ID <code><i>ID</i></code>是。 </p> </td> 
   <td colname="col3"> <p>如果在DCS调用中为同一命名空间()声明的客户ID超过3个，<code> DPID</code>则返回 <span class="wintitle"> 此错误</span> 代码。 </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>在此示例 <span class="wintitle"> DCS请求</span> 中，有4个id声明用于同一命名空间（集成代码为1）。 将丢弃一个ID，并返回错误310。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>请求包含无效参数 </p> </td> 
   <td colname="col3"> <p>当至 <span class="wintitle"> 少一个URL参数未正确编码时</span> ,DCS将返回此错误代码。 在这种情况下， <span class="wintitle"> DCS</span> 忽略整个请求。 </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>在上面的示例请求中，序列 <code> %</code> 的编码不正确。 因此，DCS <span class="wintitle"> 将忽略</span> 它。 </p> <p>正确编码的范例应如下： </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>请求包含无效的全局设备ID </p> </td> 
   <td colname="col3"> <p>当请 <span class="wintitle">求包含</span> 无效的全局设备ID时，DCS将返回此错误代码。 DCS忽略无效ID，并引发312错误和无效ID的特定错误。 有关正确 <a href="../../../features/global-data-sources.md" format="dita" scope="local">的设备广</a> 告ID格式和相应的全局数据源的详细信息，请参 <a href="../../../reference/ids-in-aam.md" format="dita" scope="local"></a> 阅Audience Manager中的全局数据源和ID索引。</p>
   <p>错误调用的示例： <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>说明： IDFA <span class="keyword">(DPID 20915)必</span> 须是大写ID。 请求中提供的ID为小写。</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>GCL中不存在CMP ID</p> </td> 
   <td colname="col3"> <p>当 <code>gdpr=1</code> 且IAB TC字符串由评估时Audience Manager的全局CMP列表的缓存版本中不存在的CMP ID生成时，IAB TCF的Audience Manager插件将丢弃IAB TC字符串并照常处理请求。 IAB TCF v2.0 ${GDPR}宏设置为0，而${GDPR_CONNENCE_XXX}宏为空。</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>CMP ID在GCL中标记为已删除</p> </td> 
   <td colname="col3"> <p>当 <code>gdpr=1</code> IAB TC字符串由在我们的全局CMP列表的缓存版本中标记为已删除的CMP生成时，IAB TCF的Audience Manager插件会丢弃TC字符串并照常处理请求，如果评估时间超过从全局CMP列表删除时间。 IAB TCF v2.0 ${GDPR}宏设置为0，而${GDPR_CONNENCE_XXX}宏为空。</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>“同意”字符串表示未同意</p> </td> 
   <td colname="col3"> <p>如果未征得同意，IAB TCF的Audience Manager插件会选择用户退出进一步的数据收集，或者如果未检测到合作伙伴上下文，则完全停止调用。</p>
   </td>
  </tr>

</tbody>
</table>

## 示例错误代码消息 {#sample-error-codes}

返 [!DNL DCS] 回对象或HTTP响 [!DNL JSON] 应字符串中X头中的错误代码和消息。

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

由X-头捕获的错误代码会像这样显示在URL字符串中 `X-Error: 101,102`。

[竞赛条件和错误处理](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)