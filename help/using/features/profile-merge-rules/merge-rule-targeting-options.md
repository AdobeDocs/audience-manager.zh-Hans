---
description: 用户档案合并规则选项允许您根据业务需求或目标扩大或收紧受众，专注于特定受众。 这些一般用例探讨如何使用可用选项并为单个、家庭和跨设备定位创建合并规则。
seo-description: 用户档案合并规则选项允许您根据业务需求或目标扩大或收紧受众，专注于特定受众。 这些一般用例探讨如何使用可用选项并为单个、家庭和跨设备定位创建合并规则。
seo-title: 用户档案合并规则的一般用例
solution: Audience Manager
title: 用户档案合并规则的一般用例
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# 用户档案合并规则的一般用例 {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 选项允许您根据业务需求或目标扩大或收紧受众，专注于特定受众。 这些一般用例探讨如何使用可用选项并为单个、家庭和跨设备定位创建合并规则。 [!UICONTROL Profile Merge Rules] 使用实时和批量目标。

>[!TIP]
>
>有关这些设置的定义和说 [!UICONTROL Merge Rule] 明，请参阅 [用户档案合并规则选项定义](merge-rule-definitions.md)。

## 设备定位 {#device-personalization}

此方案适用于希望对受众管理器中定义的受众细分评估单个设备用户档案的营销人员，以便使用支持设备ID（DSP、现场个性化平台和其他基于设备的定位平台）的定位平台向设备提供一致的体验，而不考虑用户身份验证。

要创建仅目标设备用户档案的规则，请选择 **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**。

![仅限设备](assets/device-only.png)

假设约翰拥有三部智能手机。 其中两款是iPhone 7，在Data Plan A上，其中一款是三星，在Data Plan B上。John的移动运营商不考虑他在三种设备上的已验证状态，而是希望为他优惠数据计划升级，但只针对在数据计划A上运行的iPhone 7设备。

通过使用 **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** 规则， [!DNL Device 1] 并且两者都符 [!DNL Device 3] 合区段的条件，而设备2将被忽略。

![仅限设备](assets/device-management.png)

## 共享设备定位 {#target-shared-devices}

假设约翰和他的妻子简，使用同一台笔记本电脑访问一家在线商店并订购各种商品。

约翰用自己的账户来预订旅行票和特价优惠，而简则用自己的账户来购买音乐和电影。

该商店的营销团队可以使用 **[!UICONTROL Current Authenticated Profiles]** +规 **[!UICONTROL No Device Profile]** 则目标John和Jane进行特定交易，这完全基于他们经过身份验证的活动。

![当前无设备](assets/current-no-device.png)

通过使用此规则，受众管理器将完全忽略设备用户档案、区段的John的CRM ID，而不符合Jane的CRM ID。

![共享设备定位](assets/shared-device-targeting.png)

## 联机／脱机定位 {#device-household-targeting}

此用例涵盖家庭身份管理。 公司可以将单个设备用户档案与在该设备上验证的最后一个用户档案合并，该使用 **[!UICONTROL Last Authenticated Profiles]** +规 **[!UICONTROL Device Profile]** 则。

![最后设备用户档案](assets/last-device-profile.png)

让我们来考虑一个由收入超过100.000美元／年的家庭组成的细分，其中至少包含一个设备上的 [!DNL iPhone 7] 设备 [!DNL Data Plan B]。 我们有两个家庭用户档案(跨设备用户档案)，每个都连接到两个不同的设备用户档案。 符合区段条件所需的特征分布在设备和跨设备用户档案中。

受众管理器会合并每台设备+跨设备用户档案对，以查看合并的特征集是否符合区段的条件。 由于受众管理器评估合并中包含的每个用户档案，因此设备用户档案和家庭用户档案都可以被分段。

设备与家庭用户档案之间的链接使受众经理能够有资 [!DNL Household 2] 格加入该细分，但不能 [!DNL Household 1]。 从 [!DNL Household 2]，只 [!DNL Device 3] 有区段资格。 这使 [!UICONTROL Profile Merge Rule] 营销人员能够向单个设备([!DNL Device 3])和更广泛的家庭()提供一致的营销信息[!DNL Household 2]。

![家庭管理](assets/household-management.png)

## 针对基于人员的目标进行定位 {#all-cross-device}

>[!IMPORTANT]
>
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

此定位方案仅适用于已购买该加载项 [!DNL People-Based Destinations] 的客户。 此规则允许营销人员根据自己的实名数据接触客户。

假设一家在线零售商希望通过社交平台接触现有客户，并根据先前的订单向他们展示个性化的优惠。 通过 [!UICONTROL People-Based Destinations][!DNL CRM] 它，他们可以将自己的哈希电子邮件地址收录到受众管理器中，根据离线数据构建细分，并将这些细分发送到他们要推广的社交平台，使用哈希标识符优化他们的广告支出。

要进一步了解此选项，请参 [阅基于人员的目标](../destinations/people-based-destinations-overview.md)。

![跨设备](assets/all-cross-device.png)

## 设备图形选项 {#device-graph-options}

选择规 [!UICONTROL device graph] 则的选项 [!UICONTROL Profile Merge] 取决于数字资产和业务目标所特有的条件。 这些一般准则可以帮助您了解何时使用一种图形与另一种图形。 请注意，您必须是 [Adobe Experience Cloud Device Co-op的成员](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) ，或与外部设备图形有合同关系才能使用这些选项。 有关何时选择设备图形选项的一般指导，请参阅下表。 有关特定用例，请参阅 [用户档案链接设备图形用例](profile-link-use-case.md) 和外 [部设备图形用例](external-graph-use-cases.md)。

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
   <td colname="col2"> <p><span class="wintitle"> 用户档案合并</span> (使用用户档案链接 <span class="wintitle"> )选项构建的规则</span> ，非常适合： </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">具有高级客户身份验证的数字资产。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">专注、触及面低的活动。 用户档案链 <span class="wintitle"> 接设备图</span> ，仅基于确定性数据构建。 相对于未验证的用户和设备池，此设备用户档案池始终会更小。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">客户需要处于身份验证状态才能获得分段资格的使用案例。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部设备图形选项 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 用户档案合并规则</span> (使用 <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op构建)或任何与</a> 受众管理器集成的外部设备图形 <span class="keyword"></span> ，非常适合： </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">具有低级客户身份验证的数字属性。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">广泛、触及面广的品牌活动。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">客户无需处于已验证状态即可获得分段资格的用例。 </li> 
     </ul> </p> <p> <p>提示：如果 <span class="keyword"></span><span class="keyword"></span> 您是Experience Cloud客户，且身份验证低，且与任何设备图形提供商没有关系，则Device Co-op是您的最佳选择。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

请观看以下视频，了解可能的使用案例的概述 [!UICONTROL Profile Merge Rules]。

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [用户档案链接设备图形使用案例](profile-link-use-case.md)
>* [外部设备图形使用案例](external-graph-use-cases.md)
>* [用户档案合并规则常见问题解答](../../faq/faq-profile-merge.md)

