---
description: 通过合并规则选项，您可以控制Audience manager用于细分的数据类型。 合并规则可包括由Profile Link设备图形、Adobe Experience Cloud Device Co-op和／或与Audience manager集成的其他第三方设备图形提供商映射的设备配置文件。 最多可创建4个配置文件合并规则。
seo-description: 通过合并规则选项，您可以控制Audience manager用于细分的数据类型。 合并规则可包括由Profile Link设备图形、Adobe Experience Cloud Device Co-op和／或与Audience manager集成的其他第三方设备图形提供商映射的设备配置文件。 最多可创建4个配置文件合并规则。
seo-title: 已定义配置文件合并规则选项
solution: Audience Manager
title: 已定义配置文件合并规则选项
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: 532c69981ebc082bd411a9232e9ef207b59dace5

---


# Profile Merge Rules Options Defined {#profile-merge-rule-options-defined}

通过合并规则选项，您可以控制Audience manager用于细分的数据类型。 合并规则可以包括由设备图、和/ [!UICONTROL Profile Link] 或与Audience manager集成的其 [!UICONTROL Adobe Experience Cloud Device Co-op]他第三方设备图提供者映射的设备配置文件。 最多可创建4个 [!UICONTROL Profile Merge Rules]。 第四 [!UICONTROL Profile Merge Rule] 项仅适用于购买该加载项 [!UICONTROL People-Based Destinations] 的客户。

