---
description: 合并规则选项可让您控制Audience Manager用于细分的数据类型。合并规则可包括由配置文件链接设备图表、Adobe Experience Cloud Device Co-op和/或其他与Audience Manager集成的第三方设备图表提供商映射的设备配置文件。最多可创建个配置文件合并规则。
seo-description: 合并规则选项可让您控制Audience Manager用于细分的数据类型。合并规则可包括由配置文件链接设备图表、Adobe Experience Cloud Device Co-op和/或其他与Audience Manager集成的第三方设备图表提供商映射的设备配置文件。最多可创建个配置文件合并规则。
seo-title: 已定义配置文件合并规则选项
solution: Audience Manager
title: 已定义配置文件合并规则选项
uuid: 225eaf7-45e9-4f21-9360-d80 a9 f90520 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rule Options Defined {#profile-merge-rule-options-defined}

合并规则选项可让您控制Audience Manager用于细分的数据类型。A merge rule can include device profiles mapped by the [!UICONTROL Profile Link] device graph, the [!UICONTROL Adobe Experience Cloud Device Co-op], and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 3 [!UICONTROL Profile Merge Rules].

You build a [!UICONTROL Profile Merge Rule] by making a selection from these options:

<ul class="simplelist"> 
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#auth-options"> 身份验证选项</a> </li>
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#profile-options"> 身份验证配置文件选项</a> </li>
 <li><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> 设备选项</a> </li>
</ul>

## Authenticated Options {#auth-options}

The [!UICONTROL Authenticated Options] let you select un-authenticated and authenticated users and leverage their cross-device profile for segmentation. 这些选项可帮助您识别和触及共享设备上的特定用户。For more information on anonymous and authenticated users, see [Visitor Authentication States in Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 已验证的选项 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 没有身份验证配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> not to use data collected from authenticated users. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 当前身份验证配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read and write data to the authenticated profile if a visitor has logged in to your site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 上次身份验证配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read data from the authenticated profile of the user who last logged in on the device. </p> <p>When selected, <span class="keyword"> Audience Manager</span> will not write new trait data to the authenticated profile if the user is anonymous. 在身份验证后，新特性数据会写入用户的身份验证配置文件中。 </p> </td>
  </tr> 
 </tbody>
</table>

## Authenticated Profile Options {#profile-options}

[!UICONTROL Authenticated Profile Options] 其中将列出跨设备数据源。These options use the names you provided when you created a cross-device data source (see [Create a Cross-Device Data Source](../../features/profile-merge-rules/merge-rules-start.md#create-data-source)). 可选择最多个跨设备数据源，与每个配置文件规则一起使用。[!UICONTROL Authenticated Profile Options] 当您选择 **[!UICONTROL Current Authenticated Profile]****[!UICONTROL Last Authenticated Profile]**&#x200B;或.

## Device Options {#device-options}

[!UICONTROL Device Options] 允许您选择 *`device profile`*[!UICONTROL Profile Merge Rule]由a.设备配置文件由用户在匿名浏览Web时收集的特征组成。配置文件合并规则至少包括经过身份验证的选项和设备选项。

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
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> not to use the traits contained in the anonymous profile for segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 当前设备配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to use the anonymous device profile for segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 个人资料链接设备图表</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read the profiles from the current device and the last 3 devices that the user has authenticated from. This device graph is built on your own, first-party data in <span class="keyword"> Audience Manager</span>. 它非常适合在其数字资产中具有高身份验证级别的客户。<span class="wintitle"> 此时将实时更新配置文件链接</span> 设备图表。This option is available when you select <b><span class="uicontrol"> Current Authenticated Profile</span></b> or <b><span class="uicontrol"> Last Authenticated Profile</span></b>. When using this option, you can only choose a single authenticated profile (<span class="keyword"> Audience Manager</span> automatically grays out the others). See also, <a href="../../features/profile-merge-rules/profile-link-use-case.md"> Profile Link Device Graph Use Cases</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 计划设备图表</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to merge device profiles using the links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p><span class="keyword"> 设备协作</span>是一项数字协作服务，可让参与的客户共享设备链接信息。<span class="keyword"> Device Co-op</span> 在 <span class="term"> 设备图表中处理此数据</span>。设备图将设备群集关联在一起。These links are built from <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> probabilistic and deterministic data</a>. 这些群集代表一组未知人物使用的设备。<span class="keyword">设备协作</span>会在其成员之间共享这些群集，从而帮助成员向其客户提供富有价值的、一致的跨设备体验。 </p> <p> For more information about the <span class="wintitle"> Device Co-op</span>, see the: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> 设备合作社概述</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> 成员资格要求</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> 设备图表：内部流程和输出</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience Manager和外部设备图</a> (PDF下载)。 </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>第三方设备图表选项</b> (人物和家用) </p> </td>
   <td colname="col2"> <p>这些选项允许您基于第三方供应商提供的设备图表技术构建合并规则。第三方设备图提供： </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 概率和/或确定性数据。 </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">个人或家庭级别的数据。 </li> 
     </ul> </p> <p>To use these options, you must be a customer of a device graph provides who is already integrated with <span class="keyword"> Audience Manager</span>. 有关更多信息或入门，请与您的客户经理联系。 </p> <p>另请参阅&lt; a href="../../ features/profile-multiple-rules-use-cases. md)。 </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_ LIKE_ This]
>
>* [个人资料合并规则常见问题解答](../../faq/faq-profile-merge.md)

