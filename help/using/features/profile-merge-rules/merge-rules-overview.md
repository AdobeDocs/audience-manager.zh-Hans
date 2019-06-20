---
description: 利用配置文件合并规则，您可以控制用于细分的数据集，并可以准确定位多个设备中的人员。
seo-description: 利用配置文件合并规则，您可以控制用于细分的数据集，并可以准确定位多个设备中的人员。
seo-title: 个人资料合并规则概述
solution: Audience Manager
title: 个人资料合并规则概述
uuid: e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Profile Merge Rules Overview {#profile-merge-rules-overview}

[!UICONTROL Profile Merge Rules] 您可以控制用于细分的数据集，并可以准确定位多个设备中的人员。

## Data collection and targeting with anonymous and authenticated profiles {#data-collection-targeting}

通常，受众细分和定位取决于从设备上所有用户收集的数据。基于设备级数据的数据收集和定位有一些缺点。例如，您无法区分多个共享设备的用户或准确定位跨多个设备的用户。以设备为中心的数据收集不再足以进行数字营销活动或跨设备定位。

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] 从根本上改变 [!DNL Audience Manager] 了如何收集数据和细分用户进行定位。它允许您使用种不同类型的配置文件、设备配置文件和经过身份验证的配置文件。

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 个人资料类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 设备 配置文件 </td> 
   <td colname="col2"> <p>设备配置文件绑定到给定设备的ID，如cookie ID或移动设备ID。该服务包括： </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">用户未身份验证时，基于规则的特征。 </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">绑定到设备ID的载入特征，如基于cookie的第三方数据。 </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> 身份验证配置文件 </td> 
   <td colname="col2"> <p>身份验证配置文件与用户登录站点时传入的用户ID相关联。它包括 </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">对用户进行身份验证时跨设备收集的基于规则的特征。 </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">链接到同一用户ID的脱机文件中的载入特征。 </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

这些不同的配置文件控制可用于细分的数据。例如，使用经过身份验证的配置文件，您可以根据单个人员从多个设备的数据构建准确细分。这意味着您可以跨多种设备向客户提供一致的品牌体验。Additionally, cross-device authentication allows [!DNL Audience Manager] to map the different platforms a person uses for their online activities. [!UICONTROL Profile Link Device Graph]这称为：

![](assets/authenticated2.png)

## 优势 {#advantages}

[!UICONTROL Profile Merge Rules] 您可以：

* 根据身份验证配置文件、匿名配置文件或二者组合定位用户。
* 跨设备定位特定客户。
* 根据确定的数据构建设备图表。
* 根据不同档案微调细分中的数据。
* 深入了解受众。

## 入门指南 {#getting-started}

See the following sections and the [FAQ](../../faq/faq-profile-merge.md) for more information about [!UICONTROL Profile Merge Rules].

* [个人资料合并规则入门](/help/using/features/profile-merge-rules/merge-rules-start.md)
* [个人资料合并规则控制板](/help/using/features/profile-merge-rules/merge-rules-dashboard.md)
* [已定义配置文件合并规则选项](/help/using/features/profile-merge-rules/merge-rule-definitions.md)
* [个人资料合并规则的一般使用案例](/help/using/features/profile-merge-rules/merge-rule-targeting-options.md)
* [个人资料链接设备图表使用案例](/help/using/features/profile-merge-rules/profile-link-use-case.md)
* [外部设备图形使用案例](/help/using/features/profile-merge-rules/external-graph-use-cases.md)
* [个人资料合并规则报告指标](/help/using/features/profile-merge-rules/profile-link-metrics.md)
* [个人资料合并规则和设备取消分段流程](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)
* [即时跨设备抑制](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)
* [配置文件合并规则的重要注意事项与设备图表](/help/using/features/profile-merge-rules/considerations-pmr-device-graph.md)
