---
description: Audience Manager和Adobe Experience Platform标识服务向demdex.net域发出调用并从中接收数据。 这看起来好像Adobe正在处理一个不同寻常的第三方域，但情况并非如此。 本节介绍demdex.net调用中的元素。
seo-description: Audience Manager和Adobe Experience Platform标识服务向demdex.net域发出调用并从中接收数据。 这看起来好像Adobe正在处理一个不同寻常的第三方域，但情况并非如此。 本节介绍demdex.net调用中的元素。
seo-title: 了解 Demdex 域调用
solution: Audience Manager
title: 了解 Demdex 域调用
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: d219f6fa1e2a8396b049f86391142c00e263b629
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 5%

---


# 了解 Demdex 域调用{#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] Adobe Experience Platform标识服务向demdex.net域发出调用并从其接收数据。 这看起来好像Adobe正在处理一个不同寻常的第三方域，但情况并非如此。 本节介绍呼叫中的 `demdex.net` 元素。

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
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. 它反映 <span class="keyword"> 了</span>Audience Manager<span class="keyword"> 最初的收购前名称(</span>Demdex)。 <span class="keyword"> Adobe</span> 在 <span class="keyword"> 2011年收购了Demdex</span> ，并将公司重新命名为 <span class="keyword"> Audience Manager</span>。 更改此域很困难，因为它与Audience Manager、 <span class="keyword"> ID服务</span><span class="wintitle"> 和我们安装的用户群紧密相连</span>。 请参阅 <a href="../overview/aam-overview.md#history-and-background"> 历史和背景</a>。 </p> <p>您可能会看到附加到旧 <code> demdex.net</code> 版调用的其他前缀 <code> dcs.demdex.net</code>( <code> fast.demdex.net</code>例如，等等)。 无论前缀是什么，对的调 <code><i>something</i>.demdex.net</code> 用始终是对Adobe的调 <span class="keyword"> 用</span> ，而不是对某个未知或可疑的第三方域的调用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> 是数据提供 <span class="wintitle"> 程序匹配的缩写</span>。 它告诉内部 <span class="keyword"> Adobe</span> 系统，来自Audience Manager或ID服务的 <span class="keyword"> 调用</span> ，正在传 <span class="wintitle"></span> 递客户数据以进行同步或请求ID。 这是Audience Manager <code> demdex.net</code> 或ID服务中最常见的 <span class="keyword"> 调</span> 用 <span class="wintitle"> 。</span> </p> <p><span class="wintitle"> DPM调用</span> 基础知识： </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Audience Manager</span></b>: 来自 <span class="wintitle"> Audience Manager的</span> DPM调用将数据发送至 <span class="keyword"> 收集服务器</span> 和用户档案缓 <span class="wintitle"></span><span class="wintitle"></span>存服务器。 请参 <a href="../reference/system-components/components-data-collection.md"> 阅数据收集组件</a>。 </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> <span class="wintitle"> ID服务</span></b>: 来自 <span class="wintitle"> ID</span> 服务的 <span class="wintitle"></span> DPM调用是对访客ID的请求。 请参 <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> 阅Cookie和Adobe Experience Platform身份服务</a><a href="https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html" format="https" scope="external"> 以及Adobe Experience Platform身份服务如何请求和设置ID</a>。 </li> 
     </ul> </p> <p> <p>注意：  <span class="wintitle"> ID服务</span> 客户可以更改 <span class="wintitle"> 域名中</span> 的DPM前缀。 请参 <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html" format="https" scope="external"> 阅audienceManager Server和audienceManagerServerSecure</a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform身份服务](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Audience Manager Cookie](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html)

