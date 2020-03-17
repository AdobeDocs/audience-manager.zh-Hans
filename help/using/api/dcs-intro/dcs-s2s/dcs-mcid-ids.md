---
description: ID服务客户应参阅本节，了解如何读取访客cookie以获取进行DCS API调用所需的ID。
seo-description: ID服务客户应参阅本节，了解如何读取访客cookie以获取进行DCS API调用所需的ID。
seo-title: 通过Adobe Experience Platform Identity Service获取用户ID和区域
solution: Audience Manager
title: 通过Adobe Experience Platform Identity Service获取用户ID和区域
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# 通过Adobe Experience Platform Identity Service获取用户ID和区域 {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID服务客户应参阅本节，了解如何读取访客cookie以获取进行API调用所需 [!UICONTROL DCS] 的ID。

## 从ID服务Cookie获取用户ID {#get-user-ids-from-service-cookie}

Adobe [](https://marketing.adobe.com/resources/help/en_US/mcvid/) Experience Platform Identity Service将访客和区域ID分配给访问您网站的用户。 这些ID可识别中所有解决方案中的用 [!DNL Experience Cloud] 户，如果您要拨打电话，则需要这些 [!UICONTROL DCS] ID。

* 需 [!UICONTROL user ID] 要识别数据并将其与特定访客关联。
* 此 [!UICONTROL region ID] 为必需项，因为它绑定到区域服务器名称，您需要将数据发送到该名称 [!UICONTROL DCS]。 这些 [!UICONTROL DCS] 信息存储在地理上最接近站点访问者的数据中心中。 请参阅 [DCS 区域 ID、位置和主机名](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

ID服务客户可以从ID服务Cookie或通过调用函数提取此信息。 下表描述了开始操作所需完成的任务或步骤。

斜体中 *的代码* ，表示变量占位符。

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 任务 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. 检查您 <span class="keyword"> 的Experience Cloud状态</span></b> </p> </td> 
   <td colname="col2"> <p>您需要 <span class="keyword"> Experience Cloud帐户</span> ，才能使用ID服务。 如果您有 <span class="keyword"> Experience Cloud帐户</span> ，太好了！ </p> <p> 如果您不是Experience Cloud的一部分 <span class="keyword"></span>，请注册。 我们很想拥有您，而且总有更多空间。 有关如何设置帐户的说明，请参阅核心服 <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=core_services.html" format="https" scope="external"> 务——启用您的解决方案</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Set up the <span class="keyword"> ID service</span></b> </p> </td> 
   <td colname="col2"> <p>ID服 <span class="keyword"> 务由JavaScript代码组成</span> ，这些代码放置在要用于数据收集的每个页面上。 有关详细信息，请 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html" format="https" scope="external"> 参阅ID服务实施指南</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. 阅读 <span class="keyword"> ID服务</span> Cookie</b> </p> </td> 
   <td colname="col2"> <p>ID服 <span class="keyword"> 务将用户</span> ID和区域ID存储在AMCV Cookie中。 完整的Cookie名称为 <code>AMCV_<i>###</i>@AdobeOrg</code>。 这些 <code><i>###</i></code> 元素是您的组织ID的占位符。 See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>解析AMCV cookie以找到以下键值对： </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>:此键值对包含 <span class="keyword"> Experience Cloud用户ID</span> 。 </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>:此键值对保存与区域服务器名称关联的区域ID(有时称 <span class="term"> 为位置提示</span>)。 </li> 
     </ul> </p> <p>用户和区域ID一经拥 <span class="wintitle"> 有</span> ，即可向DCS发出调用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. 使用getMarketingCloudVisitorID <span class="keyword"> 检索Experience Cloud</span> ID</b> </p> </td> 
   <td colname="col2"> <p><i>（可选）</i> ，此函数返回 <span class="keyword"> Experience Cloud访客ID</span> 。 它专为自定义解决方案和特定用例而设计。 请参 <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> 阅下面的使用getMarketingCloudVisitorID</a> 和相关 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-getmcvid.html" format="https" scope="external"> ID服务文档</a>。 </p> <p>如果您从ID服务Cookie中获得用户和位置ID，则无需使用它。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用(W) `getMarketingCloudVisitorID`{#working-with-getmarketingcloudvisitorid}

获取访客ID的另一种方法是使用该函 `getMarketingCloudVisitorID` 数。 调用此函数时，将查询 [!DNL ID service] 并返回ID。 `getMarketingCloudVisitorID` 接受可选 `callback` 参数，如下所示：

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### 回调使用和用途 {#callback-usage}

`callback` 为可选项。 此函数不起作用，但仅当访客的浏览器中有 [!DNL Experience Cloud] cookie时才返回ID。 如果访客cookie缺失，或访客没有ID，则函数将返回空对 `()` 象。 即使页面加载且访客收到新ID后，也会发生这种情况。 要避免这种情况， `callback` 请强制此函数在页面加载后检查访客ID。 如果 `callback`不返回，则访客ID函数将不会返回ID，即使该ID稍后写入访客的浏览器。

## 后续步骤 {#next-steps}

获得用户和区域ID后，即可开始发送和接收数 [!UICONTROL DCS] 据。 请参 [阅发出DCS API调用](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。