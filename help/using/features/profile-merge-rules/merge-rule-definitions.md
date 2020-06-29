---
description: 合并规则选项允许您控制Audience Manager用于分段的数据类型。 合并规则可包括由用户档案链接设备图形、Adobe Experience Cloud Device Co-op和／或与Audience Manager集成的其他第三方设备图形提供商映射的设备用户档案。 最多可创建4个用户档案合并规则。
seo-description: 合并规则选项允许您控制Audience Manager用于分段的数据类型。 合并规则可包括由用户档案链接设备图形、Adobe Experience Cloud Device Co-op和／或与Audience Manager集成的其他第三方设备图形提供商映射的设备用户档案。 最多可创建4个用户档案合并规则。
seo-title: 定义的配置文件合并规则选项
solution: Audience Manager
title: 定义的配置文件合并规则选项
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 6%

---


# [!UICONTROL Profile Merge Rules] 已定义选项 {#profile-merge-rule-options-defined}

The [!UICONTROL profile merge rule] options let you control the type of data [!DNL Audience Manager] uses for segmentation. 一种 [!UICONTROL profile merge rule] 可以包括由设备图 [!UICONTROL Profile Link] 形、和／或与 [!UICONTROL Adobe Experience Cloud Device Co-op]集成的其他第三方设备图形提供者映射的设备用户档案 [!DNL Audience Manager]。 You can create a maximum of 4 [!UICONTROL Profile Merge Rules]. 第四 [!UICONTROL Profile Merge Rule] 项仅适用于购买该加载项 [!UICONTROL People-Based Destinations] 的客户。

通过从 [!UICONTROL Profile Merge Rule] 中描述的选项进行选择来构建 [!UICONTROL Profile Merge Rule Setup]。

