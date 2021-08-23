---
description: 利用合并规则选项，可控制Audience Manager用于分段的数据类型。 合并规则可以包括由配置文件链接设备图、Adobe Experience Cloud设备协作和/或与Audience Manager集成的其他第三方设备图提供商映射的设备配置文件。 最多可创建4个配置文件合并规则。
seo-description: 利用合并规则选项，可控制Audience Manager用于分段的数据类型。 合并规则可以包括由配置文件链接设备图、Adobe Experience Cloud设备协作和/或与Audience Manager集成的其他第三方设备图提供商映射的设备配置文件。 最多可创建4个配置文件合并规则。
seo-title: 定义的配置文件合并规则选项
solution: Audience Manager
title: 定义的配置文件合并规则选项
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: 配置文件合并
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 6%

---

# [!UICONTROL Profile Merge Rules] 定义的选项 {#profile-merge-rule-options-defined}

通过[!UICONTROL profile merge rule]选项，您可以控制[!DNL Audience Manager]用于分段的数据类型。 [!UICONTROL profile merge rule]可以包含由与[!DNL Audience Manager]集成的[!UICONTROL Profile Link]设备图、[!UICONTROL Adobe Experience Cloud Device Co-op]和/或其他第三方设备图提供程序映射的设备配置文件。 最多可创建4个[!UICONTROL Profile Merge Rules]。 第四个[!UICONTROL Profile Merge Rule]仅供购买[!UICONTROL People-Based Destinations]加载项的客户使用。

