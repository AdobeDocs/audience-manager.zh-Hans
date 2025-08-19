---
description: 列出并描述了可传递到数据收集服务器(DCS)的语法和支持的属性（或键值对）。 此信息可帮助您格式化DCS请求并了解此系统返回的参数。
seo-description: Lists and describes the syntax and supported attributes (or key-value pairs) you can pass in to the Data Collection Servers (DCS). This information can help you format your DCS requests and understand the parameters returned by this system.
seo-title: Supported Attributes for DCS API Calls
solution: Audience Manager
title: DCS API调用支持的属性
keywords: d_caller， d_cb， d_cid， d_cid_ic， d_coppa， d_cts=1， d_cts=2， d_tdpid， d_dst=1， d_dst_filter， d_mid， d_ptfm， d_nsid， d_rs， d_rtbd=json， d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
feature: DCS
exl-id: 1bdd7dcd-9411-4b0a-a236-059eb5faf00d
source-git-commit: e10211057a87622340fd2c61737c7c7a45c0e99c
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 2%

---

# [!DNL DCS] [!DNL API]调用支持的属性 {#supported-attributes-for-dcs-api-calls}

列出并说明可传递到[!UICONTROL Data Collection Servers] ([!DNL DCS])的语法和支持的属性（或键值对）。 此信息可帮助您格式化[!DNL DCS]请求并了解此系统返回的参数。

## 属性前缀 {#attribute-prefixes}

[!DNL DCS]依赖于添加到键值对中的键的特定前缀来分类您要传入的数据类型。

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 密钥前缀 </th> 
   <th colname="col2" class="entry"> 保留用于 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>客户定义的属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">个Audience Manager</span>属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>HTTP标头数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>私有、客户定义的属性。 </p> <p> 当密钥具有<code> p_</code>前缀时，DCS接受您自己的私有数据。 私有数据用于特征评估，但不会记录或存储在我们的系统中。 例如，假设您有一个定义为<code> customers = p_age&lt;25</code>的特征，并且在事件调用中传入<code> p_age=23</code>。 根据这些条件，符合基于年龄的资格条件的用户符合特征资格，但在<span class="keyword"> Audience Manager</span>收到请求且未记录后，键值对将被删除。 </p> </td>
  </tr> 
 </tbody> 
</table>

## [!DNL d_]属性 {#d-attributes}

