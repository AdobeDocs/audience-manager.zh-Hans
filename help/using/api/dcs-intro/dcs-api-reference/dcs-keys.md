---
description: 列出并描述可传入数据收集服务器(DCS)的语法和支持的属性(或密钥值对)。此信息可帮助您格式化DCS请求并了解此系统返回的参数。
seo-description: 列出并描述可传入数据收集服务器(DCS)的语法和支持的属性(或密钥值对)。此信息可帮助您格式化DCS请求并了解此系统返回的参数。
seo-title: DCS API调用的支持属性
solution: Audience Manager
title: DCS API调用的支持属性
uuid: 0b98ed11-314b-4500-afde-45a041112150
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Supported Attributes for DCS API Calls {#supported-attributes-for-dcs-api-calls}

Lists and describes the syntax and supported attributes (or key-value pairs) you can pass in to the [!UICONTROL Data Collection Servers] ([!UICONTROL DCS]). This information can help you format your [!UICONTROL DCS] requests and understand the parameters returned by this system.

## Attribute Prefixes {#attribute-prefixes}

The [!UICONTROL DCS] relies on specific prefixes added to the keys in key-value pairs to classify the type of data you're passing in.

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 密钥前缀 </th> 
   <th colname="col2" class="entry"> 保留为 </th> 
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
   <td colname="col2"> <p>客户定义的私有属性。 </p> <p> The DCS accepts your own, private data when the key has a <code> p_</code> prefix. 私有数据用于特征评估，但不会记录或存储在我们的系统中。For example, lets say you have a trait defined as <code> customers = p_age&lt;25</code> and you pass in <code> p_age=23</code> in an event call. Given these conditions, the user who meets the age-based qualification criteria qualifies for the trait, but the key-value pair is dropped after <span class="keyword"> Audience Manager</span> receives the request and is not logged. </p> </td>
  </tr> 
 </tbody> 
</table>

## d_ Attributes {#d-attributes}

All of these are optional, unless you want a response from the [!UICONTROL DCS]. If you want the [!UICONTROL DCS] to return a response, then `d_rtbd=json` is required.

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 属性 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_ caller</code> </p> </td> 
   <td colname="col2"> <p>Used to identify the caller who is making the call to the <span class="wintitle"> DCS</span> API. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>Specifies a JavaScript function you want to execute using the <span class="wintitle"> DCS</span> response as a function parameter of the callback function. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Contains one or more pairs of data provider IDs (<code> DPID</code>) and data provider user IDs (<code> DPUUID</code>) assigned by <span class="keyword"> Audience Manager</span>. If you use multiple pairs of <code> DPID</code>s and <code> DPUUID</code>s, separate each pair with the non-printing character <code> %01</code>. For example: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_ cid</code> 替换 <code> d_ dpid</code> 和 <code> d_ dpuuid</code>，它们已弃用但仍然支持。请参阅 <a href="../../../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_ cid_ ic</code> </p> </td> 
   <td colname="col2"> <p>包含一个集成代码和一个关联的唯一用户ID(在一个键值对中)。 </p> <p><code> d_ cid_ ic</code> 替换 <code> d_ dpid</code> 和 <code> d_ dpuuid</code>，它们已弃用但仍然支持。请参阅 <a href="../../../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ coppa</code> </p> </td> 
   <td colname="col2"> <p>禁用第三方Cookie的使用，以遵守儿童保护规定。This parameter is dynamically set by the Adobe Experience Cloud ID service and depends on the <code> idSyncDisable3rdPartySyncing</code> configuration. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_coppa.html" format="https" scope="external"> COPPA Support in the Experience Cloud ID Service</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_ cts=1</code> </p> <p><code> d_ cts=2</code> </p> </td> 
   <td colname="col2"> <p>可选。根据客户请求启用。联系您的Adobe Audience Manager顾问或客户关怀。 </p> <p>Indicates that traits and segments should be returned inside the <code> JSON</code> response. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_ cts=</code> 返回 <a href="../../../reference/ids-in-aam.md"> 区段的旧区段ID</a> 。 </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_ cts=</code> 返回区段ID。 </p> </li>
     </ul> </p> <p>示例响应可能如下所示： </p> <p>
     <code class="syntax javascript">{“feats”：[]，“uuid”：“0795526165808603505032705804272278”，“cs_ region”：7，“traits”：[420020，5421506]，“区段”：[984263、985264]、“tid”：“ss3otQPIPQ0=”} </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dpid</code> </p> </td> 
   <td colname="col2"> <p>已弃用。See <code> d_cid</code> and <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dpuid</code> </p> </td> 
   <td colname="col2"> <p>已弃用。See <code> d_cid</code> and <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dst=1</code> </p> </td> 
   <td colname="col2"> <p>Returns URL destination data in the <code> JSON</code> response. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_ dst_ filter</code> 是一个保留属性，用于Adobe Analytics和Audience Manager之间的集成。 </p> <p>我们建议不要创建使用保留属性的特征。Adobe可以随时更改保留属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ jsonv=1||0</code> </p> </td> 
   <td colname="col2"> <p>Indicates the <code> JSON</code> version to use in the response. Normally, you should set this to <code> d_jsonv=1</code>. Setting <code> d_jsonv=0</code> disables ID syncs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Specifies the Experience Cloud ID set and used by the <span class="keyword"> Experience Cloud</span> ID service. For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ nsid</code> </p> </td> 
   <td colname="col2"> <p>名称空间ID。指示使用哪个JavaScript容器。<span class="wintitle"> 由DIL</span> 用于id同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ tpm </code> </p> </td> 
   <td colname="col2"> <p>允许Audience Manager区分来自桌面请求的移动请求。支持的值包括： </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> Android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>已弃用。<code> d_ rs</code> 是一个保留属性，用于 <span class="keyword"> Adobe Analytics</span> 和 <span class="keyword"> Audience Manager之间的传统集成</span>。 </p> <p>我们建议不要创建使用保留属性的特征。Adobe可以随时更改保留属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ rtbd= json</code> </p> </td> 
   <td colname="col2"> <p>Required if you want a <code> JSON</code> response from the <span class="wintitle"> DCS</span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">If you omit this, the <span class="wintitle"> DCS</span> returns a pixel in the header. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">If you include this, the <span class="wintitle"> DCS</span> returns a <code> JSON</code> object in the body of the response. 请参阅下面的示例。您的响应可能更复杂。 </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">{“feats”：[]，“uuid”：“229201126906967679904394944949939990”，“ds_ greate”：7，“tid”：“ss3otQPIPQ0=”} </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> 代表 <span class="term"> 得分ID</span>。这是特征或区段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ tdpid</code> </p> </td> 
   <td colname="col2"> <p>通过数据源进行特征评估。只评估此数据源中的特征。 </p> <p>例如，您有： </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>特征T1</b> ： </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Trait rule: "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Data Source (<a href="../../../reference/ids-in-aam.md"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID集成代码：ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>特征T2</b> ： </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Trait rule: "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">数据源(DPID)：2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID集成代码：ic2 </li> 
     </ul> </p> <p>In a sample call, <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>, only trait T1 is returned. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ loadpid_ ic</code> </p> </td> 
   <td colname="col2"> <p>The purpose is identical to the <code> d_tdpid</code> parameter described above. 但是，在这种情况下，将使用集成代码传递数据源。 </p> <p>保留上述特征，考虑示例调用： </p> <p>For <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>, only trait T2 is returned. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ uuid</code> </p> </td> 
   <td colname="col2"> <p>唯一用户ID。当此值从cookie不可用时识别访客。 </p> </td> 
  </tr>
 </tbody>
</table>