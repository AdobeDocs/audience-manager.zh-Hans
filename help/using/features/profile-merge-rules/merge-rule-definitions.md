---
description: 合并规则选项允许您控制受众管理器用于分段的数据类型。 合并规则可包括由用户档案链接设备图形、Adobe Experience Cloud Device Co-op和／或与受众管理器集成的其他第三方设备图形提供商映射的设备用户档案。 最多可创建4个用户档案合并规则。
seo-description: 合并规则选项允许您控制受众管理器用于分段的数据类型。 合并规则可包括由用户档案链接设备图形、Adobe Experience Cloud Device Co-op和／或与受众管理器集成的其他第三方设备图形提供商映射的设备用户档案。 最多可创建4个用户档案合并规则。
seo-title: 用户档案合并规则选项已定义
solution: Audience Manager
title: 用户档案合并规则选项已定义
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Profile Merge Rules Options Defined {#profile-merge-rule-options-defined}

合并规则选项允许您控制受众管理器用于分段的数据类型。 合并规则可以包括由设备图、和/ [!UICONTROL Profile Link] 或与受众管理器集 [!UICONTROL Adobe Experience Cloud Device Co-op]成的其他第三方设备图提供者映射的设备用户档案。 最多可创建4个 [!UICONTROL Profile Merge Rules]。 第四 [!UICONTROL Profile Merge Rule] 项仅适用于购买该加载项 [!UICONTROL People-Based Destinations] 的客户。

通过从 [!UICONTROL Profile Merge Rule] 中描述的选项进行选择来构建 [!UICONTROL Profile Merge Rule Setup]。

![用户档案合并规则设置](assets/profile-merge-rule-setup.png)

## Profile Merge Rule Options Overview {#overview}

用户档案合并规则允许多种规则组合，每种组合都针对特定的使用情形。 有关何时使用每个规则组合的详细信息，请参阅下表。

| 跨设备选项 | 设备选项 | 可用性 | 评估类型 | 受众实验室支持 | 用例 |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| 无跨设备用户档案 | 设备用户档案 | 所有客户 | 实时和批处理 | 是 | [设备定位](merge-rule-targeting-options.md#device-personalization) |
| 无跨设备用户档案 | 外部设备图（包括协作设备图） | 所有客户 | 实时和批处理 | 否 | [扩展的设备定位](external-graph-use-cases.md#audience-expansion) |
| 当前已验证的用户档案 | 无设备用户档案 | 所有客户 | 仅实时 | 否 | [共享设备定位](merge-rule-targeting-options.md#target-shared-devices) |
| 上次验证用户档案 | 设备用户档案 | 所有客户 | 实时和批处理 | 是 | [联机／脱机定位](merge-rule-targeting-options.md#device-household-targeting) |
| 上次验证用户档案 | 用户档案链接设备图 | 所有客户 | 实时和批处理 | 是 | [跨设备定位](profile-link-use-case.md#cross-device-personalization) |
| 上次验证用户档案 | 外部设备图（包括协作设备图） | 所有客户 | 实时和批处理 | 否 | [高级跨设备定位](external-graph-use-cases.md#advanced-graph-expansion) |
| 所有跨设备用户档案 | 不适用 | 基于人 [员的目的地客户独享](../destinations/people-based-destinations-overview.md) | 仅批 | 否 | [针对基于人的目标进行定位](merge-rule-targeting-options.md#all-cross-device) |

## 用户档案合并规则段评估 {#segment-evaluation}

根据您 [!UICONTROL Profile Merge Rules] 的配置，受众管理器可以实时、批量或同时执行区段评估。

* 实时细分评估要求 [!DNL DCS] 访客实时查看您的数字资产，以符合细分资格。
* 对先前符合条件的特征执行批处理段评估。
* [!UICONTROL Profile Merge Rules] 支持实时和批量细分评估的方法，将实时访客活动与先前合格的特征相结合。

## 用户档案合并规则报告延迟 {#reporting-latency}

实时细分评估会立即反映在报 [!UICONTROL Profile Merge Rules] 告中。

批细分评估最长可能需要24小时，才能反映在“用户档案合 [并规则”报告中](profile-link-metrics.md)。

## 跨设备选项 {#auth-options}

您可 [!UICONTROL Cross-Device Options] 以选择已验证和未验证的用户，并利用其跨设备用户档案进行细分。 这些选项可帮助您识别并触及共享设备上的特定用户。 有关匿名和已验证用户的详细信息，请参阅 [受众管理器中的访客身份验证状态](../../reference/visitor-authentication-states.md)。

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
   <td colname="col2"> <p>告知 <span class="keyword"> 受众管理</span> 器不要使用从经过身份验证的用户收集的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 当前已验证的用户档案</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> 受众管理</span> 器在访客已登录您的站点时，将数据读取并写入已验证的用户档案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 上次验证用户档案</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> 受众管理</span> 器从上次登录设备的用户的已验证用户档案读取数据。 </p> <p>选中后， <span class="keyword"> 受众管理器</span> (如果用户为匿名用户档案)将不会向已验证的数据写入新特征数据。 验证后，新特征数据将写入用户的已验证用户档案。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 所有跨设备用户档案</span></b> </p> </td> 
   <td colname="col2"> <p>告知受众管理器从所有跨设备用户档案读取数据，而不管身份验证状态如何。 此选项仅适用于已购买“基于人员的目标”加载项的受众经理客户。</p> </td>
  </tr>
 </tbody>
</table>

## 跨设备用户档案选项 {#profile-options}

列表 [!UICONTROL Cross-Device Profile Options] 您的跨设备数据源。 这些选项使用您在创建跨设备数据源时提供的名称(请 [参阅创建跨设备数据源](merge-rules-start.md#create-data-source))。 您最多可以选择3个跨设备数据源，以与每个用户档案规则一起使用。 当您 [!UICONTROL Authenticated Profile Options] 选择或时，可 **[!UICONTROL Current Authenticated Profiles]** 以使用 **[!UICONTROL Last Authenticated Profiles]**。

## 设备选项 {#device-options}

您 [!UICONTROL Device Options] 可以选择用 *`device profile`* 户的类型 [!UICONTROL Profile Merge Rule]。 设备用户档案是根据从匿名浏览活动收集的特征构建的。 用户档案合并规则至少包括经过身份验证的选项和设备选项。

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
   <td colname="col2"> <p>告 <span class="keyword"> 诉受众</span> 管理者不要使用匿名用户档案中包含的特征进行细分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 设备用户档案</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> 受众管理</span> 者使用匿名设备用户档案进行细分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 用户档案链接设备图</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> 受众管理</span> 器从当前设备和最多100台用户已通过身份验证的其他设备读取用户档案。 此设备图表基于受众管理器中您自己的第一方 <span class="keyword"> 数据</span>。 它非常适合那些在数字资产中具有高级身份验证的客户。 用户档案 <span class="wintitle"> 链接</span> 设备图形会实时更新。 当您选择“当前已验证用户档案” <b><span class="uicontrol"> 或“上次已验证用户档案</span></b> ”时 <b><span class="uicontrol"> ，此选项可用</span></b>。 使用此选项时，您只能选择单个经过身份验证的用户档案(<span class="keyword"> 受众管理器</span> 会自动灰显其他)。 另请参阅 <a href="profile-link-use-case.md"> 用户档案链接设备图使用案例</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 协作设备图</span></b> </p> </td> 
   <td colname="col2"> <p>告知 <span class="keyword"> 受众</span> Manager使用Experience Cloud Device Co-op提供的链接从当前设备和最多100台其他设备 <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> 读取用户档案</a>。 </p> <p><span class="keyword"> 设备协作</span>是一项数字协作服务，可让参与的客户共享设备链接信息。设备 <span class="keyword"> 合作社在设备图</span> 中处理此 <span class="term"> 数据</span>。 设备图形将设备连接在一起，形成设备群集。 这些链接是根据概率 <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> 和确定性数据构建的</a>。 这些群集代表由未知人使用的一组设备。 <span class="keyword">设备协作</span>会在其成员之间共享这些群集，从而帮助成员向其客户提供富有价值的、一致的跨设备体验。 </p> <p> 有关设备协 <span class="wintitle"> 作的详细信息</span>，请参阅： </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> 设备合作社概述</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> 成员资格要求</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> 设备图： 内部流程和输出</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> 受众管理器和外部设备图形</a> （PDF下载）。 </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>第三方设备图选项</b> （人员和家庭） </p> </td>
   <td colname="col2"> <p>这些选项允许您根据第三方供应商提供的设备图技术构建合并规则。 第三方设备图表提供： </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 概率和／或确定性数据。 </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">个人或家庭级别的数据。 </li> 
     </ul> </p> <p>要使用这些选项，您必须是已与受众管理器集成的设备图形提供者 <span class="keyword"> 的客户</span>。 请联系您的客户经理以了解更多信息或开始。 </p> </td>
  </tr>
 </tbody>
</table>

<!--Victor/Vlad: In the above table, you link to a .pdf file on marketing.adobe.com. Can you move that PDF into Git and link to it? This pdf might get blown away with the marketing.adobe.com decommission. -Bob-->

## 外部合并策略 {#external-merge-policies}

根据在受众管理器外部定义的合并规则，从其他Experience Cloud解决方案自动创建的受众区段会被标记为使用 [!UICONTROL External Merge Policy]。 例如，请参阅 [受众管理器与Adobe Experience Platform之间的受众共享](../../integration/integration-aep/aam-aep-audience-sharing.md)。

>[!MORELIKETHIS]
>
>* [用户档案合并规则常见问题解答](../../faq/faq-profile-merge.md)

