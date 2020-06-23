---
description: 本页说明了创建Facebook网站自定义受众(WCA)像素的过程，以便将基于Web的Audience Manager受众段发送到Facebook，以便通过提高透明度实现在线广告定位。
seo-description: 本页说明了创建Facebook网站自定义受众(WCA)像素的过程，以便将基于Web的Audience Manager受众段发送到Facebook，以便通过提高透明度实现在线广告定位。
seo-title: Facebook WCA 集成
solution: Audience Manager
title: Facebook WCA 集成
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 6%

---


# [!DNL Facebook WCA] 集成 {#facebook-wca-integration}

本页说明了创建()像 [!DNL Facebook Website Custom Audiences] 素的过[!DNL WCA]程，以便将基于Web的受众细分发送 [!DNL Audience Manager][!DNL Facebook]到，以便通过提高透明度实现在线广告定位。

## 概述 {#overview}

[Facebook网站自定义受众](https://www.facebook.com/business/help/449542958510885) (WCA)允许您创建访问过特定页面或在您的网站上执行特定操作的人员的列表。 [!DNL Audience Manager] 支持激活 [!DNL WCA] 使 [!DNL URL] 用目标，您可以通过目标配置基于像素的自定义集成，将基于Web的受众发送 [!DNL Facebook] 到目标。

![Facebook WCA 集成](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 此功能要求您选择URL [!UICONTROL Website] 目标中的社交平台 [受众选项](/help/using/features/destinations/create-url-destination.md)。 社交平台要求在将推荐人信息发送到其平台时解除遮罩。 请注意，这意味着目标平台／合作伙伴将能够在您的推荐人中查看信息 [!DNL URL]。

## 先决条件 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] 区段，随时可分配到新目 [!DNL Facebook] 标。 下面介 [绍如何在UI中创建](/help/using/features/segments/segment-builder.md) 区 [!DNL Audience Manager] 段。
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID])版本4.1.0或更高版本。 Download the latest version **[here](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL])9.0或更高版本，可从此处 **[下载](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。 或者，如果您使[用服务器端转发](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)(SSF)将数据导入[!DNL Audience Manager]，则必须使用AppMeasurement版本2.12或更高版本。 Download[!DNL AppMeasurement]using the[Analytics Code Manager](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/admin-tools/code-manager-admin.html).

我们建议您使用Adobe Experience Platform启动或Adobe动态标签管理在步骤3和 [步骤4](https://docs.adobelaunch.com/) 中 [安装或升级库](https://docs.adobe.com/content/help/zh-Hans/dtm/using/dtm-home.html)。

## 第1步——创建 [!UICONTROL Facebook Destination] [!DNL Audience Manager] {#step-1-create-facebook-destination}

在中创建 [!UICONTROL URL Destination] 新 [!DNL Audience Manager] 名称 [!DNL Facebook Website Custom Audiences]。 创建目标时，请使用下面的设置。 您还可以参阅配 [置URL目标页](/help/using/features/destinations/create-url-destination.md) 。

### 基本信息

* **[!UICONTROL Category]**: 自定义
* **[!UICONTROL Type]**: [!DNL URL]
* 选中复 **[!UICONTROL Auto-fill Destination Mapping]** 选框，然后选择 **[!UICONTROL Segment ID]**。

### [!UICONTROL Data Export Labels]

选择选项 **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**。

>[!NOTE]
>
> 此导出标签可防止从设备图形派生的第三方数据和数据包含在区段中。

### 配置

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. 通过选择 [!UICONTROL URL Type] 此选项， [!DNL Audience Manager] 在触发像素时不 [!DNL URL] 会模糊推荐人 [!DNL Facebook WCA] 信息。
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* 在和字 **[!UICONTROL Base URL]** 段 **[!UICONTROL Secure URL]** 中，输入像 [!DNL Facebook WCA] 素。
* **[!UICONTROL Delimiter]**: `,`

基本 [!DNL URL] 示例： `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

从页面触发的示例像素。 此示例显示有资格划分三 [!DNL Audience Manager] 个区段（ID为3401321、2993399、3263410）的用户：

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 参数 | 描述 |
---------|----------|
| `id` | 您 [!DNL Facebook] 的像素ID，创建受众像素时， [!DNL Facebook Ad Manager] 您可以在用户界面中找到它。 |
| `ev` | Event.     这是任意值，当像素开始在现 [!DNL Facebook Ad Manager] 场触发时，该值将显示在用户界面中。 有关详 [!UICONTROL Include] 细信 [息，请参](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)阅步骤3中的项。 |
| `cd[segID]` | 一个附加参数，在像素开始在现 [!DNL Facebook Ad Manager] 场触发后，该参数将开始填充用户界面。 `segID` 也是武断的。 |
| `%ALIAS%` | 一 [!DNL Audience Manager] 个宏，将动态替换为站点访客符 [!DNL Audience Manager] 合的ID，用逗号 [!UICONTROL segment] 分隔， |

您 [!UICONTROL URL destination] 的配置应类似于下图：

![目标配置](/help/using/integration/assets/facebook-wca.png)

保存 [!UICONTROL destination]。 然后，您可以继续执行“ **段映射** ”步骤。

## 第2步——段映射——将段映射到目标 {#step-2-segment-mappings}

在“配 [置URL目标](/help/using/features/destinations/create-url-destination.md) ”工作流中，将适用的区段映射到您新创建的 [!UICONTROL destination]。 请注意，映射值会自动填充 [!DNL Audience Manager][!UICONTROL segment ID]。

输入终止日期（如果适用），否则，在无终止日期时留空。

## 第3步——在中创 [!UICONTROL Audience] 建 [!DNL Facebook Ads Manager] {#step-3-create-audience}

请参 [阅帮助文档中的](https://www.facebook.com/business/help/666509013483225) “创建网 [!DNL Facebook] 站自定义”。 在下表 [!UICONTROL Create Audience] 中选择以下选项：

| 项目 | 描述 |
---------|----------|
| 网站流量 | 自定义组合 |
| 包含 | <ul><li>选择 **[!UICONTROL Event]** >选择 **[!UICONTROL Adobe-Audience-Manager-Segment]**。 这是步骤1中示 `ev` 例像素中的参数值。 请注意，如果像素尚未触发，则选 **[!UICONTROL Event]** 项或 **[!UICONTROL Adobe-Audience-Manager-Segment]** 不可能显示在用 [!DNL Facebook] 户界面中。</li><li>添加参数： 选择 `segID`。</li><li><p>选择包含 **运算符** 。</p><p>考虑到访客可能有资格使用多个段，因此像素参数中可 [!UICONTROL segment IDs] 能有多个段，这一点很重要。 使用等号(`=`)运算符可能不能使访客符合受众的条件，并且您将观察到较小的音量。</p></li><li>添加值： 输入 [!DNL Audience Manager] 区段ID。</li></ul> |
| 添加新条件 | 可选设置。 |
| 最后一个 | 可选设置。 |
| 受众名称 | 建议您使用相同的区 [!DNL Audience Manager] 段名称来保持一致性，除非您向此受众添加其他条件。 |

## 第4步——将 [!UICONTROL Audience] 指定 [!UICONTROL Campaign] 到 [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

创建完 [!DNL Custom Audience]成后，将其分配给广告活动。 创建新活动或编辑现有受众，您会发现新创建的列在用户 [!DNL Facebook] 界面中。 您的广告活动将目标在访问您的网站时（如果在区段中包括），已在浏览器上看到像 [!DNL Audience Manager] 素火的用户。

## 概要 {#summary}

现在，您已将区段 [!DNL Audience Manager] 分配到目 [!DNL Facebook WCA] 标， [!DNL Audience Manager] 将使用像素中的相 [!DNL Facebook WCA] 应区段ID选择性地将像素激发给给定区段的用户以填充该 [!DNL Facebook Audience]区段。 这会导致向网站上的适 [!DNL Facebook Audience] 用受众触发的标记越多，标记的数量逐渐增加。

>[!NOTE]
>
> 如果用户掉出区 [!DNL Audience Manager] 段，则当前无法通 [!DNL Audience Manager] 知 [!DNL Facebook] 将用户从中删除 [!DNL Custom Audience]。

