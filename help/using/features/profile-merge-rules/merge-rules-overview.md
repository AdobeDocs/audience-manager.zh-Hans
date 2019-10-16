---
description: 利用配置文件合并规则，您可以控制用于细分的数据集，并且可以跨多个设备准确定位人员。
seo-description: 利用配置文件合并规则，您可以控制用于细分的数据集，并且可以跨多个设备准确定位人员。
seo-title: 个人资料合并规则概述
solution: Audience Manager
title: 个人资料合并规则概述
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# 个人资料合并规则概述 {#profile-merge-rules-overview}

您可 [!UICONTROL Profile Merge Rules] 以控制用于细分的数据集，并且可以跨多个设备准确定位用户。

>[!VIDEO](https://video.tv.adobe.com/v/28974?captions=chi_hans)

## 使用匿名和实名档案进行数据收集和定位 {#data-collection-targeting}

通常，受众细分和定位依赖于从设备上所有用户收集的数据。 基于设备级数据的数据收集和定位存在一些缺点。 例如，您无法区分共享设备的多个用户或跨多个设备准确地定位用户。 以设备为中心的数据收集不再足以用于数字营销活动或跨设备定位。

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] 从根本上改变 [!DNL Audience Manager] 收集数据和细分用户进行定位的方式。 它允许您使用2种不同类型的配置文件、设备配置文件和经过身份验证 [的配置文件](../../reference/visitor-authentication-states.md)。

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 配置文件类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 设备 配置文件 </td> 
   <td colname="col2"> <p>设备配置文件绑定到给定设备的ID，如cookie ID或移动设备ID。 该服务包括： </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">在用户未通过身份验证时实现基于规则的特征。 </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">绑定到设备ID（如基于cookie的第三方数据）的已载入特征。 </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> 已验证的配置文件 </td> 
   <td colname="col2"> <p>经过身份验证的配置文件将绑定到用户登录您的站点时传入的用户ID。 包括 </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">当用户通过身份验证时跨设备收集的基于规则的特征。 </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">链接到同一用户ID的脱机文件中已载入的特征。 </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

这些不同的配置文件控制可用于细分的数据。 例如，使用经过身份验证 [的配置文件](../../reference/visitor-authentication-states.md)，您可以根据来自多个设备的数据为单个用户构建准确的细分。 这意味着您可以跨多种设备为客户提供一致的品牌体验。 Audience manager通过存储用户用于其在线活动的不同设备与其经过身份验证的配置文件的映射来实现 [这一点](../../reference/visitor-authentication-states.md)。 这些映射称为 [!UICONTROL Profile Link Device Graph]。

![](assets/authenticated2.png)

## 优势 {#advantages}

您 [!UICONTROL Profile Merge Rules] 可以：

* 根据实名档案、 [匿名档案](../../reference/visitor-authentication-states.md)，或两者的组合定位用户。
* 跨设备定位特定客户。
* 基于确定性数据构建设备图。
* 根据不同的配置文件微调细分中的数据。
* 进一步了解受众。
