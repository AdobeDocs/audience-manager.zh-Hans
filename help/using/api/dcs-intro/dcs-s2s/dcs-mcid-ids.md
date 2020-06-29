---
description: ID服务客户应参阅本节，了解如何读取访客cookie，以获取进行DCS API调用所需的ID。
seo-description: ID服务客户应参阅本节，了解如何读取访客cookie，以获取进行DCS API调用所需的ID。
seo-title: 通过 Adobe Experience Platform Identity Service 获取用户 ID 和区域
solution: Audience Manager
title: 通过 Adobe Experience Platform Identity Service 获取用户 ID 和区域
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 9%

---


# 通过 Adobe Experience Platform Identity Service 获取用户 ID 和区域 {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID服务客户应参阅本节，了解如何读取访客cookie以获取进行API调用所需 [!DNL DCS] 的ID。

## 从ID服务Cookie获取用户ID {#get-user-ids-from-service-cookie}

Adobe Experience Platform [身份服务](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html) ，会为访问您网站的用户分配访客和区域ID。 这些ID可识别中所有解决方案中的 [!DNL Experience Cloud] 用户，如果您要拨叫，则需要这些 [!DNL DCS] ID。

* 需要 [!UICONTROL user ID] 识别数据并将其与特定访客关联。
* 此 [!UICONTROL region ID] 项是必需的，因为它绑定到区域服务器名称，您需要将数据发送到该服务器 [!DNL DCS]。 在地理 [!DNL DCS] 上最接近站点访客的数据中心中存储信息。 请参阅 [DCS 区域 ID、位置和主机名](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

ID服务客户可以从ID服务Cookie或通过调用函数提取此信息。 下表描述了开始操作所需完成的任务或步骤。

斜体 *代码* 表示变量占位符。

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 任务 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. 检查您的 <span class="keyword"> Experience Cloud</span> 状态</b> </p> </td> 
   <td colname="col2"> <p>您需要一个 <span class="keyword"> Experience Cloud</span> 帐户才能使用ID服务。 如果你有 <span class="keyword"> Experience Cloud</span> ，太好了！ </p> <p> 如果您不是Experience Cloud的一 <span class="keyword"> 员</span>，请注册。 我们很想拥有你，而且总有更多空间。 有关如何设置帐户的说明，请参阅为核 <a href="https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> 心服务启用解决方案</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Set up the <span class="keyword"> ID service</span></b> </p> </td> 
   <td colname="col2"> <p>ID <span class="keyword"> 服务由</span> JavaScript代码组成，这些代码会放在要用于数据收集的每个页面上。 有关详细信息， <a href="https://docs.adobe.com/content/help/en/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> 请参阅</a> ID服务实施指南。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. 阅读 <span class="keyword"> ID服务</span> Cookie</b> </p> </td> 
   <td colname="col2"> <p>ID服 <span class="keyword"> 务将用户</span> 和区域ID存储在AMCV cookie中。 完整的Cookie名称为 <code>AMCV_<i>###</i>@AdobeOrg</code>。 元 <code><i>###</i></code> 素是您的组织ID的占位符。 See <a href="https://docs.adobe.com/content/help/zh-Hans/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>解析AMCV cookie，以找到这些键值对： </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: 此键值对包含 <span class="keyword"> Experience Cloud</span> ID。 </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: 此键值对包含与区域服务器名称关联的区 <span class="term"> 域ID</span>（有时称为位置提示）。 </li> 
     </ul> </p> <p>用户和区域ID <span class="wintitle"> 一经</span> ，即可向DCS发出调用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. 使用getMarketingCloud <span class="keyword"> Visitor</span> ID检索Experience CloudID</b> </p> </td> 
   <td colname="col2"> <p><i>(可选</i> )此函数返回 <span class="keyword"> Experience Cloud</span> 访客ID。 它专为自定义解决方案和特定用例而设计。 请参 <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> 阅下面的使用getMarketingCloudVisitor</a> ID和相关 <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> ID服务文档</a>。 </p> <p>如果从ID服务Cookie获取用户和位置ID，则无需使用它。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用 `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

获取访客ID的另一种方法是使用该函 `getMarketingCloudVisitorID` 数。 调用此函数时，将查询 [!DNL ID service] 该函数并返回ID。 `getMarketingCloudVisitorID` 接受可选 `callback` 参数，如所示：

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### 回调使用和用途 {#callback-usage}

`callback` 为可选。 此函数不起作用，但仅当访客的浏览器中有cookie时 [!DNL Experience Cloud] 才返回ID。 如果访客cookie缺失，或访客没有ID，则函数返回空对 `()` 象。 即使页面加载且访客收到新ID后，也会发生这种情况。 要避免这种情况 `callback` ，请强制此函数在页面加载后检查访客ID。 如 `callback`果没有，访客ID函数将不返回ID，即使它稍后写入访客的浏览器。

## 后续步骤 {#next-steps}

获得用户和区域ID后，即可开始发送和接收 [!DNL DCS] 数据。 请参 [阅进行DCS API调用](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。