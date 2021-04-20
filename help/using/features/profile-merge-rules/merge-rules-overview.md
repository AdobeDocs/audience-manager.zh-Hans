---
description: 利用用户档案合并规则，您可以控制用于细分的数据集，并可以跨多个设备准确目标人。
seo-description: 利用用户档案合并规则，您可以控制用于细分的数据集，并可以跨多个设备准确目标人。
seo-title: 配置文件合并规则概述
solution: Audience Manager
title: 配置文件合并规则概述
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 4%

---

# [!UICONTROL Profile Merge Rules] 概述 {#profile-merge-rules-overview}

通过[!UICONTROL Profile Merge Rules]，您可以控制哪些数据集用于细分，并可以跨多个设备准确目标用户。

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## 使用匿名和实名用户档案{#data-collection-targeting}进行数据收集和定位

通常，受众细分和定位依赖于从设备上所有用户收集的数据。 基于设备级数据的数据收集和定位存在一些缺点。 例如，您无法区分共享设备的多个用户或在多个设备上准确目标用户。 以设备为中心的数据收集不再足以用于数字营销活动或跨设备定位。

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] 从根本上改变 [!DNL Audience Manager] 收集数据和细分用户以进行定位的方式。它允许您使用2种不同类型的用户档案、设备用户档案和[已验证用户档案](../../reference/visitor-authentication-states.md)。

| 用户档案类型 | 描述 |
|---|---|
| [!UICONTROL Device Profile] | [!UICONTROL device profile]与给定设备的ID（如[!UICONTROL cookie] ID或移动设备ID）绑定。<br><br>该服务包括：<ul><li>[!UICONTROL Rule-based traits] 当用户未通过身份验证时实现。</li><li>[!UICONTROL Onboarded traits] 绑定到设备ID(如 [!UICONTROL cookie-based]第三方数据)。</li></ul> |
| [!UICONTROL Authenticated Profile] | [!UICONTROL authenticated profile]与用户登录您的站点时传入的用户ID关联。<br><br>该服务包括：<ul><li>[!UICONTROL Rule-based traits] 当用户通过身份验证时跨设备收集。</li><li>[!UICONTROL Onboarded traits] 链接到同一用户ID的脱机文件中。</li></ul> |

这些不同的用户档案控制可用于分段的数据。 例如，使用[已验证的用户档案](../../reference/visitor-authentication-states.md)，您可以根据来自多个设备的数据为单个用户构建准确的[!UICONTROL segments]。 这意味着您可以跨多种设备为客户提供一致的品牌体验。 [!DNL Audience Manager] 通过存储个人用于其在线活动的不同设备到其已验证用户档案的映射来实 [现这一点](../../reference/visitor-authentication-states.md)。这些映射称为[!UICONTROL Profile Link Device Graph]。

![](assets/authenticated2.png)

## 优势 {#advantages}

使用[!UICONTROL Profile Merge Rules]，您可以：

* 目标用户基于[已验证用户档案](../../reference/visitor-authentication-states.md)、匿名用户档案或两者的组合。
* 目标跨设备的特定客户。
* 根据确定性数据构建设备图。
* 根据不同的用户档案微调[!UICONTROL segments]中的数据。
* 进一步了解您的受众。