![用户档案合并规则设置](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] 选项概述 {#overview}

[!UICONTROL Profile Merge Rules] 允许多种规则组合，每种组合都适合特定用例。 有关何时使用每个规则组合的详细信息，请参阅下表。

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | 可用性 | 评估类型 | [!UICONTROL Audience Lab] 支持 | 用例 |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | 所有客户 | 实时和批处理 | 是 | [设备定位](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (包括 [!UICONTROL Co-op Device Graph]) | 所有客户 | 实时和批处理 | 否 | [扩展的设备定位](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | 所有客户 | 仅实时 | 否 | [共享设备定位](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | 所有客户 | 实时和批处理 | 是 | [联机／脱机定位](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | 所有客户 | 实时和批处理 | 是 | [跨设备定位](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (包括 [!UICONTROL Co-op Device Graph]) | 所有客户 | 实时和批处理 | 否 | [高级跨设备定位](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | 不适用 | 基于人 [员的目的地客户独享](../destinations/people-based-destinations-overview.md) | 仅批 | 否 | [针对基于人的目标进行定位](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] 评估 {#segment-evaluation}

根据您 [!UICONTROL Profile Merge Rules] 的配 [!DNL Audience Manager] 置，可以 [!UICONTROL segment] 实时、批量或同时执行评估。

* 实时评 [!UICONTROL segment] 估要求 [!DNL DCS] 访客实时查看您的数字资产，以获得相应资格 [!UICONTROL segment]。
* 对以 [!UICONTROL segment] 前的合格执行批评估 [!UICONTROL traits]。
* [!UICONTROL Profile Merge Rules] 支持实时和批量评估的工具 [!UICONTROL segment] ，将实时访客活动与先前的合格内容相结合 [!UICONTROL traits]。

## [!UICONTROL Profile Merge Rules] 报告延迟 {#reporting-latency}

实时评 [!UICONTROL segment] 价立即反映在报 [!UICONTROL Profile Merge Rules] 告中。

批评 [!UICONTROL segment] 可能需要24小时才能反映在“用户档案合 [并规则”报告中](profile-link-metrics.md)。

## [!UICONTROL Cross-Device Options] {#auth-options}

您可 [!UICONTROL Cross-Device Options] 以选择已验证和未验证的用户，并利用其跨设备用户档案进行细分。 这些选项可帮助您识别并触及共享设备上的特定用户。 有关匿名和已验证用户的详细信息，请参阅 [访客身份验证状态Audience Manager](../../reference/visitor-authentication-states.md)。

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 跨设备选项 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 无跨设备用户档案</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> ，不要使用从经过身份验证的用户收集的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 当前已验证的用户档案</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> ，如果访客已登录您的站点，则向已验证的用户档案读取数据并将其写入。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 上次验证用户档案</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> ，从上次登录设备的用户的已验证用户档案读取数据。 </p> <p>选中后， <span class="keyword"> Audience Manager</span> 将不会向已验证用户档案写入新特征数据（如果用户为匿名数据）。 验证后，新特征数据将写入用户的已验证用户档案。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 所有跨设备用户档案</span></b> </p> </td> 
   <td colname="col2"> <p>告知Audience Manager从所有跨设备用户档案读取数据，而不管身份验证状态如何。 此选项仅适用于已购买“基于人员的目标”加载项的Audience Manager客户。</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

列表 [!UICONTROL Cross-Device Profile Options] 您的 [!UICONTROL cross-device data sources]。 这些选项使用您在创建时提供的 [!UICONTROL cross-device] 名 [!UICONTROL data source] 称( [请参阅创建跨设备数据源](merge-rules-start.md#create-data-source))。 您最多可以选择3个 [!UICONTROL cross-device data sources] 与每个用户档案规则一起使用。 当您 [!UICONTROL Authenticated Profile Options] 选择或时，可 **[!UICONTROL Current Authenticated Profiles]** 以使用 **[!UICONTROL Last Authenticated Profiles]**。

## [!UICONTROL Device Options] {#device-options}

您 [!UICONTROL Device Options] 可以选择用 *`device profile`* 户的类型 [!UICONTROL Profile Merge Rule]。 设备用户档案是从匿名浏览 [!UICONTROL traits] 活动收集的。 至少包括 [!UICONTROL profile merge rule] 一个 [!UICONTROL authenticated option] 和一个 [!UICONTROL device option]。

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设备选项 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 无设备用户档案</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> ，不要使用匿名用户档案中包含的特征进行细分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 设备用户档案</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> ，使用匿名设备用户档案进行细分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 用户档案链接设备图</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> ，从当前设备以及用户已通过身份验证的最多100个其他设备中读取用户档案。 此设备图表基于您自己的第一方Audience Manager <span class="keyword"> 构建</span>。 它非常适合那些在数字资产中具有高级身份验证的客户。 用户档案 <span class="wintitle"> 链接</span> 设备图形会实时更新。 当您选择“当前已验证用户档案” <b><span class="uicontrol"> 或“上次已验证用户档案</span></b> ”时 <b><span class="uicontrol"> ，此选项可用</span></b>。 使用此选项时，您只能选择单个已验证的用户档案(<span class="keyword"> Audience Manager</span> 会自动灰显其他用户)。 See also, <a href="profile-link-use-case.md"> Profile Link Device Graph Use Cases</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 协作设备图</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> ，使用“Experience Cloud设备协作”提供的链接从当前设备和多达100个其他设备 <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> 读取用户档案</a>。 </p> <p><span class="keyword"> 设备协作</span>是一项数字协作服务，可让参与的客户共享设备链接信息。设备 <span class="keyword"> 合作社在设备图</span> 中处理此 <span class="term"> 数据</span>。 设备图形将设备连接在一起，形成设备群集。 这些链接是根据概率 <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> 和确定性数据构建的</a>。 这些群集代表由未知人使用的一组设备。 <span class="keyword">设备协作</span>会在其成员之间共享这些群集，从而帮助成员向其客户提供富有价值的、一致的跨设备体验。 </p> <p> 有关设备协 <span class="wintitle"> 作的详细信息</span>，请参阅： </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/zh-Hans/device-co-op/using/home.html" format="https" scope="external"> 设备合作社概述</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> 成员资格要求</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> 设备图： 内部流程和输出</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>第三方设备图选项</b> （人员和家庭） </p> </td>
   <td colname="col2"> <p>这些选项允许您根据第三方供应商提供的设备图技术构建合并规则。 第三方设备图表提供： </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 概率和／或确定性数据。 </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">个人或家庭级别的数据。 </li> 
     </ul> </p> <p>要使用这些选项，您必须是已与Audience Manager集成的设备图提供者的客 <span class="keyword"> 户</span>。 请联系您的客户经理以了解更多信息或开始。 </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

根据外部定义的合并规 [!DNL Experience Cloud] 则，从其他解决方案自动创建的受众 [!DNL Audience Manager]段被标记为使用 [!UICONTROL External Merge Policy]。 For example, see [Audience Sharing Between Audience Manager and Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [用户档案合并规则常见问题解答](../../faq/faq-profile-merge.md)