除非您需要[!DNL DCS]的响应，否则所有这些都是可选的。 如果您希望[!DNL DCS]返回响应，则需要`d_rtbd=json`。

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 属性 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_caller</code> </p> </td> 
   <td colname="col2"> <p>用于标识对<span class="wintitle"> DCS</span> API进行调用的调用方。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>指定要使用<span class="wintitle"> DCS</span>响应作为回调函数的函数参数执行的JavaScript函数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>包含由<code> DPID</code> Audience Manager<code> DPUUID</code>分配的一个或多个数据提供程序ID (<span class="keyword">)和数据提供程序用户ID (</span>)对。 如果您使用多对<code> DPID</code>和<code> DPUUID</code>，请用非打印字符<code> %01</code>分隔每对。 例如： <code><i>DPID</i>%01<i>DPUUUID</i></code>。 </p> <p><code> d_cid</code> 替换<code> d_dpid</code>和<code> d_dpuuid</code>，它们已被弃用，但仍受支持。 请参阅<a href="../../../reference/cid.md"> CID取代DPID和DPUUID</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>在单个键值对中包含集成代码和关联的唯一用户ID。 </p> <p><code> d_cid_ic</code> 替换<code> d_dpid</code>和<code> d_dpuuid</code>，它们已被弃用，但仍受支持。 请参阅<a href="../../../reference/cid.md"> CID取代DPID和DPUUID</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>为了遵守儿童保护法规，禁止使用第三方Cookie。 此参数由Adobe Adobe Experience Platform Identity Service动态设置，依赖于<code> idSyncDisable3rdPartySyncing</code>配置。 请参阅Adobe Experience Platform Identity服务<a href="https://experienceleague.adobe.com/docs/id-service/using/reference/coppa.html" format="https" scope="external">中的</a> COPPA支持。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>可选。已根据客户请求启用。 请联系您的Adobe Audience Manager顾问或客户关怀团队。 </p> <p>指示应在<code> JSON</code>响应中返回特征和区段。 </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> 返回区段的<a href="../../../reference/ids-in-aam.md">旧区段ID</a>。 </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> 返回区段的区段ID。 </p> </li>
     </ul> </p> <p>示例响应可能如下所示： </p> <p>
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"07955261652886032950143702505894272138",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"traits":&nbsp;[420020,&nbsp;5421506],
      &nbsp;&nbsp;&nbsp;&nbsp;"segments":&nbsp;[984263,&nbsp;985264],
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpid</code> </p> </td> 
   <td colname="col2"> <p>已弃用。查看<code> d_cid</code>和<code> d_cid_ic</code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>已弃用。查看<code> d_cid</code>和<code> d_cid_ic</code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>在<code> JSON</code>响应中返回URL目标数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> 是一个保留属性，用于Adobe Analytics和Audience Manager之间的集成。 </p> <p>我们建议不要创建使用保留属性的特征。 Adobe可以随时更改保留属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>指示要在响应中使用的<code> JSON</code>版本。 通常情况下，您应该将此项设置为<code> d_jsonv=1</code>。 设置<code> d_jsonv=0</code>可禁用ID同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>指定由<span class="keyword"> Experience Cloud</span> ID服务设置和使用的Experience Cloud ID。 有关ECID的详细信息，请参阅<a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Experience Cloud Identity服务</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>命名空间ID。 指示使用的JavaScript容器。 由<span class="wintitle"> DIL</span>用于进行ID同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>允许Audience Manager区分移动请求和桌面请求。 支持的值包括： </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>已弃用。<code> d_rs</code>是一个保留属性，用于<span class="keyword"> Adobe Analytics</span>和<span class="keyword"> Audience Manager</span>之间的旧版集成。 </p> <p>我们建议不要创建使用保留属性的特征。 Adobe可以随时更改保留属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>如果您需要来自<code> JSON</code> DCS<span class="wintitle">的</span>响应，则此为必填字段。 </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">如果忽略此项，则<span class="wintitle"> DCS</span>在标题中返回一个像素。 </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">如果包括此项，则<span class="wintitle"> DCS</span>在响应正文中返回<code> JSON</code>对象。 请参阅以下示例。 您的响应可能比较复杂。 </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"22920112968019678612904394744954398990",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> 表示<span class="term">得分ID</span>。 这是特征或区段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>传递用于特征评估的数据源。 仅评估来自此数据源的特征。 </p> <p>例如，假设您拥有： </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>特征T1</b>具有以下特征： </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">特征规则： "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">数据Source (<a href="../../../reference/ids-in-aam.md"> DPID</a>)： 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID集成代码：ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>特征T2</b>，带： </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">特征规则： "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">数据Source (DPID)：2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID集成代码：ic2 </li> 
     </ul> </p> <p>在示例调用<code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>中，只返回特征T1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>用途与上面描述的<code> d_tdpid</code>参数相同。 但是，在这种情况下，将使用集成代码传递数据源。 </p> <p>保持上述特征，请考虑示例调用： </p> <p>对于<code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>，只返回特征T2。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>独特用户ID。 在Cookie中无法提供此值时标识访客。 </p> </td> 
  </tr>
 </tbody>
</table>

## h_属性

这些标头包含诸如HTTP调用中的数据请求和响应之类的信息。

| 属性 | 描述 |
| --- | --- | 
| `h_host` | 设置为客户端的特定数据收集主机名。 它显示为`host name .demdex.net`。 请参阅[了解 Demdex 域调用](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=en)。 |
| `h_user-agent` | 设置为`User-Agent`标头值。 |
| `h_accept-language` | 设置为`Accept-Language`标头值。 |
| `h_referer` | 设置为`Referer`标头值。 |
| `h_referrer` | 设置为`Referrer`标头值。 |
| `h_date` | 设置为`Date`标头值。 |