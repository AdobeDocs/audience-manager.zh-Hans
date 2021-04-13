---
description: 用户档案合并规则选项允许您根据业务需求或目标扩展或加强受众对特定受众的关注。 这些一般用例探讨如何使用可用选项并为个人、家庭和跨设备定位创建合并规则。
seo-description: 用户档案合并规则选项允许您根据业务需求或目标扩展或加强受众对特定受众的关注。 这些一般用例探讨如何使用可用选项并为个人、家庭和跨设备定位创建合并规则。
seo-title: 配置文件合并规则的一般用例
solution: Audience Manager
title: 配置文件合并规则的一般用例
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: 用户档案合并
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 4%

---

# 配置文件合并规则的一般用例 {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 通过各种选项，您可以根据业务需要或目标扩展或收紧受众，专注于特定受众。这些一般用例探讨如何使用可用选项并为个人、家庭和跨设备定位创建合并规则。 [!UICONTROL Profile Merge Rules] 使用实时和批处理目标。

>[!TIP]
>
>有关这些[!UICONTROL Merge Rule]设置的定义和说明，请参阅[定义的用户档案合并规则选项](merge-rule-definitions.md)。

## 设备定位{#device-personalization}

此方案适用于希望评估在Audience Manager中定义的受众区段的单个设备用户档案的营销人员，以便使用支持设备ID(DSP、在线个性化平台和其他基于设备的定位平台)的定位平台（不考虑用户身份验证）为设备提供一致的体验。

要创建仅目标设备用户档案的规则，请选择&#x200B;**[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**。

![仅限设备](assets/device-only.png)

假设约翰拥有三部智能手机。 其中两款是Data Plan A上的iPhone 7，其中一款是Data Plan B上的三星。John的移动运营商不考虑他在三台设备中任何一台上的已验证状态，而是希望为他优惠数据计划升级，但只针对在数据计划A上运行的iPhone 7设备。

通过使用&#x200B;**[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**&#x200B;规则，[!DNL Device 1]和[!DNL Device 3]都符合区段要求，而设备2则被忽略。

![仅限设备](assets/device-management.png)

## 共享设备定位{#target-shared-devices}

假设约翰和他的妻子简，使用同一台笔记本电脑访问网上商店并订购各种商品。

约翰用自己的账户来订票和特别优惠，而简则用自己的账户来买音乐和电影。

该商店的营销团队可以使用&#x200B;**[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]**&#x200B;规则，仅根据其经过身份验证的活动来目标John和Jane进行特定交易。

![当前 — 无设备](assets/current-no-device.png)

通过使用此规则，Audience Manager将完全忽略设备用户档案、区段的John的CRM ID资格，而不会确认Jane的CRM ID。

![共享设备定位](assets/shared-device-targeting.png)

## 联机/脱机定位{#device-household-targeting}

此用例涵盖家庭身份管理。 公司可以使用&#x200B;**[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]**&#x200B;规则将单个设备用户档案与在该设备上验证的最后一个用户档案合并。

![最后一个设备用户档案](assets/last-device-profile.png)

让我们考虑一个由收入超过100.000美元/年的家庭组成的细分，其中至少包含一个设备，该设备在[!DNL Data Plan B]上为[!DNL iPhone 7]。 我们有两个家庭用户档案(跨设备用户档案)，每个都连接到两个不同的设备用户档案。 符合区段条件所需的特征分布在设备和跨设备用户档案。

Audience Manager会合并每个设备+跨设备用户档案对，以查看合并的一组特征是否符合区段的条件。 由于Audience Manager对合并中包括的每个用户档案进行评估，因此设备用户档案和家庭用户档案都可以被分段。

设备与家庭用户档案之间的链接使Audience Manager能够确定[!DNL Household 2]是段，但不能确定[!DNL Household 1]。 从[!DNL Household 2]中，只有[!DNL Device 3]符合区段资格。 此[!UICONTROL Profile Merge Rule]使营销人员能够向单个设备([!DNL Device 3])和更广的家庭([!DNL Household 2])提供一致的营销信息。

![家庭管理](assets/household-management.png)

## 针对基于人员的目标{#all-cross-device}定位

>[!IMPORTANT]
>
>本文包含旨在指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都是法律建议。 请咨询您自己的法律顾问以获得法律指导。

此定位方案仅适用于已购买[!DNL People-Based Destinations]加载项的客户。 此规则允许营销人员根据客户自己的经过身份验证的数据触及客户。

假设一家在线零售商希望通过社交平台接触现有客户，并根据先前的订单向他们展示个性化的优惠。 借助[!UICONTROL People-Based Destinations]，他们可以将自己的[!DNL CRM]哈希电子邮件地址收录到Audience Manager中，从离线数据构建区段，并将这些区段发送到他们想要投放的社交平台，使用该哈希标识符优化广告支出。

要进一步了解此选项，请参阅[基于人员的目标](../destinations/people-based-destinations-overview.md)。

![跨设备](assets/all-cross-device.png)

## 设备图选项{#device-graph-options}

为[!UICONTROL Profile Merge]规则选择[!UICONTROL device graph]选项取决于您的数字属性和业务目标所特有的条件。 这些一般准则可以帮助您了解何时使用一种图形与另一种图形。 注意，您必须是[Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/zh-Hans/device-co-op/using/home.html)的成员，或与外部设备图形具有合同关系才能使用这些选项。 有关何时选择设备图表选项的一般指导，请参阅下表。 有关特定用例，请参阅[用户档案链接设备图表用例](profile-link-use-case.md)和[外部设备图表用例](external-graph-use-cases.md)。

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设备图表类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 用户档案链接设备图</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 用户档案 </span> Mergerules是使用用户档案 <span class="wintitle"> 链</span> 接选项构建的理想之选： </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">具有高级客户身份验证的数字资产。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">专注、触及面低的活动。 <span class="wintitle">用户档案链接</span>设备图形仅基于确定性数据。 相对于未经过身份验证的用户和设备池，此设备用户档案池始终会更小。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">客户需要处于已验证状态才能获得分段资格的用例。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部设备图表选项 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 用户档案 </span> Mergerules是使用 <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-</a> opor任何与受众 Manager集成的外部设 <span class="keyword"> 备图</span> 形的理想之选： </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">具有低级客户身份验证的数字属性。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">广泛、触及面广的品牌活动。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">客户无需处于已验证状态即可获得分段资格的用例。 </li> 
     </ul> </p> <p> <p>提示：如果您是<span class="keyword">Experience Cloud</span>客户，且与任何设备图形提供商没有关系，则<span class="keyword">设备协作</span>是最佳选择。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

观看以下视频，了解[!UICONTROL Profile Merge Rules]的可能使用案例的概述。

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [配置文件关联设备图用例](profile-link-use-case.md)
>* [外部设备图用例](external-graph-use-cases.md)
>* [用户档案合并规则常见问题解答](../../faq/faq-profile-merge.md)

