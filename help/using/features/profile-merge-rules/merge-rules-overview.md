---
description: 通过配置文件合并规则，您可以控制用于分段的数据集，并可以在多个设备上准确地定位人员。
seo-description: With Profile Merge Rules you get control over the data sets used for segmentation and can target a person accurately across multiple devices.
seo-title: Profile Merge Rules Overview
solution: Audience Manager
title: 配置文件合并规则概述
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# [!UICONTROL Profile Merge Rules]概述 {#profile-merge-rules-overview}

通过[!UICONTROL Profile Merge Rules]，您可以控制用于分段的数据集，并且可以跨多个设备准确地定位用户。

>[!VIDEO](https://video.tv.adobe.com/v/31955?captions=chi_hans)

## 使用匿名和经过身份验证的用户档案进行数据收集和定位 {#data-collection-targeting}

通常，受众分段和定位依赖于从设备上的所有用户那里收集的数据。 基于设备级数据的数据收集和定位存在一些缺点。 例如，您无法区分共享一台设备的多个用户，也无法跨多个设备准确地定位用户。 以设备为中心的数据收集不再足以满足数字营销活动或跨设备定位的需要。

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules]从根本上改变了[!DNL Audience Manager]收集用于定位的数据和区段用户的方式。 它允许您使用2种不同类型的配置文件、一个设备配置文件和[已验证的配置文件](../../reference/visitor-authentication-states.md)。

| 配置文件类型 | 描述 |
|---|---|
| [!UICONTROL Device Profile] | [!UICONTROL device profile]绑定到给定设备的ID，如[!UICONTROL cookie] ID或移动设备ID。<br><br>它包括：<ul><li>[!UICONTROL Rule-based traits]在用户未通过身份验证时实现。</li><li>[!UICONTROL Onboarded traits]绑定到设备ID，例如[!UICONTROL cookie-based]第三方数据。</li></ul> |
| [!UICONTROL Authenticated Profile] | [!UICONTROL authenticated profile]绑定到人员登录到您的网站时传入的用户ID。<br><br>它包括：<ul><li>对用户进行身份验证后，跨设备收集了[!UICONTROL Rule-based traits]。</li><li>在链接到相同用户ID的脱机文件中[!UICONTROL Onboarded traits]。</li></ul> |

这些不同的配置文件控制可用于分段的数据。 例如，使用[验证的配置文件](../../reference/visitor-authentication-states.md)，您可以基于单个用户的多个设备数据构建准确的[!UICONTROL segments]。 这意味着您可以跨多个设备为客户提供一致的品牌体验。 [!DNL Audience Manager]通过将用户用于其在线活动的不同设备映射到其[已验证的配置文件](../../reference/visitor-authentication-states.md)来实现此目标。 这些映射称为[!UICONTROL Profile Link Device Graph]。

![](assets/authenticated2.png)

## 优势 {#advantages}

通过[!UICONTROL Profile Merge Rules]，您可以：

* 基于[已验证的配置文件](../../reference/visitor-authentication-states.md)、匿名配置文件或两者的组合定位用户。
* 跨设备定位特定客户。
* 基于确定性数据构建设备图。
* 根据不同的配置文件微调[!UICONTROL segments]中的数据。
* 获得对受众的其他洞察。
