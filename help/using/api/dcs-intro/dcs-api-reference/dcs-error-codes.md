---
description: 数据收集服务器(DCS)生成的错误代码和消息按代码ID的数字顺序列出。
seo-description: 数据收集服务器(DCS)生成的错误代码和消息按代码ID的数字顺序列出。
seo-title: DCS 错误代码、消息和示例
solution: Audience Manager
title: DCS 错误代码、消息和示例
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1545'
ht-degree: 4%

---

# DCS 错误代码、消息和示例 {#dcs-error-codes-messages-and-examples}

由[!UICONTROL Data Collection Servers]([!DNL DCS])生成的错误代码和消息按代码ID的数字顺序列出。

在下表中，*斜体*&#x200B;表示变量占位符。

## 系统错误代码 {#system-error-codes}

| 错误代码 | 错误消息 | 描述 |
|---|---|---|
| 0 | 未指定错误 | 这是一个全包错误，用于处理其他错误处理程序未涵盖的事件。 对此错误进行故障诊断很困难。 它可能由各种未知操作或事件引起。 如果收到此错误，请重试[!DNL DCS]请求。 如果问题仍然存在，请联系您的[!DNL Adobe]代表。 |
| 1 | 找不到主机名的配置：`hostname` | 我们的合作伙伴配置团队尚未设置在请求中发送的主机名。 如果看到此错误消息，请联系您的[!DNL Adobe]代表。 |
| 2 | 无效的`d_orgid`值（找不到此组织ID的配置）：`ID` | 组织ID不正确。 请检查您的ID，然后重试请求。 如果您不知道或没有组织ID，请参阅“管理页面”部分[组织和帐户关联](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html)以了解有关如何查找组织ID的信息。 |
| 10 | 无法评估特征 | 请求中的特征要么经过部分评估，要么根本未进行评估。 如果问题仍然存在，请联系您的[!DNL Adobe]代表。 |

## 集成错误代码 {#integration-error-codes}

| 错误代码 | 错误消息 | 描述 |
|---|---|---|
| 100 | 无法检索请求的主机名 | [!DNL API]调用未在请求中发送主机[!DNL HTTP]标头。 将主机标头添加到调用中，然后重试。 大多数浏览器和[!DNL API]客户端都会自动执行此操作。 |
| 101 | 在`ID`中传递的[!DNL Experience Cloud] ID无效 | [!DNL DCS]调用包含无效的[!DNL Experience Cloud] ID。 检查标题字符串中的`d_mid=`键值对。 请确保传递了正确的[!DNL Experience Cloud] ID，然后重试请求。 |
| 102 | 请求`ID`中传递的[!DNL AAM ID]无效 | [!DNL DCS]调用包含无效的[!DNL Audience Manager] ID。 检查标题字符串中的`d_uuid=`键值对。 请确保传递了正确的[!DNL Audience Manager] ID，然后重试请求。 |
| 104 | 所有客户ID都无效 | 您调用中的所有客户ID都无效。 请检查您的ID，然后重试。 |
| 109 | 合作伙伴`Partner ID`不允许引用`HTTP referer` | 调用中的合作伙伴ID不允许使用`HTTP referer`标头。 检查`HTTP referer`标头是否正确。 |
| 111 | 收到无效的`IMS`令牌 | 为[!DNL Audience Manager] - [!DNL Adobe Target]集成返回。 对[!DNL DCS]（包含无效的[!DNL IMS]令牌）进行调用时，会引发错误。 令牌可能格式错误、过期，或者用户可能无权访问所需资源。 |

