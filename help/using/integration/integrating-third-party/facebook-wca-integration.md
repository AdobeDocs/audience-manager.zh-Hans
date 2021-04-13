---
description: 本页说明了创建Facebook网站自定义受众(WCA)像素的过程，以便将基于Web的Audience Manager受众区段发送到Facebook，以便通过提高透明度实现在线广告定位。
seo-description: 本页说明了创建Facebook网站自定义受众(WCA)像素的过程，以便将基于Web的Audience Manager受众区段发送到Facebook，以便通过提高透明度实现在线广告定位。
seo-title: Facebook WCA 集成
solution: Audience Manager
title: Facebook WCA 集成
feature: 第三方集成
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 5%

---

# [!DNL Facebook WCA] 集成 {#facebook-wca-integration}

本页说明了创建[!DNL Facebook Website Custom Audiences]([!DNL WCA])像素的过程，以便将基于Web的[!DNL Audience Manager]受众段发送到[!DNL Facebook]，以便通过提高透明度实现在线广告定位。

## 概述 {#overview}

[Facebook网站自定义受众(](https://www.facebook.com/business/help/449542958510885) WCA)允许您创建列表访问过特定页面或在您的网站上执行特定操作的人员。[!DNL Audience Manager] 支持激活 [!DNL WCA] 使 [!DNL URL] 用目标，您可以通过目标配置基于像素的自定义集成，将基于Web的受众发送 [!DNL Facebook] 到目标。

![Facebook WCA 集成](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 此功能要求您在[URL目标](/help/using/features/destinations/create-url-destination.md)中选择[!UICONTROL Website]社交平台受众选项。 社交平台要求在将推荐人信息发送到其平台时解除掩码。 请注意，这意味着目标平台/合作伙伴将能够在您的推荐人[!DNL URL]中查看信息。

## 先决条件 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] 区段，随时可分配到新目 [!DNL Facebook] 标。以下是如何在[!DNL Audience Manager] UI中创建区段](/help/using/features/segments/segment-builder.md)。[
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID])版本4.1.0或更高版本。下载最新版本&#x200B;**[此处](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**。
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL])9.0或更高版本，可从此处 **[下载](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。或者，如果您使用[服务器端转发(SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)将数据导入[!DNL Audience Manager]，则必须使用AppMeasurement版本2.12或更高版本。 使用[分析代码管理器](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)下载[!DNL AppMeasurement]。

我们建议您使用[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html)或[Adobe动态标签管理](https://docs.adobe.com/content/help/zh-Hans/dtm/using/dtm-home.html)在步骤3和4中安装或升级库。

## 步骤1 — 在[!DNL Audience Manager] {#step-1-create-facebook-destination}中创建[!UICONTROL Facebook Destination]

在[!DNL Audience Manager]中新建一个[!UICONTROL URL Destination]，并将其命名为[!DNL Facebook Website Custom Audiences]。 创建目标时，请使用以下设置。 您还可以参阅[配置URL目标](/help/using/features/destinations/create-url-destination.md)页。

### 基本信息

* **[!UICONTROL Category]**: 自定义
* **[!UICONTROL Type]**: [!DNL URL]
* 选中&#x200B;**[!UICONTROL Auto-fill Destination Mapping]**&#x200B;复选框，然后选择&#x200B;**[!UICONTROL Segment ID]**。

### [!UICONTROL Data Export Labels]

选择选项&#x200B;**[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**。

>[!NOTE]
>
> 此导出标签可防止从设备图形派生的第三方数据和数据包含在区段中。

### 配置

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. 通过选择此[!UICONTROL URL Type]选项，[!DNL Audience Manager]在触发[!DNL Facebook WCA]像素时不会模糊推荐人[!DNL URL]信息。
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* 在&#x200B;**[!UICONTROL Base URL]**&#x200B;和&#x200B;**[!UICONTROL Secure URL]**&#x200B;字段中，输入[!DNL Facebook WCA]像素。
* **[!UICONTROL Delimiter]**:  `,`

基[!DNL URL]示例：`https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

从页面触发的示例像素。 此示例显示了符合以下三个[!DNL Audience Manager]区段条件的用户，其ID为3401321、2993399、3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 参数 | 描述 |
---------|----------|
| `id` | 您的[!DNL Facebook]像素ID，创建受众像素时可在[!DNL Facebook Ad Manager]用户界面中找到。 |
| `ev` | Event.     这是任意值，当像素开始在站点上触发时，该值将显示在[!DNL Facebook Ad Manager]用户界面中。 有关详细信息，请参阅[步骤3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)中的[!UICONTROL Include]项。 |
| `cd[segID]` | 一个附加参数，在像素开始在站点上触发后，该参数将开始填充到[!DNL Facebook Ad Manager]用户界面中。 `segID` 也是武断的。 |
| `%ALIAS%` | [!DNL Audience Manager]宏，将动态替换为站点访客符合的[!DNL Audience Manager] [!UICONTROL segment] ID，用逗号分隔 |

您的[!UICONTROL URL destination]配置应类似于下图：

![目标配置](/help/using/integration/assets/facebook-wca.png)

保存[!UICONTROL destination]。 然后，您可以继续执行&#x200B;**区段映射**&#x200B;步骤。

## 步骤2 — 区段映射 — 将区段映射到目标{#step-2-segment-mappings}

在[配置URL目标](/help/using/features/destinations/create-url-destination.md)工作流中，将适用区段映射到您新创建的[!UICONTROL destination]。 请注意，映射值会自动填充[!DNL Audience Manager] [!UICONTROL segment ID]。

输入终止日期（如果适用），否则留空为无终止日期。

## 步骤3 — 在[!DNL Facebook Ads Manager] {#step-3-create-audience}中创建[!UICONTROL Audience]

请参阅[!DNL Facebook]帮助文档中的[创建网站自定义受众](https://www.facebook.com/business/help/666509013483225)。 在下表中选择[!UICONTROL Create Audience]选项：

| 项目 | 描述 |
---------|----------|
| 网站流量 | 自定义组合 |
| 包含 | <ul><li>选择&#x200B;**[!UICONTROL Event]** >选择&#x200B;**[!UICONTROL Adobe-Audience-Manager-Segment]**。 这是步骤1中示例像素中`ev`参数的值。 请注意，如果像素尚未触发，则&#x200B;**[!UICONTROL Event]**&#x200B;选项或&#x200B;**[!UICONTROL Adobe-Audience-Manager-Segment]**&#x200B;可能不会显示在[!DNL Facebook]用户界面中。</li><li>添加参数：选择`segID`。</li><li><p>选择&#x200B;**包含**&#x200B;运算符。</p><p>这很重要，因为访客可能符合多个段的条件，因此像素参数中可能有多个[!UICONTROL segment IDs]。 使用等号(`=`)运算符可能不能使您的访客符合受众条件，您将看到较小的音量。</p></li><li>添加值：输入[!DNL Audience Manager]区段ID。</li></ul> |
| 添加新条件 | 可选设置。 |
| 最后 | 可选设置。 |
| 受众名称 | 我们建议您使用相同的[!DNL Audience Manager]区段名称来实现一致性，除非您向此受众添加其他条件。 |

## 步骤4 — 将[!UICONTROL Audience]分配给[!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}中的[!UICONTROL Campaign]

创建[!DNL Custom Audience]后，将其分配给广告活动。 创建新活动或编辑现有受众，您会发现新创建的列在[!DNL Facebook]用户界面中。 如果[!DNL Audience Manager]在区段中包含了在您的网站上，您的广告活动将目标在浏览器上看到像素着火的用户。

## 概要 {#summary}

现在，您已将[!DNL Audience Manager]区段分配给[!DNL Facebook WCA]目标，[!DNL Audience Manager]将选择性地将[!DNL Facebook WCA]像素激发给定区段的用户，其中像素中具有相应的区段ID，以填充[!DNL Facebook Audience]。 这会导致[!DNL Facebook Audience]的逐渐增加，标签被触发到网站上的适用受众的次数越多。

>[!NOTE]
>
> 如果用户从[!DNL Audience Manager]区段中脱离，则当前没有办法让[!DNL Audience Manager]通知[!DNL Facebook]将用户从[!DNL Custom Audience]中删除。

