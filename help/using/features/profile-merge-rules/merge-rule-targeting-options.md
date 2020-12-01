---
description: 用户档案合并规则选项允许您根据业务需求或目标扩大或收紧受众对特定受众的关注。 这些一般用例探讨如何使用可用选项并为个人、家庭和跨设备定位创建合并规则。
seo-description: 用户档案合并规则选项允许您根据业务需求或目标扩大或收紧受众对特定受众的关注。 这些一般用例探讨如何使用可用选项并为个人、家庭和跨设备定位创建合并规则。
seo-title: 配置文件合并规则的一般用例
solution: Audience Manager
title: 配置文件合并规则的一般用例
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '997'
ht-degree: 4%

---


# 配置文件合并规则的一般用例 {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 通过各种选项，您可以根据业务需要或目标扩大或加强受众对特定受众的关注。这些一般用例探讨如何使用可用选项并为个人、家庭和跨设备定位创建合并规则。 [!UICONTROL Profile Merge Rules] 处理实时和批处理目标。

>[!TIP]
>
>有关这些[!UICONTROL Merge Rule]设置的定义和说明，请参阅[已定义的用户档案合并规则选项](merge-rule-definitions.md)。

## 设备定位{#device-personalization}

此方案适用于希望评估Audience Manager中定义的受众细分的单个设备用户档案的营销人员，以便使用支持设备ID(DSP、在线个性化平台和其他基于设备的定位平台)的定位平台为设备提供一致的体验，而不考虑用户身份验证。

要创建仅目标设备用户档案的规则，请选择&#x200B;**[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**。

![仅限设备](assets/device-only.png)

假设约翰拥有三部智能手机。 其中两款是iPhone 7，在数据计划A上，其中一款是三星，在数据计划B上。若不考虑他在三个设备上的已验证状态，John的移动运营商希望优惠他进行数据计划升级，但只针对在数据计划A上运行的iPhone 7设备。

通过使用&#x200B;**[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**&#x200B;规则，[!DNL Device 1]和[!DNL Device 3]都符合段条件，而忽略设备2。

![仅限设备](assets/device-management.png)

## 共享设备定位{#target-shared-devices}

假设John和他的妻子Jane使用同一台笔记本电脑访问网上商店并订购各种商品。

约翰用自己的账户来订旅行票和特价优惠，而简则用自己的账户来购买音乐和电影。

该商店的营销团队可以使用&#x200B;**[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]**&#x200B;规则，仅根据John和Jane经过身份验证的目标，对其进行特定交易活动。

![当前——无设备](assets/current-no-device.png)

通过使用此规则，Audience Manager会完全忽略设备用户档案、区段的John的CRM ID资格，而不会符合Jane的CRM ID资格。

![共享设备定位](assets/shared-device-targeting.png)

## 联机／脱机定位{#device-household-targeting}

此用例涵盖家庭身份管理。 公司可以使用&#x200B;**[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]**&#x200B;规则将单个设备用户档案与在该设备上验证的最后一个用户档案合并。

![最后设备用户档案](assets/last-device-profile.png)

让我们考虑一个由年收入超过100.000美元／年的家庭组成的细分，其中至少包含一个[!DNL Data Plan B]上的[!DNL iPhone 7]设备。 我们有两个家庭用户档案(跨设备用户档案)，每个都连接到两个不同的设备用户档案。 符合区段条件所需的特征分布于设备和跨设备用户档案。

Audience Manager会合并每台设备+跨设备用户档案对，以查看合并的特征集是否符合区段的条件。 由于Audience Manager对包括在合并中的每个用户档案进行评估，因此可以分段设备用户档案和家庭用户档案。

设备与家庭用户档案之间的链接使Audience Manager能够符合[!DNL Household 2]的区段资格，但不能符合[!DNL Household 1]的条件。 从[!DNL Household 2]中，只有[!DNL Device 3]符合段资格。 这[!UICONTROL Profile Merge Rule]使营销人员能够向单个设备([!DNL Device 3])和更广泛的家庭([!DNL Household 2])提供一致的营销信息。

![家庭管理](assets/household-management.png)

## 针对基于人员的目标{#all-cross-device}

>[!IMPORTANT]
>
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

此定位方案仅适用于已购买[!DNL People-Based Destinations]加载项的客户。 此规则允许营销人员根据他们自己的经过身份验证的数据接触客户。

比如，一家在线零售商希望通过社交平台接触现有客户，并根据先前的订单向他们展示个性化的优惠。 借助[!UICONTROL People-Based Destinations]，他们可以将散列电子邮件地址从自己的[!DNL CRM]收录到Audience Manager中，从离线数据构建区段，并将这些区段发送到他们要投放的社交平台，使用散列标识符优化广告支出。

要进一步了解此选项，请参阅[基于人员的目标](../destinations/people-based-destinations-overview.md)。

![跨设备](assets/all-cross-device.png)

## 设备图选项{#device-graph-options}

为[!UICONTROL Profile Merge]规则选择[!UICONTROL device graph]选项取决于数字属性和业务目标所特有的条件。 这些一般准则可以帮助您了解何时使用一种图形与另一种图形。 注意，您必须是[Adobe Experience Cloud设备合作社](https://docs.adobe.com/content/help/zh-Hans/device-co-op/using/home.html)的成员，或与外部设备图形具有合同关系才能使用这些选项。 有关何时选择设备图形选项的一般指导，请参阅下表。 有关特定用例，请参阅[用户档案链路设备图使用案例](profile-link-use-case.md)和[外部设备图使用案例](external-graph-use-cases.md)。

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设备图形类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 用户档案链接设备图</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 用户档案</span> 使用用户档案链接 <span class="wintitle"> 选</span> 项构建的Mergerules非常适合： </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">具有高级客户身份验证的数字属性。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">专注、触及范围小的活动。 <span class="wintitle">用户档案链接</span>设备图形仅基于确定性数据构建。 相对于未验证的用户和设备池，此设备用户档案池始终会更小。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">在客户需要处于已验证状态才能获得分段资格的情况下使用。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部设备图形选项 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 用户档案</span> Mergerules使用 <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud设备协作</a> 或任何与受众管理器集成的外 <span class="keyword"> 部设</span> 备图形，是以下产品的理想选择： </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">具有低级客户身份验证的数字属性。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">广泛、触及面广的品牌活动。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">在客户无需处于已验证状态即可获得分段资格的情况下使用。 </li> 
     </ul> </p> <p> <p>提示：如果您是<span class="keyword">Experience Cloud</span>客户，且身份验证低且与任何设备图形提供商没有关系，则<span class="keyword">设备合作社</span>是最佳选择。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

观看以下视频，了解[!UICONTROL Profile Merge Rules]的可能使用案例。

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [配置文件关联设备图用例](profile-link-use-case.md)
>* [外部设备图用例](external-graph-use-cases.md)
>* [用户档案合并规则常见问题解答](../../faq/faq-profile-merge.md)

