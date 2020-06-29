---
description: 利用用户档案合并规则，您可以控制用于细分的数据集，并且可以跨多个设备准确目标人。
seo-description: 利用用户档案合并规则，您可以控制用于细分的数据集，并且可以跨多个设备准确目标人。
seo-title: 配置文件合并规则概述
solution: Audience Manager
title: 配置文件合并规则概述
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---


# [!UICONTROL Profile Merge Rules] 概述 {#profile-merge-rules-overview}

您 [!UICONTROL Profile Merge Rules] 可以控制用于细分的数据集，并可以跨多个设备准确目标用户。

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## 通过匿名和实名用户档案收集和定位数据 {#data-collection-targeting}

通常，受众细分和定位依赖于从设备上所有用户收集的数据。 基于设备级数据的数据收集和定位存在一些缺点。 例如，您无法区分共享设备的多个用户或在多个设备上准确目标用户。 以设备为中心的数据收集不再足以用于数字营销活动或跨设备定位。

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] 从根本上改变 [!DNL Audience Manager] 收集数据和细分用户以进行定位的方式。 它允许您使用2种不同类型的用户档案、设备用户档案和经过身份验证 [的用户档案](../../reference/visitor-authentication-states.md)。

| 用户档案类型 | 描述 |
|---|---|
| [!UICONTROL Device Profile] | A [!UICONTROL device profile] 绑定到指定设备的ID，如 [!UICONTROL cookie] ID或移动设备ID。<br><br>该服务包括：<ul><li>[!UICONTROL Rule-based traits] 当用户未通过身份验证时实现。</li><li>[!UICONTROL Onboarded traits] 绑定到设备ID(如 [!UICONTROL cookie-based]第三方数据)。</li></ul> |
| [!UICONTROL Authenticated Profile] | 该 [!UICONTROL authenticated profile] 关联到在用户登录您的站点时传入的用户ID。<br><br>该服务包括：<ul><li>[!UICONTROL Rule-based traits] 当用户通过身份验证时跨设备收集。</li><li>[!UICONTROL Onboarded traits] 链接到同一用户ID的脱机文件中。</li></ul> |

这些不同的用户档案控制可用于分段的数据。 例如，使用经过验 [证的用户档案](../../reference/visitor-authentication-states.md)，您可以根据来自 [!UICONTROL segments] 多个设备的数据为单个用户构建准确的数据。 这意味着您可以跨多种设备为客户提供一致的品牌体验。 [!DNL Audience Manager] 通过存储个人用于其在线活动的不同设备到其认证用户档案的映 [射来实现](../../reference/visitor-authentication-states.md)。 这些映射称为 [!UICONTROL Profile Link Device Graph]。

![](assets/authenticated2.png)

## 优势 {#advantages}

您 [!UICONTROL Profile Merge Rules] 可以：

* 目标用户 [基于实名用户档案](../../reference/visitor-authentication-states.md)、匿名用户档案或两者的组合。
* 目标跨设备的特定客户。
* 根据确定性数据构建设备图。
* 根据不同的用户档案 [!UICONTROL segments] 微调数据。
* 进一步了解您的受众。
