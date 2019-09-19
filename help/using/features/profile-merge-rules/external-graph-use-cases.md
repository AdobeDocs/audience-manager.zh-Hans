---
description: 使用外部设备图表，为未知用户推荐和使用案例，以便发现、重新定位和个性化。 外部设备图形定义为与Audience manager分开的设备图形。 这包括Adobe Experience Cloud Device Co-op以及Adobe与第三方确定性或概率性设备图形公司进行的其他集成。
seo-description: 使用外部设备图表，为未知用户推荐和使用案例，以便发现、重新定位和个性化。 外部设备图形定义为与Audience manager分开的设备图形。 这包括Adobe Experience Cloud Device Co-op以及Adobe与第三方确定性或概率性设备图形公司进行的其他集成。
seo-title: 外部设备图形使用案例
solution: Audience Manager
title: 外部设备图形使用案例
uuid: f4bc822d-39d2-4680-90ed-7ee2ead6db6f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 外部设备图形使用案例 {#external-device-graph-use-cases}

使用外部设备图表，为未知用户推荐和使用案例，以便发现、重新定位和个性化。 外部设备图形定义为与Audience manager分开的设备图形。 这包括Adobe [!DNL Adobe Experience Cloud Device Co-op] 与第三方确定性或概率性设备图形公司的集成和其他集成。

## 推荐 {#recommendations}

考虑以下 [!DNL Experience Cloud Device Co-op] 营销活动的第三方设备图形选项：

* 在数字资产中进行低级别的身份验证。 如果您有 [大量经过身份验证的用户](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) ，请使用“配置文件链接”设备图形选项。
* 瞄准大型受众。 第三 [!DNL Experience Cloud Device Co-op] 方设备图形包含经过身份验证和未经过身份验证的数据。
* 在个人和家庭层面对经过身份验证和／或未经身份验证的访客进行细分。

![](assets/merge-rule-triangle1.png)

## 潜在客户／品牌使用案例 {#prospecting-branding-use-cases}

品牌营销活动旨在触及尽可能多的用户。 它对细分资格没有限制。 但是，这些营销活动会不断定位多次查看内容且无法转化的人员，从而浪费预算和印象。 使用 [!UICONTROL Profile Merge] 该或第三方选 [!DNL Device Co-op] 项的规则可以帮助您创建有效的品牌营销活动。 例如，在设置的频率上限跨多个设备查看这些未知用户后，您可以将这些用户添加到“非市场内”区段。

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
   <td colname="col2">此用例假定以下条件： <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">您希望为特定广告营销活动的匿名用户提供最多10个展示。 </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">用户具有多个设备，并且可能已或可能未通过站点身份验证。 </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">匿名用户在其当前设备上以未验证状态浏览广告时，以及通过外部设备图形链接的最多3个设备时，共查看10次广告。 </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">您定义了 <span class="keyword"> Audience Manager细分</span> ，以在匿名用户看到10个印象后对其进行资格鉴定。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>鉴于这些条件， <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">合并从当前设备收集的匿名未验证活动和通过外部设备图形链接的3台设备（每个设备的广告印象）。 </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">根据通过外部设备图形和当前设备链接的所有3台设备上的匿名活动组合，评估未通过身份验证的用户的细分资格。 </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">将该段发送到任何实时目标，以用作当前设备上的抑制段以及通过外部设备图形链接的所有3台设备。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 重新定位或网站个性化用例 {#retargeting-use-case}

这些策略旨在将未经身份验证或未知的用户带回您的网站，或在其上线时个性化其浏览体验。

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
   <td colname="col2">此用例假定以下条件： <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">您希望根据匿名用户在未验证状态下的网站活动，为其提供个性化的现场和／或场外体验。 </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">用户具有多个设备，并且可能已或可能未通过站点身份验证。 </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">当用户在当前设备上以未验证状态浏览并且最多3台通过外部设备图形链接的设备时，用户会查看您网站上的多个页面。 </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">您定义了 <span class="keyword"> Audience Manager区段</span> ，以便在用户在以未验证状态浏览时查看网站上的多个页面后，确定其资格。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>鉴于这些条件， <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">合并从当前设备收集的匿名未验证活动和通过外部设备图形链接的3台设备（每个设备的多个页面查看）。 </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">根据通过外部设备图形和当前设备链接的所有3台设备上的匿名活动组合，评估未通过身份验证的用户的细分资格。 </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">将区段发送到任何实时目标，以在当前设备和通过外部设备图形链接的所有3台设备上提供个性化的现场和／或场外体验。 </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## 外部设备图形使用案例的配置文件合并规则选项 {#profile-merge}

这些用例的合并规则选项与下面显示的可用选项类似。 这些 [!UICONTROL Authenticated Profile] 选项会被取消激活，因为这些设置仅在您选择或时 **[!UICONTROL Current Authenticated Profile]** 才可用 **[!UICONTROL Last Authenticated Profile]**。 您 [!UICONTROL Device Options] 的设备图设置将因您要使用或可用的设备图设置类型而异。

![](assets/merge-rules-external.png)

有关这些设备图形处理方式的更多信息，请下载我们的PDF、 [Audience manager和外部设备图形](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf)。

>[!MORE_LIKE_THIS]
>
>* [配置文件链接设备图形使用案例](../../features/profile-merge-rules/profile-link-use-case.md)
>* [配置文件合并规则的一般用例](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [个人资料合并规则常见问题解答](../../faq/faq-profile-merge.md)

