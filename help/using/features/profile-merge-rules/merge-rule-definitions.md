---
description: 合并规则选项允许您控制Audience Manager用于分段的数据类型。 合并规则可以包括由配置文件链接设备图和/或与Audience Manager集成的其他第三方设备图提供商映射的设备配置文件。 您最多可以创建4个配置文件合并规则。
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: 定义的配置文件合并规则选项
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 1%

---

# 已定义[!UICONTROL Profile Merge Rules]选项 {#profile-merge-rule-options-defined}

[!UICONTROL profile merge rule]选项允许您控制[!DNL Audience Manager]用于分段的数据类型。 [!UICONTROL profile merge rule]可以包含由[!UICONTROL Profile Link]设备图形和/或与[!DNL Audience Manager]集成的其他第三方设备图形提供商映射的设备配置文件。 您最多可以创建4个[!UICONTROL Profile Merge Rules]。 第四个[!UICONTROL Profile Merge Rule]仅供购买[!UICONTROL People-Based Destinations]加载项的客户使用。

您通过在[!UICONTROL Profile Merge Rule Setup]中从下述选项中进行选择来构建[!UICONTROL Profile Merge Rule]。

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule]选项概述 {#overview}

[!UICONTROL Profile Merge Rules]允许使用许多规则组合，每个规则组合都适用于特定用例。 有关何时使用每个规则组合的详细信息，请参阅下表。

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | 可用性 | 评估类型 | [!UICONTROL Audience Lab]支持 | 用例 |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | 所有客户 | 实时和批量 | 是 | [设备定位](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | 所有客户 | 实时和批量 | 否 | [扩展的设备定位](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | 所有客户 | 仅实时 | 否 | [共享设备定位](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | 所有客户 | 实时和批量 | 是 | [在线/离线定位](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | 所有客户 | 实时和批量 | 是 | [跨设备定位](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | 所有客户 | 实时和批量 | 否 | [高级跨设备定位](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | 不适用 | 专属于[基于人员的目标](../destinations/people-based-destinations-overview.md)客户 | 仅批次 | 否 | [基于人员的目标定位](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment]评估 {#segment-evaluation}

根据您的[!UICONTROL Profile Merge Rules]配置，[!DNL Audience Manager]可以实时、批量或同时执行这两项评估。[!UICONTROL segment]

* 实时[!UICONTROL segment]评估需要[!DNL DCS]才能看到访客实时访问您的数字资产，从而符合[!UICONTROL segment]的条件。
* 对先前限定的[!UICONTROL traits]执行批次[!UICONTROL segment]评估。
* 同时支持实时和批次[!UICONTROL segment]评估的[!UICONTROL Profile Merge Rules]将实时访客活动与以前限定的[!UICONTROL traits]相结合。

## [!UICONTROL Profile Merge Rules]报告延迟 {#reporting-latency}

实时[!UICONTROL segment]评估立即反映在[!UICONTROL Profile Merge Rules]报表中。

批次[!UICONTROL segment]评估可能需要24小时才能反映在[配置文件合并规则报表](profile-link-metrics.md)中。

## [!UICONTROL Cross-Device Options] {#auth-options}

[!UICONTROL Cross-Device Options]允许您选择经过身份验证和未经身份验证的用户，并利用其跨设备配置文件进行分段。 这些选项可帮助您识别并联系共享设备上的特定用户。 有关匿名和经过身份验证的用户的详细信息，请参阅Audience Manager[&#128279;](../../reference/visitor-authentication-states.md)中的访客身份验证状态。

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 跨设备选项 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">没有跨设备配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>不使用从经过身份验证的用户收集的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">个当前已验证的配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>在访客已登录您的网站时读取和写入经过身份验证的配置文件中的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">上次验证的用户档案</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>从上次登录设备的用户的已验证配置文件中读取数据。 </p> <p>选中后，如果Audience Manager是匿名用户，<span class="keyword">用户</span>不会将新特征数据写入已验证的配置文件。 身份验证后，新特征数据将写入用户经过身份验证的配置文件。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">所有跨设备配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>告知Audience Manager从所有跨设备配置文件中读取数据，而不考虑身份验证状态。 此选项仅适用于已购买People-Based Destinations插件的Audience Manager客户。</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

[!UICONTROL Cross-Device Profile Options]列出了您的[!UICONTROL cross-device data sources]。 这些选项使用您在创建[!UICONTROL cross-device] [!UICONTROL data source]时提供的名称(请参阅[创建跨设备数据Source](merge-rules-start.md#create-data-source))。 您最多可以选择3个[!UICONTROL cross-device data sources]用于每个配置文件规则。 当您选择&#x200B;**[!UICONTROL Current Authenticated Profiles]**&#x200B;或&#x200B;**[!UICONTROL Last Authenticated Profiles]**&#x200B;时，[!UICONTROL Authenticated Profile Options]可用。

## [!UICONTROL Device Options] {#device-options}

[!UICONTROL Device Options]允许您选择[!UICONTROL Profile Merge Rule]使用的&#x200B;*`device profile`*&#x200B;类型。 设备配置文件是从匿名浏览活动收集的[!UICONTROL traits]生成的。 [!UICONTROL profile merge rule]至少包括[!UICONTROL authenticated option]和[!UICONTROL device option]。

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设备选项 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">无设备配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>不要使用匿名配置文件中包含的特征进行分段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">设备配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>使用匿名设备配置文件进行分段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">配置文件链接设备图</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>从当前设备和最多100个用户已从中进行身份验证的其他设备读取配置文件。 此设备图是根据<span class="keyword">Audience Manager</span>中您自己的第一方数据生成的。 它非常适合对其数字资产进行高级别身份验证的客户。 <span class="wintitle">配置文件链接</span>设备图已实时更新。 当您选择<b><span class="uicontrol">当前已验证的配置文件</span></b>或<b><span class="uicontrol">上次已验证的配置文件</span></b>时，此选项可用。 使用此选项时，您只能选择单个经过身份验证的配置文件(<span class="keyword">个Audience Manager</span>会自动将其余配置文件变灰)。 另请参阅<a href="profile-link-use-case.md">配置文件链接设备图用例</a>。 </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>第三方设备图选项</b>（人员和家庭） </p> </td>
   <td colname="col2"> <p>这些选项允许您根据第三方供应商提供的设备图技术构建合并规则。 第三方设备图提供： </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 概率和/或确定性数据。 </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">个人或家庭的数据。 </li> 
     </ul> </p> <p>要使用这些选项，您必须是设备图提供的已与<span class="keyword">Audience Manager</span>集成的设备客户。 请联系您的客户经理以了解更多信息或开始使用。 </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

根据在[!DNL Audience Manager]外部定义的合并规则从其他[!DNL Experience Cloud]解决方案自动创建的受众区段，将使用[!UICONTROL External Merge Policy]标记为使用。 例如，请参阅[Audience Manager与Adobe Experience Platform之间的受众共享](../../integration/integration-aep/aam-aep-audience-sharing.md)。

>[!MORELIKETHIS]
>
>* [配置文件合并规则常见问题解答](../../faq/faq-profile-merge.md)
