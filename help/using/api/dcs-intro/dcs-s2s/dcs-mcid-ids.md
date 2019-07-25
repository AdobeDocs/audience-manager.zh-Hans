---
description: ID服务客户应参阅本节，以了解有关如何为进行DCS API调用所需ID读取访客cookie的信息。
seo-description: ID服务客户应参阅本节，以了解有关如何为进行DCS API调用所需ID读取访客cookie的信息。
seo-title: 通过Experience Cloud ID服务获取用户ID和区域
solution: Audience Manager
title: 通过Experience Cloud ID服务获取用户ID和区域
uuid: 80de6cf2-5d9e-4ef8-a0 f2-d53 b5 d574 c89
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions Through the Experience Cloud ID Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make [!UICONTROL DCS] API calls.

## Get the User ID from the ID Service Cookie {#get-user-ids-from-service-cookie}

[Experience Cloud ID服务](https://marketing.adobe.com/resources/help/en_US/mcvid/) 可为访问您网站的用户分配访客和区域ID。These IDs identify users across all the solutions in the [!DNL Experience Cloud] and they are required if you want to make [!UICONTROL DCS] calls.

* [!UICONTROL user ID] 需要识别数据并将其关联到特定访客。
* The [!UICONTROL region ID] is required because it is tied to a regional server name, which you need to send data to the [!UICONTROL DCS]. The [!UICONTROL DCS] stores information in data centers that are geographically closest to site visitors. 请参阅 [DCS 区域 ID、位置和主机名](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

ID服务客户可以从ID服务cookie中提取此信息或调用函数。下表介绍了完成工作所需的任务或步骤。

*斜体代码* 表示变量占位符。

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 任务 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Check your <span class="keyword"> Experience Cloud</span> status</b> </p> </td> 
   <td colname="col2"> <p>You need a <span class="keyword"> Experience Cloud</span> account to use the ID service. If you have a <span class="keyword"> Experience Cloud</span> account, great! </p> <p> If you're not part of the <span class="keyword"> Experience Cloud</span>, then sign up. 我们很乐意为您提供更多信息，而且还有更多的机会。For instructions on how to set up an account, see <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=core_services.html" format="https" scope="external"> Core Services - Enabling Your Solutions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Set up the <span class="keyword"> ID service</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID服务</span> 由JavaScript代码组成，这些代码放在要用于数据收集的每个页面上。See the ID service <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html" format="https" scope="external"> implementation guides</a> for more information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Read the <span class="keyword"> ID service</span> cookie</b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID服务</span> 存储AMCV cookie中的用户和区域ID。The full cookie name is <code>AMCV_<i>###</i>@AdobeOrg</code>. <code><i>###</i></code> 元素是组织ID的占位符。See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>解析这些键值对的AMCV cookie： </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>id=<i>用户ID</i></code>：此键值对包含 <span class="keyword"> Experience Cloud</span> 用户ID。 </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamweaver=<i>地区ID</i></code>：此键值对存放与区域服务器名称关联的区域ID(有时称为 <span class="term"> 位置提示</span>)。 </li> 
     </ul> </p> <p>You can make calls to the <span class="wintitle"> DCS</span> once you have the user and region IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Retrieve the <span class="keyword"> Experience Cloud ID</span> with getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(可选)</i> 此函数返回 <span class="keyword"> Experience Cloud</span> 访客ID。它专为自定义解决方案和特定用例而设计。See <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Working With getMarketingCloudVisitorID</a> below and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-getmcvid.html" format="https" scope="external"> related ID service documentation</a>. </p> <p>如果您从ID服务cookie获得用户和位置ID，则无需使用此设置。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Working With `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Another way to get the visitor ID is with the `getMarketingCloudVisitorID` function. When invoked, this function queries the [!DNL ID service] and returns an ID. `getMarketingCloudVisitorID` 接受所示的可选 `callback` 参数：

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Callback Usage and Purpose {#callback-usage}

`callback` 是可选的。This function works without it, but returns an ID only when a visitor has a [!DNL Experience Cloud] cookie in their browser. If the visitor cookie is missing, or a visitor doesn't have an ID, the function returns an empty `()` object. 即使在加载页面且访客收到新ID后，也可能发生这种情况。To avoid this, `callback` forces this function to check for a visitor ID after the page loads. Without `callback`, the visitor ID function won't return an ID even if it's written to the visitor's browser later.

## 后续步骤 {#next-steps}

Once you have the user and region ID, you can start sending and receiving [!UICONTROL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).