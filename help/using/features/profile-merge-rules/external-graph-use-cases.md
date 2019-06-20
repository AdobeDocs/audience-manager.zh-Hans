---
description: 针对未知用户使用外部设备图探索、重定向和个性化的推荐和使用案例。外部设备图定义为与Audience Manager分开的设备图表。这包括Adobe Experience Cloud Device Co-op和Adobe与第三方确定或概率设备图公司的其他集成。
seo-description: 针对未知用户使用外部设备图探索、重定向和个性化的推荐和使用案例。外部设备图定义为与Audience Manager分开的设备图表。这包括Adobe Experience Cloud Device Co-op和Adobe与第三方确定或概率设备图公司的其他集成。
seo-title: 外部设备图形使用案例
solution: Audience Manager
title: 外部设备图形使用案例
uuid: f4bc822d-39d2-4680-90ed-7ee2ead6db6f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 外部设备图形使用案例 {#external-device-graph-use-cases}

针对未知用户使用外部设备图探索、重定向和个性化的推荐和使用案例。外部设备图定义为与Audience Manager分开的设备图表。This includes the [!DNL Adobe Experience Cloud Device Co-op] and other integrations Adobe has with third-party deterministic or probabilistic device graph companies.

## 推荐 {#recommendations}

Consider the [!DNL Experience Cloud Device Co-op] and third-party device graph options for campaigns that:

* 在其数字资产中具有较低的身份验证级别。Use the [Profile Link device graph option](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) if you have a large number of authenticated users.
* 瞄准大型受众。[!DNL Experience Cloud Device Co-op] 第三方设备图包含经过身份验证和未验证的数据。
* 在个人和家庭级别细分实名和/或未身份验证的访客。

![](assets/merge-rule-triangle1.png)

## Prospecting/Branding Use Case {#prospecting-branding-use-cases}

品牌营销活动旨在触及尽可能多的人群。它对细分资格有一些限制。但是，这些营销活动会持续定位查看您的内容且不转化的人群，从而浪费预算和印象。[!UICONTROL Profile Merge] 使用 [!DNL Device Co-op] 或第三方选项的规则可以帮助您创建有效的品牌营销活动。例如，在为设置频率上限跨多台设备查看这些用户之后，您可以将这些未知的用户添加到“非市场内”区段。

<table id="table_00F6EED172574E80A38CADA8A92A23B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>条件</b> </p> </td> 
   <td colname="col2">此用例假设下列条件： <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">您希望为某个特定广告系列用户最多提供10个匿名用户的印象。 </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">用户有多个设备，也可能未对您的网站进行身份验证。 </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">匿名用户在其当前设备上以未身份身份验证状态浏览时总共将广告视为10次，最多可在外部设备图链接的设备上进行浏览。 </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify anonymous users after they have seen 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">合并从当前设备和外部设备图链接的3设备(每台设备的广告印象)收集的匿名、未验证活动。 </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">根据外部设备图和当前设备链接的所有种设备上的匿名活动组合，评估未经过身份验证的用户进行细分资格的情况。 </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">将区段发送到任何实时目标，用作当前设备上的抑制区段以及外部设备图链接的所有种设备。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retargeting or Site Personalization Use Case {#retargeting-use-case}

这些策略旨在将未经过身份验证或未知的用户带回网站，或在网站上进行浏览体验。

<table id="table_0EE2052AA3E744B3B76036FC06B5A453"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>条件</b> </p> </td> 
   <td colname="col2">此用例假设下列条件： <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">您希望根据匿名用户在未身份验证的状态下的活动，为匿名用户提供个性化的现场和/或场外体验。 </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">用户有多个设备，也可能未对您的网站进行身份验证。 </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">用户在其当前设备上以未身份验证状态浏览时，以及外部设备图链接的最多台设备上查看多个页面。 </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify users after they have viewed multiple pages on your site while browsing in an unauthenticated state. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">合并从当前设备和外部设备图链接的三个设备(每个设备的多个页面视图)收集的匿名、未经过身份验证的活动。 </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">根据外部设备图和当前设备链接的所有种设备上的匿名活动组合，评估未经过身份验证的用户进行细分资格的情况。 </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">将区段发送到任何实时目标，以便在当前设备和外部设备图链接的所有设备上提供个性化的现场和/或线外体验。 </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## Profile Merge Rule Options for External Device Graph Use Cases {#profile-merge}

这些使用案例的合并规则选项类似于下面显示的可用选项。[!UICONTROL Authenticated Profile] 选项将停用，因为这些设置仅在您选择 **[!UICONTROL Current Authenticated Profile]** 或使用时才可用 **[!UICONTROL Last Authenticated Profile]**。Your [!UICONTROL Device Options] will vary depending on the type of device graph setting that you want to use or that is available to you.

![](assets/merge-rules-external.png)

For more information about how these device graph processes work, download our PDF, [Audience Manager and External Device Graphs](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_ LIKE_ This]
>
>* [个人资料链接设备图表使用案例](../../features/profile-merge-rules/profile-link-use-case.md)
>* [个人资料合并规则的一般使用案例](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [个人资料合并规则常见问题解答](../../faq/faq-profile-merge.md)

