---
description: ID服务客户应该参阅此部分，了解有关如何读取访客Cookie以获取DCS API调用所需的ID的信息。
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: 通过Adobe Experience Platform Identity服务获取用户ID和区域
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 2%

---

# 通过Adobe Experience Platform Identity服务获取用户ID和区域 {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID服务客户应该参阅本节以了解如何读取访客Cookie，以获取进行[!DNL DCS] API调用所需的ID。

## 从ID服务Cookie获取用户ID {#get-user-ids-from-service-cookie}

[Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)将访客和区域ID分配给访问您网站的用户。 这些ID标识[!DNL Experience Cloud]中所有解决方案的用户，如果要进行[!DNL DCS]调用，则需要这些ID。

* 需要[!UICONTROL user ID]才能识别数据并将其与特定访客关联。
* [!UICONTROL region ID]是必需的，因为它绑定到区域服务器名称，您需要将该名称将数据发送到[!DNL DCS]。 [!DNL DCS]将信息存储在地理位置最接近网站访客的数据中心。 请参阅 [DCS 区域 ID、位置和主机名](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

ID服务客户可以从ID服务Cookie或通过调用函数来提取此信息。 下表描述了开始使用时需要完成的任务或步骤。

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
   <td colname="col1"> <p> <b>1. 检查您的<span class="keyword">Experience Cloud</span>状态</b> </p> </td> 
   <td colname="col2"> <p>您需要<span class="keyword">Experience Cloud</span>帐户才能使用ID服务。 如果您有<span class="keyword">Experience Cloud</span>帐户，非常好！ </p> <p> 如果您不属于<span class="keyword">Experience Cloud</span>，请注册。 我们很乐意拥有你，而且总是有更多的空间。 有关如何设置帐户的说明，请参阅<a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external">启用核心服务的解决方案</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. 设置<span class="keyword"> ID服务</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID服务</span>包含JavaScript代码，这些代码放置到您要用于数据收集的每个页面上。 有关详细信息，请参阅ID服务<a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external">实施指南</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. 读取<span class="keyword"> ID服务</span> Cookie</b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID服务</span>将用户和区域ID存储在AMCV Cookie中。 完整的Cookie名称为<code>AMCV_<i>###</i>@AdobeOrg</code>。 <code><i>###</i></code>元素是您的组织ID的占位符。 有关详细信息，请参阅<a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Experience CloudID</a>。 </p> <p>解析这些键值对的AMCV Cookie： </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>：此键值对包含<span class="keyword">Experience Cloud</span>用户ID。 </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>：此键值对包含与区域服务器名称关联的区域ID （有时称为<span class="term">位置提示</span>）。 </li> 
     </ul> </p> <p>一旦拥有用户和区域ID，您就可以调用<span class="wintitle"> DCS</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. 使用getMarketingCloudVisitorID</b>检索<span class="keyword">Experience CloudID</span> </p> </td> 
   <td colname="col2"> <p><i>（可选）</i>此函数返回<span class="keyword">Experience Cloud</span>访客标识。 它专为自定义解决方案和特定用例而设计。 请参阅下面的<a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid">使用getMarketingCloudVisitorID</a>以及<a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external">相关的ID服务文档</a>。 </p> <p>如果您从ID服务Cookie中获取用户和位置ID，则无需使用此项。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用`getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

获取访客ID的另一种方法是使用`getMarketingCloudVisitorID`函数。 调用时，此函数将查询[!DNL ID service]并返回ID。 `getMarketingCloudVisitorID`接受可选的`callback`参数，如下所示：

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### 回调使用情况和用途 {#callback-usage}

`callback`是可选的。 此函数无需使用它即可运行，但仅当访客的浏览器中具有[!DNL Experience Cloud] Cookie时才返回ID。 如果访客Cookie缺失，或访客没有ID，则此函数将返回空`()`对象。 即使在页面加载且访客收到新ID后，也可能发生这种情况。 为避免这种情况，`callback`强制此函数在页面加载后检查访客ID。 如果没有`callback`，访客ID函数将不会返回ID，即使稍后将其写入访客的浏览器中也是如此。

## 后续步骤 {#next-steps}

一旦您拥有了用户和地区ID，就可以开始发送和接收[!DNL DCS]数据。 请参阅[进行DCS API调用](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。
