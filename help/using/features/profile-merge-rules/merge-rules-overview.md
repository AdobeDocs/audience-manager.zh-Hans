---
description: 通过配置文件合并规则，您可以控制用于分段的数据集，并可以跨多个设备准确地定位人员。
seo-description: 通过配置文件合并规则，您可以控制用于分段的数据集，并可以跨多个设备准确地定位人员。
seo-title: 配置文件合并规则概述
solution: Audience Manager
title: 配置文件合并规则概述
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: 配置文件合并
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 4%

---

# [!UICONTROL Profile Merge Rules] 概述 {#profile-merge-rules-overview}

借助[!UICONTROL Profile Merge Rules]，您可以控制哪些数据集用于分段，并可以跨多个设备准确地定位用户。

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## 使用匿名和已验证的用户档案{#data-collection-targeting}进行数据收集和定位

通常，受众分段和定位依赖于从设备上所有用户收集的数据。 基于设备级别数据的数据收集和定位存在一些缺点。 例如，您无法区分共享设备的多个用户，也无法跨多个设备准确定位用户。 以设备为中心的数据收集不再足以用于数字营销活动或跨设备定位。

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] 从根本上改变 [!DNL Audience Manager] 收集数据和区段用户以进行定位的方式。它允许您使用2种不同类型的配置文件、设备配置文件和经过[验证的配置文件](../../reference/visitor-authentication-states.md)。

| 配置文件类型 | 描述 |
|---|---|
| [!UICONTROL Device Profile] | [!UICONTROL device profile]绑定到给定设备的ID，如[!UICONTROL cookie] ID或移动设备ID。<br><br>该服务包括：<ul><li>[!UICONTROL Rule-based traits] 在用户未进行身份验证时实现。</li><li>[!UICONTROL Onboarded traits] 与设备ID(如第三方 [!UICONTROL cookie-based]数据)关联。</li></ul> |
| [!UICONTROL Authenticated Profile] | [!UICONTROL authenticated profile]绑定到用户登录您的网站时传入的用户ID。<br><br>该服务包括：<ul><li>[!UICONTROL Rule-based traits] 在用户进行身份验证后跨设备收集。</li><li>[!UICONTROL Onboarded traits] 链接到同一用户ID的脱机文件中。</li></ul> |

这些不同的用户档案控制可用于分段的数据。 例如，使用经过[验证的配置文件](../../reference/visitor-authentication-states.md)，您可以根据来自多个设备的数据为单个用户构建准确的[!UICONTROL segments]。 这意味着您可以跨多个设备为客户提供一致的品牌体验。 [!DNL Audience Manager] 要实现此目的，需要将人员在线活动所使用的不同设备映射到其已验证的 [配置文件](../../reference/visitor-authentication-states.md)。这些映射称为[!UICONTROL Profile Link Device Graph]。

![](assets/authenticated2.png)

## 优势 {#advantages}

通过[!UICONTROL Profile Merge Rules]，您可以：

* 根据经过[验证的用户档案](../../reference/visitor-authentication-states.md)、匿名用户档案或两者的组合来定位用户。
* 定位跨设备的特定客户。
* 根据确定性数据构建设备图。
* 根据不同的用户档案优化[!UICONTROL segments]中的数据。
* 深入了解受众。