## 选择禁用错误代码 {#opt-out-error-codes}

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
   <td colname="col2"> <p>遇到ID <code><i>ID</i></code>的选择退出标记 </p> </td> 
   <td colname="col3"> <p>客户已选择退出接收基于兴趣的广告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>阻止的Cookie </p> </td> 
   <td colname="col3"> <p>在用户的浏览器阻止第三方Cookie时返回。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>通过<a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a>遇到信任关系 </p> </td> 
   <td colname="col3"> <p>用户已通过NAI启动了选择退出流程。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>合作伙伴将阻止来自此国家/地区的请求 </p> </td> 
   <td colname="col3"> <p>根据IP地址，<span class="wintitle"> DCS</span>会阻止来自合作伙伴有意限制流量的国家/地区的请求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>不允许来自此国家/地区的请求 </p> </td> 
   <td colname="col3"> <p><span class="wintitle"> DCS</span>会根据IP地址阻止来自以下国家/地区的请求： </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">古巴（古巴） </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">伊朗(IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">朝鲜(KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">苏丹（南达科他） </li> 
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
   <td colname="col2"> <p> 无法从配置文件缓存读取ID的特征：<code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>在无法从内部存储中读取用户配置文件时返回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> 无法从配置文件缓存中读取客户ID的设备ID:<code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当无法为配置文件链接合并规则检索<a href="../../../reference/ids-in-aam.md">设备ID</a>时返回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>无法读取设备ID的相关客户：<code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当无法从内部存储中为“上次身份验证”合并规则检索与设备ID关联的<a href="../../../reference/ids-in-aam.md">客户ID(UUID)</a>时返回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> 无法读取设备群集的ID:<code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>无法为此设备ID返回来自同一设备图群集的链接设备ID。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>无法执行迁移，因为主设备的配置文件读取失败 </p> </td> 
   <td colname="col3"> <p>如果您收到此错误，我们的数据存储(<span class="wintitle"> PCS</span>)可能会遇到可扩展性问题。 如果问题仍然存在，请与Adobe代表联系。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>无法从<code><i>ID</i></code>迁移到<code><i>ID</i></code>，因为<code><i>ID</i></code>的配置文件读取失败 </p> </td>
   <td colname="col3"> <p>如果您收到此错误，我们的数据存储(<span class="wintitle"> PCS</span>)可能会遇到可扩展性问题。 如果问题仍然存在，请与Adobe代表联系。 </p> </td> 
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
   <td colname="col3"> <p>客户ID无效（缺少数据源值、缺少集成代码、数据源格式无效、客户ID被阻止、客户ID空白、未授权访问不属于合作伙伴的数据源尝试）。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>超出的客户ID最大数量。 允许的最大值为<code><i>maximum allowed</i></code>。 找到的是<code><i>maximum found</i></code>。</p> </td> 
   <td colname="col3"> <p>与跨设备数据源关联的客户ID数量超过了每个请求允许的跨设备ID数量。 这些ID包括跨设备ID、移动设备ID或Cookie ID。 此限制当前设置为10。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>未授权的客户ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>当客户ID数据源不归当前组织ID所有时返回。 如果您不知道或没有组织ID，请参阅<a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external">组织和帐户关联</a>中的“查找组织ID”部分，以了解有关如何查找组织ID的信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>阻止的客户ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>在客户ID被识别为恶意ID并添加到时返阻止列表回。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>阻止的数据源ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>在数据源ID被识别为恶意ID并添加到时返阻止列表回 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>已阻止声明的设备ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>设备ID已被识别为恶意ID，并且已添加到中。如果我们在短时间内收到包含此设备ID的阻止列表超常数量的<span class="wintitle"> DCS</span>请求，则可能会发生这种情况。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p><code><i>ID</i></code>的配置文件操作被阻止 </p> </td> 
   <td colname="col3"> <p>已阻止读/写操作，因为ID已被识别为恶意，并且已添加到中。请参阻止列表阅错误代码306。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>客户ID <code><i>ID</i></code>已被丢弃，因为它超过了每个请求声明的客户ID的限制 </p> </td> 
   <td colname="col3"> <p>与错误301相关。 此错误会指定由于超出限制而丢弃的客户ID。 </p> <p>例如，如果在<span class="wintitle"> DCS</span>调用中声明了12个客户ID，则将丢弃其中2个。 为了中继哪些客户ID被丢弃，此错误将在响应中显示两次（对于每个被丢弃的客户ID显示一次）。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>客户ID已被丢弃，因为它超出了给定命名空间的限制。 命名空间id为<code><i>ID</i></code>，客户id为<code><i>ID</i></code>。 </p> </td> 
   <td colname="col3"> <p>如果在<span class="wintitle"> DCS</span>调用中为相同命名空间(<code> DPID</code>)声明了3个以上的客户ID，则返回此错误代码。 </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>在此示例<span class="wintitle"> DCS</span>请求中，为同一命名空间声明了4个ID（集成代码为1）。 丢弃一个ID，并返回错误310。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>请求包含无效参数 </p> </td> 
   <td colname="col3"> <p>当至少有一个URL参数未正确编码时，<span class="wintitle"> DCS</span>会返回此错误代码。 在这种情况下，<span class="wintitle"> DCS</span>会忽略整个请求。 </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>在上述示例请求中，<code> %</code>序列被错误编码。 因此， <span class="wintitle"> DCS</span>将忽略它。 </p> <p>正确编码的示例应如下所示： </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>请求包含无效的全局设备ID </p> </td> 
   <td colname="col3"> <p>当请求包含无效的全局设备ID时， <span class="wintitle">DCS</span>会返回此错误代码。 DCS会忽略无效ID，并引发312错误以及无效ID的特定错误。 请参阅<a href="../../../features/global-data-sources.md" format="dita" scope="local">全局数据源</a>和<a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Audience Manager</a>中的ID索引，以获取有关正确的设备广告ID格式和相应的全局数据源的详细信息。</p>
   <p>错误调用的示例： <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>解释：<span class="keyword">IDFA(DPID 20915)</span>必须是大写的ID。 请求中提供的ID是小写的。</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>GCL中不存在CMP ID</p> </td> 
   <td colname="col3"> <p>当<code>gdpr=1</code>和IAB TC字符串是由评估时Audience Manager的全局CMP列表缓存版本中不存在的CMP ID生成时，适用于IAB TCF的Audience Manager插件会丢弃IAB TC字符串，并照常处理请求。 IAB TCF v2.0 ${GDPR}宏设置为0，而${GDPR_CONSENT_XXX}宏为空。</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>在GCL中，CMP ID被标记为已删除</p> </td> 
   <td colname="col3"> <p>当<code>gdpr=1</code>和IAB TC字符串由在全局CMP列表的缓存版本中标记为已删除的CMP生成时，如果评估时间超过了从全局CMP列表中删除时间，则适用于IAB TCF的Audience Manager插件会丢弃TC字符串并照常处理请求。 IAB TCF v2.0 ${GDPR}宏设置为0，而${GDPR_CONSENT_XXX}宏为空。</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>同意字符串表示未同意</p> </td> 
   <td colname="col3"> <p>如果未提供同意，适用于IAB TCF的Audience Manager插件会选择用户退出进一步的数据收集，或者在未检测到合作伙伴上下文时完全停止调用。</p>
   </td>
  </tr>

</tbody>
</table>

## 示例错误代码消息 {#sample-error-codes}

[!DNL DCS]在[!DNL JSON]对象或HTTP响应字符串的X — 标头中返回错误代码和消息。

### DCS错误代码和消息示例

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

### X错误

X — 标头捕获的错误代码会像`X-Error: 101,102`这样显示在URL字符串中。

[争用条件和错误处理](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
