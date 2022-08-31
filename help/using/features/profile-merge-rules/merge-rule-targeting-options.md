---
description: 通过“配置文件合并规则”选项，您可以根据业务需求或目标，扩展或收紧对特定受众的关注。 这些一般用例探讨了如何使用可用选项，并为个人、家庭和跨设备定位创建合并规则。
seo-description: Profile Merge Rules options let you expand or tighten audience focus on specific audiences based on business needs or goals. These general use cases explore how to use available options and create merge rules for individual, household, and cross-device targeting.
seo-title: General Use Cases for Profile Merge Rules
solution: Audience Manager
title: 配置文件合并规则的一般用例
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 2%

---

# 配置文件合并规则的一般用例 {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 通过选项，您可以根据业务需求或目标，扩大或收紧对特定受众的关注。 这些一般用例探讨了如何使用可用选项，并为个人、家庭和跨设备定位创建合并规则。 [!UICONTROL Profile Merge Rules] 处理实时目标和批量目标。

>[!TIP]
>
>有关这些定义和描述 [!UICONTROL Merge Rule] 设置，请参阅 [定义的配置文件合并规则选项](merge-rule-definitions.md).

## 设备定位 {#device-personalization}

此方案适用于那些希望评估在Audience Manager中定义的受众区段的单个设备配置文件的营销人员，以便在没有考虑用户身份验证的情况下，使用支持设备ID的定位平台(DSP、网站个性化平台和其他基于设备的定位平台)为设备提供一致的体验。

要创建仅定向设备配置文件的规则，请选择 **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![仅限设备](assets/device-only.png)

比如说，John拥有三部智能手机。 其中两个是iPhone 7（在数据计划A中），其中一个是三星（在数据计划B中）。John的移动运营商不考虑他在三个设备中的任何一台上的身份验证状态，而是希望为他提供数据计划升级，但仅适用于在数据计划A中运行的iPhone 7设备。

通过使用 **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** 规则， [!DNL Device 1] 和 [!DNL Device 3] 二者均符合区段的资格条件，而设备2则被忽略。

![仅限设备](assets/device-management.png)

## 共享设备定位 {#target-shared-devices}

比如说，John和他的妻子Jane使用相同的笔记本电脑访问网上商店并订购各种商品。

John用自己的账户来预订旅行票和特价优惠，而Jane则用自己的账户来购买音乐和电影。

该商店的营销团队可以使用 **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** 规则，仅根据经过身份验证的活动来定位John和Jane的特定交易。

![当前无设备](assets/current-no-device.png)

通过使用此规则，Audience Manager会完全忽略设备配置文件、确定John的CRM ID符合区段的条件，以及不确定Jane的CRM ID。

![共享设备定位](assets/shared-device-targeting.png)

## 在线/离线定位 {#device-household-targeting}

此用例涵盖家庭身份管理。 公司可以使用 **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** 规则。

![last-device-profile](assets/last-device-profile.png)

让我们考虑一个由收入超过每年100,000美元的家庭组成的区段，该区段包含至少一个设备，该设备是 [!DNL iPhone 7] on [!DNL Data Plan B]. 我们有两个家庭配置文件（跨设备配置文件），每个配置文件都连接到两个不同的设备配置文件。 符合区段资格条件所需的特征在设备和跨设备配置文件之间进行分配。

Audience Manager可合并每个设备+跨设备配置文件对，以查看合并的特征集是否符合区段的条件。 由于Audience Manager会评估合并中包含的每个用户档案，因此设备用户档案和家庭用户档案都可以进行分段。

设备与家庭用户档案之间的链接允许Audience Manager符合条件 [!DNL Household 2] ，但不 [!DNL Household 1]. 从 [!DNL Household 2]仅 [!DNL Device 3] 符合区段资格。 此 [!UICONTROL Profile Merge Rule] 使营销人员能够向单个设备([!DNL Device 3])和更广大的家庭([!DNL Household 2])。

![家庭管理](assets/household-management.png)

## 针对基于人员的目标进行定位 {#all-cross-device}

>[!IMPORTANT]
>
>本文包含旨在指导您完成此功能的设置和使用的产品文档。 这里没有任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

此定位方案仅适用于已购买 [!DNL People-Based Destinations] 附加组件。 此规则允许营销人员根据客户自己的经过身份验证的数据来联系客户。

比如说，一家在线零售商希望通过社交平台联系现有客户，并根据其先前的订单向他们显示个性化优惠。 使用 [!UICONTROL People-Based Destinations]，他们可以从自己的地址中摄取经过哈希处理的电子邮件地址 [!DNL CRM] 进入Audience Manager，从离线数据构建区段，并使用经过哈希处理的标识符将这些区段发送到他们要广告的社交平台，从而优化其广告支出。

要了解有关此选项的更多信息，请参阅 [基于人员的目标](../destinations/people-based-destinations-overview.md).

![全跨设备](assets/all-cross-device.png)

## 设备图选项 {#device-graph-options}

选择 [!UICONTROL device graph] 选项 [!UICONTROL Profile Merge] 规则取决于您的数字资产和业务目标所特有的条件。 这些一般准则可帮助您了解何时使用一种类型的图形，何时使用另一种类型的图形。 请注意，您必须与外部设备图存在合同关系才能使用这些选项。 有关何时选择设备图选项的一般指导，请参阅下表。 有关特定用例，请参阅 [配置文件链接设备图用例](profile-link-use-case.md) 和 [外部设备图用例](external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设备图类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 配置文件链接设备图</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 配置文件合并</span> 使用 <span class="wintitle"> 配置文件链接</span> 选项非常适合： </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">具有高级客户身份验证的数字属性。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">重点突出、影响力小的营销活动。 的 <span class="wintitle"> 配置文件链接</span> 设备图仅基于确定性数据构建。 相对于未经身份验证的用户和设备池，此设备配置文件池将始终较小。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">客户需要处于已验证状态才能有资格进行分段的用例。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部设备图选项 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 配置文件合并</span> 通过与集成的任何外部设备图构建的规则 <span class="keyword"> Audience Manager</span> 非常适合： </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">具有低级别客户身份验证的数字属性。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">广泛、广泛的品牌宣传。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">客户无需处于已验证状态即可有资格进行分段的用例。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

请观看以下视频，了解 [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [配置文件关联设备图用例](profile-link-use-case.md)
>* [外部设备图用例](external-graph-use-cases.md)
>* [配置文件合并规则常见问题解答](../../faq/faq-profile-merge.md)

