---
description: ID服务客户应参阅本节，了解如何为进行DCS API调用所需的ID读取访客Cookie。
seo-description: ID服务客户应参阅本节，了解如何为进行DCS API调用所需的ID读取访客Cookie。
seo-title: 通过 Adobe Experience Platform Identity Service 获取用户 ID 和区域
solution: Audience Manager
title: 通过 Adobe Experience Platform Identity Service 获取用户 ID 和区域
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
translation-type: tm+mt
source-git-commit: e40233ace5cb74743db7d0f9f90707fa596a7e79
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 9%

---


# 通过 Adobe Experience Platform Identity Service 获取用户 ID 和区域 {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID服务客户应参阅本节，了解如何为进行[!DNL DCS] API调用所需的ID读取访客Cookie。

## 从ID服务Cookie {#get-user-ids-from-service-cookie}获取用户ID

[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)为访问您网站的用户分配访客和区域ID。 这些ID可标识[!DNL Experience Cloud]中所有解决方案的用户，如果您要进行[!DNL DCS]调用，则需要这些ID。

* [!UICONTROL user ID]是标识数据并将其与特定访客关联的必需参数。
* [!UICONTROL region ID]是必需的，因为它与区域服务器名称关联，您需要将数据发送到[!DNL DCS]。 [!DNL DCS]在地理上最接近站点访客的数据中心中存储信息。 请参阅 [DCS 区域 ID、位置和主机名](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

ID服务客户可以从ID服务Cookie或通过调用函数提取此信息。 下表说明了您需要完成的任务或步骤以开始操作。

*斜体*&#x200B;中的代码表示变量占位符。

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 任务 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. 检查<span class="keyword">Experience Cloud</span>状态</b> </p> </td> 
   <td colname="col2"> <p>您需要<span class="keyword">Experience Cloud</span>帐户才能使用ID服务。 如果您有<span class="keyword">Experience Cloud</span>帐户，太棒了！ </p> <p> 如果您不是<span class="keyword">Experience Cloud</span>的一部分，请注册。 我们很想拥有您，而且总有更多空间。 有关如何设置帐户的说明，请参阅<a href="https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html" format="https" scope="external">启用核心服务的解决方案</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. 设置<span class="keyword"> ID服务</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID服务</span>由JavaScript代码组成，这些代码被放置在要用于数据收集的每个页面上。 有关详细信息，请参阅ID服务<a href="https://docs.adobe.com/content/help/en/id-service/using/implementation/implementation-guides.html" format="https" scope="external">实现指南</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. 阅读<span class="keyword"> ID服务</span> cookie</b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID服务</span>将用户和区域ID存储在AMCV Cookie中。 完整Cookie名称为<code>AMCV_<i>###</i>@AdobeOrg</code>。 <code><i>###</i></code>元素是您的组织ID的占位符。 有关详细信息，请参阅<a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Experience CloudID</a>。 </p> <p>解析AMCV Cookie以找到以下键值对： </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>:此键值对包含Experience  <span class="keyword"> Cloud</span> 用户ID。 </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>:此键值对保存与区域服务器名称关联的区域 <span class="term"> ID</span>（有时称为位置提示）。 </li> 
     </ul> </p> <p>一旦有了用户和区域ID，您就可以对<span class="wintitle"> DCS</span>进行调用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. 使用getMarketingCloudVisitorID</b>检索<span class="keyword">Experience CloudID</span> </p> </td> 
   <td colname="col2"> <p><i>（可选）</i> 此函数返回 <span class="keyword"> Experience </span> Cloud访客ID。它专为定制解决方案和特定用例而设计。 请参阅下面的<a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid">使用getMarketingCloudVisitorID</a>和<a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external">相关ID服务文档</a>。 </p> <p>如果从ID服务Cookie获取用户和位置ID，则无需使用它。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用`getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

获取访客ID的另一种方法是使用`getMarketingCloudVisitorID`函数。 调用此函数时，将查询[!DNL ID service]并返回ID。 `getMarketingCloudVisitorID` 接受可选 `callback` 参数，如所示：

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### 回调使用情况和用途{#callback-usage}

`callback` 为可选。此函数不使用它，但仅当访客在其浏览器中具有[!DNL Experience Cloud] Cookie时才返回ID。 如果访客Cookie缺失，或访客没有ID，则函数返回空`()`对象。 即使在页面加载且访客收到新ID后，也可能发生这种情况。 为避免这种情况，`callback`在页面加载后强制此函数检查访客ID。 如果没有`callback`，则访客 ID函数将不返回ID，即使稍后将其写入访客的浏览器也是如此。

## 后续步骤 {#next-steps}

获得用户和区域ID后，即可开始发送和接收[!DNL DCS]数据。 请参阅[进行DCS API调用](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。