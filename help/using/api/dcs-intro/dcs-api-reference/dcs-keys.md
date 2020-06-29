---
description: 列表并描述可传递到数据收集服务器(DCS)的语法和支持的属性（或键值对）。 此信息有助于您格式化DCS请求并了解此系统返回的参数。
seo-description: 列表并描述可传递到数据收集服务器(DCS)的语法和支持的属性（或键值对）。 此信息有助于您格式化DCS请求并了解此系统返回的参数。
seo-title: DCS API 调用支持的属性
solution: Audience Manager
title: DCS API 调用支持的属性
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 5%

---


# 支持的调用 [!DNL DCS] 属 [!DNL API] 性 {#supported-attributes-for-dcs-api-calls}

列表并描述可传递给()的语法和支持的属性(或键值 [!UICONTROL Data Collection Servers] 对[!DNL DCS])。 此信息可以帮助您设置请求 [!DNL DCS] 的格式并了解此系统返回的参数。

## 属性前缀 {#attribute-prefixes}

该 [!DNL DCS] 类型依赖于键值对中添加到键的特定前缀，以对要传入的数据类型进行分类。

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 密钥前缀 </th> 
   <th colname="col2" class="entry"> 保留对象 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>客户定义的属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>HTTP头数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>客户定义的私有属性。 </p> <p> 当密钥具有前缀时，DCS会接受您自己的专用 <code> p_</code> 数据。 专用数据用于特征评估，但不会记录或存储在我们的系统中。 例如，假设您有一个特征定义为 <code> customers = p_age&lt;25</code> ，并且您在事件 <code> p_age=23</code> 调用中传入。 在满足这些条件的情况下，符合基于年龄的资格条件的用户有资格获得该特征，但在Audience Manager收到请求后，键值对 <span class="keyword"> 会</span> 被删除，并且不会记录。 </p> </td>
  </tr> 
 </tbody> 
</table>

## [!DNL d_] 属性 {#d-attributes}

除非您希望得到响应，否则所有这些都是可选的 [!DNL DCS]。 如果您希望 [!DNL DCS] 该用户返回响应，则 `d_rtbd=json` 为必需。

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
   <td colname="col2"> <p>用于标识对DCS API进行调用的 <span class="wintitle"> 调用</span> 者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>指定要使用DCS响应作为回调函数的 <span class="wintitle"> 函数参数</span> ，执行的JavaScript函数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>包含由Audience Manager分配的一对或多<code> DPID</code>对数据提供程序ID()和<code> DPUUID</code>数据提供程序用户 <span class="keyword"> ID()</span>。 如果使用多对s <code> DPID</code>和 <code> DPUUID</code>s，则每对用非打印字符分开 <code> %01</code>。 For example: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_cid</code> 替换 <code> d_dpid</code> 和 <code> d_dpuuid</code>（已弃用但仍受支持）。 请参阅 <a href="../../../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>在单个键值对中包含集成代码和关联的唯一用户ID。 </p> <p><code> d_cid_ic</code> 替换 <code> d_dpid</code> 和 <code> d_dpuuid</code>（已弃用但仍受支持）。 请参阅 <a href="../../../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>为遵守儿童保护法规，禁止使用第三方cookie。 此参数由AdobeAdobe Experience Platform身份服务动态设置，具体取决于配 <code> idSyncDisable3rdPartySyncing</code> 置。 请参 <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/coppa.html" format="https" scope="external"> 阅Adobe Experience Platform标识服务中的COPPA支持</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>可选。在客户请求时启用。 联系您的Adobe Audience Manager顾问或客户关怀。 </p> <p>指示应在响应内返回特征和区 <code> JSON</code> 段。 </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> 返回 <a href="../../../reference/ids-in-aam.md"> 区段的旧</a> “区段ID”。 </p> </li>
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
   <td colname="col2"> <p>已弃用。请参阅 <code> d_cid</code> 和 <code> d_cid_ic</code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>已弃用。请参阅 <code> d_cid</code> 和 <code> d_cid_ic</code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>在响应中返回URL目标 <code> JSON</code> 数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> 是保留属性，用于AdobeAnalytics与Audience Manager之间的集成。 </p> <p>我们建议不要创建使用保留属性的特征。 Adobe可随时更改保留属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>指示要 <code> JSON</code> 在响应中使用的版本。 通常，您应将其设置为 <code> d_jsonv=1</code>。 设置 <code> d_jsonv=0</code> 将禁用ID同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>指定Experience CloudID服务设置和使用 <span class="keyword"> 的Experience Cloud</span> ID。 有关ECID的详细信息，请参 <a href="https://docs.adobe.com/content/help/zh-Hans/id-service/using/intro/cookies.html" format="https" scope="external"> 阅Cookie和Experience Cloud身份服务</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>名称空格ID。 指示使用哪个JavaScript容器。 由DIL <span class="wintitle"> 用</span> 于ID同步。 </p> </td> 
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
   <td colname="col2"> <p>已弃用。<code> d_rs</code> 是保留属性，用于AdobeAnalytics与 <span class="keyword"> Audience Manager的旧</span> 版集 <span class="keyword"> 成</span>。 </p> <p>我们建议不要创建使用保留属性的特征。 Adobe可随时更改保留属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>如果希望DCS <code> JSON</code> 做出响应， <span class="wintitle"> 则必需</span>。 </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">如果忽略此项 <span class="wintitle"></span> ,DCS将返回头中的像素。 </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">如果包含此 <span class="wintitle"> 项</span> ,DCS <code> JSON</code> 将返回响应正文中的对象。 请参阅以下示例。 您的反应可能更复杂。 </li> 
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
   <td colname="col2"> <p><code> SID</code> 代表 <span class="term"> 得分ID</span>。 这是特征或区段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>传递数据源以进行特征评估。 只评估来自此数据源的特征。 </p> <p>例如，假设您有： </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>特征T1</b> : </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">特征规则： “<code> key1 == val1</code>” </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">数据源(<a href="../../../reference/ids-in-aam.md"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID集成代码： ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>特征T2</b> : </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">特征规则： “<code> key2 == val2</code>” </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">数据源(DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID集成代码： ic2 </li> 
     </ul> </p> <p>在示例调用中， <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>只返回特征T1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>其用途与上述参 <code> d_tdpid</code> 数相同。 但是，在这种情况下，数据源使用集成代码进行传递。 </p> <p>保留上述特征，请考虑示例调用： </p> <p>对 <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>于，只返回特征T2。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>唯一用户ID。 标识当此值不可从Cookie中使用时的访客。 </p> </td> 
  </tr>
 </tbody>
</table>