---
description: Audience Manager 和 Experience Cloud ID 服务可调用 demdex.net 域中的数据并从该域接收数据。这看起来好像Adobe正在处理一个不同寻常的第三方域，但情况并非如此。 本节介绍demdex.net调用中的元素。
seo-description: Audience Manager 和 Experience Cloud ID 服务可调用 demdex.net 域中的数据并从该域接收数据。这看起来好像Adobe正在处理一个不同寻常的第三方域，但情况并非如此。 本节介绍demdex.net调用中的元素。
seo-title: 了解 Demdex 域调用
solution: Audience Manager
title: 了解 Demdex 域调用
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 了解 Demdex 域调用{#understanding-calls-to-the-demdex-domain}

Audience Manager 和 Experience Cloud ID 服务可调用 demdex.net 域中的数据并从该域接收数据。这看起来好像Adobe正在处理一个不同寻常的第三方域，但情况并非如此。 本节介绍demdex.net调用中的元素。

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 调用元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> demdex.net</code> </p> </td> 
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. 它反映 <span class="keyword"> 了Audience Manager</span>(Demdex)最初的客户赢取前名称<span class="keyword"> (Demdex</span>)。 <span class="keyword"> Adobe</span> 于2011 <span class="keyword"> 年收购Demdex</span> ，并将公司重新命名为 <span class="keyword"> Audience Manager</span>。 很难更改此域，因为它与 <span class="keyword"> Audience Manager</span>、 <span class="wintitle"> ID服务以及我们的已安装用户群紧密相连</span>。 请参阅 <a href="../overview/aam-overview.md#history-and-background"> 历史和背景</a>。 </p> <p>您可能会看到附加到旧 <code> demdex.net</code> 调用的其他前缀( <code> dcs.demdex.net</code>例如 <code> fast.demdex.net</code>，等等)。 无论前缀如何，对的调 <code><i>something</i>.demdex.net</code> 用始终是对 <span class="keyword"> Adobe</span> 的调用，而不是对某个未知或可疑的第三方域的调用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> 是“数据提供者匹配 <span class="wintitle"> ”的缩写</span>。 它告诉内部 <span class="keyword"> Adobe</span> 系统， <span class="keyword"> Audience Manager</span> 或 <span class="wintitle"></span> ID服务的调用正在传递客户数据以进行同步或请求ID。 这是Audience Manager或 <code> demdex.net</code> ID服务中最常见的调 <span class="keyword"> 用</span><span class="wintitle"> 。</span> </p> <p><span class="wintitle"> DPM调用基础知识</span> : </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Audience Manager</span></b>:来自 <span class="wintitle"> Audience Manager的DPM调用将数据发送到</span> Data Collection Server和Adobe <span class="keyword"> Cache Server</span> (数据收集服 <span class="wintitle"></span><span class="wintitle"></span>务器)。 请参阅 <a href="../reference/system-components/components-data-collection.md"> 数据收集组件</a>。 </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> <span class="wintitle"> ID服务</span></b>:来自 <span class="wintitle"> ID服务的DPM调用是对访客ID的请求</span><span class="wintitle"></span> 。 请参 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> 阅Cookie和Experience Cloud ID服务</a> ，以及 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> Experience Cloud ID服务如何请求和设置ID</a>。 </li> 
     </ul> </p> <p> <p>注意： <span class="wintitle"> ID服务</span> ，客户可以更改域名中的 <span class="wintitle"> DPM</span> 前缀。 请参 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> 阅audienceManager server和audienceManagerServerSecure</a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Experience Cloud ID 服务](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Audience Manager Cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)