您可以通 [!UICONTROL Profile Merge Rule] 过在中的以下选项中进行选择来构建 [!UICONTROL Profile Merge Rule Setup]。

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Profile Merge Rule Options Overview {#overview}

配置文件合并规则允许多种规则组合，每种组合都适合特定用例。 有关何时使用每个规则组合的详细信息，请参阅下表。

| 跨设备选项 | 设备选项 | 可用性 | 评估类型 | Audience Lab支持 | 用例 |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| 无跨设备配置文件 | 设备配置文件 | 所有客户 | 实时和批量 | 是 | [设备定位](merge-rule-targeting-options.md#device-personalization) |
| 无跨设备配置文件 | 外部设备图（包括协作设备图） | 所有客户 | 实时和批量 | 否 | [扩展的设备定位](external-graph-use-cases.md#audience-expansion) |
| 当前已验证的配置文件 | 无设备配置文件 | 所有客户 | 仅实时 | 否 | [共享设备定位](merge-rule-targeting-options.md#target-shared-devices) |
| 上次验证的配置文件 | 设备配置文件 | 所有客户 | 实时和批量 | 是 | [联机／脱机定位](merge-rule-targeting-options.md#device-household-targeting) |
| 上次验证的配置文件 | 配置文件链接设备图 | 仅限北美和加拿大 | 实时和批量 | 是 | [跨设备定位](profile-link-use-case.md#cross-device-personalization) |
| 上次验证的配置文件 | 外部设备图（包括协作设备图） | 所有客户 | 实时和批量 | 否 | [高级跨设备定位](external-graph-use-cases.md#advanced-graph-expansion) |
|  所有跨设备配置文件 | 不适用 | 基于人 [员的目标客户独有](../destinations/people-based-destinations-overview.md) | 仅批处理 | 否 | [针对基于人员的目标进行定位](merge-rule-targeting-options.md#all-cross-device) |

## 配置文件合并规则区段评估 {#segment-evaluation}

根据您的 [!UICONTROL Profile Merge Rules] 配置，Audience manager可以实时、批量或同时执行区段评估。

* 实时细分评估要求访 [!DNL DCS] 客实时查看您的数字资产，以符合细分资格。
* 批区段评估是针对以前合格的特征执行的。
* [!UICONTROL Profile Merge Rules] 同时支持实时和批量细分评估的功能将实时访客活动与先前的合格特征相结合。

## 配置文件合并规则报告延迟 {#reporting-latency}

实时细分评估会立即反映在报告 [!UICONTROL Profile Merge Rules] 中。

批细分评估最多可能需要24小时才能反映在“配置文件合并规 [则”报表中](profile-link-metrics.md)。

## 跨设备选项 {#auth-options}

您可 [!UICONTROL Cross-Device Options] 以选择已验证和未验证的用户，并利用其跨设备配置文件进行细分。 这些选项可帮助您识别和接触共享设备上的特定用户。 有关匿名用户和已验证用户的详细信息，请参 [阅Audience manager中的访客身份验证状态](../../reference/visitor-authentication-states.md)。

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
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> 不要使用从经过身份验证的用户收集的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 当前已验证的配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> ，如果访客已登录您的站点，则可以读取数据并将数据写入已验证的配置文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 上次验证的配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> ，从上次登录设备的用户的已验证配置文件中读取数据。 </p> <p>选择后， <span class="keyword"> 如果用户为匿名用户</span> ，则Audience Manager不会将新特征数据写入已验证的配置文件。 身份验证后，新特征数据将写入用户的已验证配置文件。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 所有跨设备配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>告知Audience manager从所有跨设备配置文件中读取数据，而不管身份验证状态如何。 此选项仅适用于已购买基于人员的目标加载项的Audience manager客户。</p> </td>
  </tr>
 </tbody>
</table>

## 跨设备配置文件选项 {#profile-options}

列 [!UICONTROL Cross-Device Profile Options] 出跨设备数据源。 这些选项使用您在创建跨设备数据源时提供的名称(请参 [阅创建跨设备数据源](merge-rules-start.md#create-data-source))。 您最多可以选择3个跨设备数据源，以便与每个配置文件规则一起使用。 当您 [!UICONTROL Authenticated Profile Options] 选择或时，可以使用 **[!UICONTROL Current Authenticated Profiles]** 它 **[!UICONTROL Last Authenticated Profiles]**。

## 设备选项 {#device-options}

您 [!UICONTROL Device Options] 可以选择用 *`device profile`* 于的类型 [!UICONTROL Profile Merge Rule]。 设备配置文件是根据从匿名浏览活动收集的特征构建的。 配置文件合并规则至少包括经过身份验证的选项和设备选项。

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
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> ，不要将匿名配置文件中包含的特征用于细分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 设备配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> ，使用匿名设备配置文件进行细分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 配置文件链接设备图</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> Audience Manager</span> 从当前设备和最多100台用户已通过身份验证的其他设备中读取配置文件。 此设备图表基于 <span class="keyword"> Audience manager中您自己的第一方数据构建</span>。 它是跨数字资产进行高级别身份验证的客户的理想选择。 Profile <span class="wintitle"> Link</span> device graph is real time updated. 当您选择“当前已验证配置文件”或“上 <b><span class="uicontrol"> 次已验证配置文件</span></b> ”时， <b><span class="uicontrol"> 此选项可用</span></b>。 使用此选项时，您只能选择单个经过身份验证的配置文件(<span class="keyword"> Audience Manager</span> 会自动灰化其他配置文件)。 另请参阅配置 <a href="profile-link-use-case.md"> 文件链接设备图形使用案例</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 协作设备图</span></b> </p> </td> 
   <td colname="col2"> <p>通 <span class="keyword"> 知Audience Manager</span> ，使用 <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op提供的链接从当前设备和多达100台其他设备读取配置文件</a>。 </p> <p><span class="keyword"> 设备协作</span>是一项数字协作服务，可让参与的客户共享设备链接信息。设 <span class="keyword"> 备协作在设备图</span> 中处理此 <span class="term"> 数据</span>。 设备图形将设备从设备群集连接在一起。 这些链接是根据概率和确 <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> 定性数据构建的</a>。 这些群集代表由未知人使用的一组设备。 <span class="keyword">设备协作</span>会在其成员之间共享这些群集，从而帮助成员向其客户提供富有价值的、一致的跨设备体验。 </p> <p> 有关设备协作的 <span class="wintitle"> 详细信息</span>，请参阅： </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> 设备合作概述</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> 成员资格要求</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> 设备图：内部流程和输出</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience manager和外部设备图</a> （PDF下载）。 </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>第三方设备图表选项</b> （个人和家庭） </p> </td>
   <td colname="col2"> <p>这些选项允许您根据第三方供应商提供的设备图技术构建合并规则。 第三方设备图形提供： </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 概率和／或确定性数据。 </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">个人或家庭级别的数据。 </li> 
     </ul> </p> <p>要使用这些选项，您必须是已与 <span class="keyword"> Audience Manager集成的设备图形提供者的客户</span>。 请联系您的客户经理以了解更多信息或开始。 </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_LIKE_THIS]
>
>* [个人资料合并规则常见问题解答](../../faq/faq-profile-merge.md)