通过从[!UICONTROL Profile Merge Rule Setup]中的以下选项中进行选择来构建[!UICONTROL Profile Merge Rule]。

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] 选项概述 {#overview}

[!UICONTROL Profile Merge Rules] 允许使用多种规则组合，每种组合适用于特定用例。有关何时使用每个规则组合的详细信息，请参阅下表。

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | 可用性 | 评估类型 | [!UICONTROL Audience Lab] 支持 | 用例 |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | 所有客户 | 实时和批量处理 | 是 | [设备定位](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (包括 [!UICONTROL Co-op Device Graph]) | 所有客户 | 实时和批量处理 | 否 | [扩展的设备定位](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | 所有客户 | 仅实时 | 否 | [共享设备定位](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | 所有客户 | 实时和批量处理 | 是 | [在线/离线定位](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | 所有客户 | 实时和批量处理 | 是 | [跨设备定位](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (包括 [!UICONTROL Co-op Device Graph]) | 所有客户 | 实时和批量处理 | 否 | [高级跨设备定位](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | 不适用 | 仅适用于[基于人员的目标](../destinations/people-based-destinations-overview.md)客户 | 仅批 | 否 | [针对基于人员的目标进行定位](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] 评估 {#segment-evaluation}

根据您的[!UICONTROL Profile Merge Rules]配置，[!DNL Audience Manager]可以实时、批量或同时执行[!UICONTROL segment]评估。

* 实时[!UICONTROL segment]评估要求[!DNL DCS]查看访客实时访问您的数字资产，以符合[!UICONTROL segment]的条件。
* 对先前限定的[!UICONTROL traits]执行批次评估。[!UICONTROL segment]
* [!UICONTROL Profile Merge Rules] 支持实时和批量评估 [!UICONTROL segment] 的功能，可将实时访客活动与之前获得资格的活动结合 [!UICONTROL traits]使用。

## [!UICONTROL Profile Merge Rules] 报告延迟 {#reporting-latency}

实时[!UICONTROL segment]评估会立即反映在[!UICONTROL Profile Merge Rules]报表中。

批量[!UICONTROL segment]评估最多可能需要24小时才能反映在[配置文件合并规则报表](profile-link-metrics.md)中。

## [!UICONTROL Cross-Device Options] {#auth-options}

通过[!UICONTROL Cross-Device Options]，您可以选择已验证和未验证的用户，并利用其跨设备配置文件进行分段。 这些选项可帮助您识别和联系共享设备上的特定用户。 有关匿名用户和已通过身份验证的用户的更多信息，请参阅Audience Manager](../../reference/visitor-authentication-states.md)中的[访客身份验证状态。

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 跨设备选项 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 无跨设备配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>不要使用从经过身份验证的用户收集的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 当前已验证的配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>在访客已登录您的网站时，将数据读取并写入已验证的配置文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 上次验证的用户档案</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>从上次登录设备的用户的经过验证的配置文件中读取数据。 </p> <p>选择<span class="keyword">Audience Manager</span>后，如果用户是匿名的，则该用户将不会向经过身份验证的配置文件写入新的特征数据。 验证后，新特征数据将写入用户经过验证的配置文件中。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 所有跨设备配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>告知Audience Manager从所有跨设备配置文件读取数据，而不考虑身份验证状态。 此选项仅适用于已购买基于人员的目标加载项的Audience Manager客户。</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

[!UICONTROL Cross-Device Profile Options]会列出您的[!UICONTROL cross-device data sources]。 这些选项使用您在创建[!UICONTROL cross-device] [!UICONTROL data source]时提供的名称（请参阅[创建跨设备数据源](merge-rules-start.md#create-data-source)）。 最多可以选择3个[!UICONTROL cross-device data sources]用于每个配置文件规则。 选择&#x200B;**[!UICONTROL Current Authenticated Profiles]**&#x200B;或&#x200B;**[!UICONTROL Last Authenticated Profiles]**&#x200B;时，[!UICONTROL Authenticated Profile Options]将可用。

## [!UICONTROL Device Options] {#device-options}

使用[!UICONTROL Device Options]可选择[!UICONTROL Profile Merge Rule]使用的&#x200B;*`device profile`*&#x200B;类型。 设备配置文件是根据从匿名浏览活动收集的[!UICONTROL traits]构建的。 [!UICONTROL profile merge rule]至少包括[!UICONTROL authenticated option]和[!UICONTROL device option]。

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设备选项 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 无设备配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>不要使用匿名配置文件中包含的特征进行分段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 设备配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>使用匿名设备配置文件进行分段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 配置文件链接设备图</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>从当前设备和用户已从中进行身份验证的最多100个其他设备中读取配置文件。 此设备图基于您自己的<span class="keyword">Audience Manager</span>中的第一方数据构建。 它非常适合那些在其数字资产中进行高级别身份验证的客户。 <span class="wintitle">配置文件链接</span>设备图会实时更新。 当您选择<b><span class="uicontrol">当前已验证配置文件</span></b>或<b><span class="uicontrol">上次已验证配置文件</span></b>时，此选项将可用。 使用此选项时，您只能选择单个经过身份验证的配置文件(<span class="keyword">Audience Manager</span>会自动将其他配置文件灰显)。 另请参阅<a href="profile-link-use-case.md">配置文件链接设备图用例</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 协作设备图</span></b> </p> </td> 
   <td colname="col2"> <p>告知<span class="keyword">Audience Manager</span>使用<a href="https://experienceleague.adobe.com/docs/device-co-op/using/about/overview.html" format="https" scope="external">Experience Cloud设备协作</a>提供的链接从当前设备和多达100个其他设备读取配置文件。 </p> <p><span class="keyword"> 设备协作</span>是一项数字协作服务，可让参与的客户共享设备链接信息。<span class="keyword">设备协作</span>在<span class="term">设备图</span>中处理此数据。 设备图将设备链接在一起，形成设备群集。 这些链接是根据<a href="https://experienceleague.adobe.com/docs/device-co-op/using/device-graph/links.html" format="https" scope="external">概率数据和确定性数据</a>构建的。 群集表示未知人员使用的一组设备。 <span class="keyword">设备协作</span>会在其成员之间共享这些群集，从而帮助成员向其客户提供富有价值的、一致的跨设备体验。 </p> <p> 有关<span class="wintitle">设备协作</span>的更多信息，请参阅： </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://experienceleague.adobe.com/docs/device-co-op/using/home.html" format="https" scope="external"> 设备协作概述</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://experienceleague.adobe.com/docs/device-co-op/using/about/requirements.html" format="https" scope="external"> 成员资格要求</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://experienceleague.adobe.com/docs/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> 设备图：内部流程和输出</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>第三方设备图选项</b> （人员和家庭） </p> </td>
   <td colname="col2"> <p>这些选项允许您根据第三方供应商提供的设备图技术构建合并规则。 第三方设备图提供： </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 概率和/或确定性数据。 </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">个人或家庭级别的数据。 </li> 
     </ul> </p> <p>要使用这些选项，您必须是已与<span class="keyword">Audience Manager</span>集成的设备图提供者的客户。 请联系您的客户经理以了解更多信息或开始使用。 </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

根据在[!DNL Audience Manager]之外定义的合并规则，从其他[!DNL Experience Cloud]解决方案自动创建的受众区段将标记为使用[!UICONTROL External Merge Policy]。 例如，请参阅[Audience Manager与Adobe Experience Platform之间的受众共享](../../integration/integration-aep/aam-aep-audience-sharing.md)。

>[!MORELIKETHIS]
>
>* [配置文件合并规则常见问题解答](../../faq/faq-profile-merge.md)

