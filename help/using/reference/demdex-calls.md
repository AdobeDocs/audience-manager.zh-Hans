---
description: Audience Manager 和 Experience Cloud ID 服务可调用 demdex.net 域中的数据并从该域接收数据。这好像Adobe正与一个不同寻常的第三方域合作，但事实并非如此。本节介绍demdex. net调用中的元素。
seo-description: Audience Manager 和 Experience Cloud ID 服务可调用 demdex.net 域中的数据并从该域接收数据。这好像Adobe正与一个不同寻常的第三方域合作，但事实并非如此。本节介绍demdex. net调用中的元素。
seo-title: 了解 Demdex 域调用
solution: Audience Manager
title: 了解 Demdex 域调用
uuid: c06ae3a-f169-4712-80fb-d6 d448 dce51 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 了解 Demdex 域调用{#understanding-calls-to-the-demdex-domain}

Audience Manager 和 Experience Cloud ID 服务可调用 demdex.net 域中的数据并从该域接收数据。这好像Adobe正与一个不同寻常的第三方域合作，但事实并非如此。本节介绍demdex. net调用中的元素。

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
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. It reflects <span class="keyword"> Audience Manager</span>'s original, pre-acquisition name (<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> 在2011年收购 <span class="keyword"> 了Demdex</span> ，并更名为 <span class="keyword"> Audience Manager</span>公司。It is difficult to change this domain because it is entwined deeply with <span class="keyword"> Audience Manager</span>, the <span class="wintitle"> ID service</span>, and our installed user base. See <a href="../overview/aam-overview.md#history-and-background"> History and Background</a>. </p> <p>You may see other prefixes attached to legacy <code> demdex.net</code> calls (e.g., <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>, etc.). Regardless of the prefix, a call to <code><i>something</i>.demdex.net</code> is always a call to <span class="keyword"> Adobe</span> and not to some unknown or suspicious third-party domain. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> 是 <span class="wintitle"> 数据提供商匹配</span>的缩写。It tells internal, <span class="keyword"> Adobe</span> systems that a call from <span class="keyword"> Audience Manager</span> or the <span class="wintitle"> ID service</span> is passing in customer data for synchronization or requesting an ID. This is the most common <code> demdex.net</code> call you'll see from <span class="keyword"> Audience Manager</span> or the <span class="wintitle"> ID service</span>. </p> <p><span class="wintitle"> DPM</span> 调用基础知识： </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b><span class="keyword"> Audience Manager</span></b>：Audience Manager的 <span class="wintitle"> DPM</span><span class="keyword"> 调用将数据</span> 发送到 <span class="wintitle"> 数据收集服务器</span> 和 <span class="wintitle"> 配置文件缓存服务器</span>。See <a href="../reference/system-components/components-data-collection.md"> Data Collection Components</a>. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b><span class="wintitle"> ID服务</span></b>：来自ID服务的 <span class="wintitle"> DPM</span><span class="wintitle"> 调用</span> 是访客ID的请求。See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> and <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> How the Experience Cloud ID Service Requests and Sets IDs</a>. </li> 
     </ul> </p> <p> <p>Note:  <span class="wintitle"> ID service</span> customers can change the <span class="wintitle"> DPM</span> prefix in the domain name. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> audienceManager Server and audienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [Experience Cloud ID 服务](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Audience Manager Cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)

