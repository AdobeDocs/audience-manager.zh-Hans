---
description: 本页介绍了创建Facebook网站自定义受众(WCA)像素的过程，这些像素用于将基于Web的Audience Manager受众区段发送到Facebook，以便提高透明度的在线广告定位。
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Facebook WCA 集成
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 3%

---

# [!DNL Facebook WCA] 集成 {#facebook-wca-integration}

本页说明了创建 [!DNL Facebook Website Custom Audiences] ([!DNL WCA])像素，用于发送基于Web的 [!DNL Audience Manager] 受众区段 [!DNL Facebook]，用于提高透明度的在线广告定位。

## 概述 {#overview}

[Facebook网站自定义受众(WCA)](https://www.facebook.com/business/help/449542958510885) 用于创建访问过特定页面或在您的网站上执行特定操作的人员列表。 [!DNL Audience Manager] 启用 [!DNL WCA] 使用 [!DNL URL] 目标，您可以通过该目标配置基于像素的自定义集成，以将基于Web的受众发送到 [!DNL Facebook] 进行定位。

![Facebook WCA 集成](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 此功能要求您选择 [!UICONTROL Website] 适用于社交平台的受众选项 [URL目标](/help/using/features/destinations/create-url-destination.md). 社交平台要求在发送到其平台时，反向链接信息应被解除屏蔽。 请注意，这意味着目标平台/合作伙伴将能够在您的反向链接中看到信息 [!DNL URL].

## 先决条件 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] 区段，可以分配给新 [!DNL Facebook] 目标。 以下是 [如何创建区段](/help/using/features/segments/segment-builder.md) 在 [!DNL Audience Manager] UI。
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID])版本4.1.0或更高版本。 下载最新版本 **[此处](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL])版本9.0或更高版本，可从以下网站下载 **[此处](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. 或者，如果您使用 [服务器端转发(SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) 将数据导入 [!DNL Audience Manager]，则必须使用AppMeasurement版本2.12或更高版本。 下载 [!DNL AppMeasurement] 使用 [Analytics代码管理器](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

我们建议您使用 [Adobe Experience Platform标记](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## 步骤1 — 创建 [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

新建 [!UICONTROL URL Destination] in [!DNL Audience Manager] 然后命名 [!DNL Facebook Website Custom Audiences]. 创建目标时，请使用下面的设置。 您还可以将 [配置URL目标](/help/using/features/destinations/create-url-destination.md) 页面。

### 基本信息

* **[!UICONTROL Category]**: 自定义
* **[!UICONTROL Type]**: [!DNL URL]
* 选择 **[!UICONTROL Auto-fill Destination Mapping]** 复选框，然后选择 **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

选择选项 **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> 此导出标签可防止从设备图派生的第三方数据和数据包含在区段中。

### 配置

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. 选择此 [!UICONTROL URL Type] 选项， [!DNL Audience Manager] 不会掩盖反向链接 [!DNL URL] 触发时的信息 [!DNL Facebook WCA] 像素。
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* 在 **[!UICONTROL Base URL]** 和 **[!UICONTROL Secure URL]** 字段，输入 [!DNL Facebook WCA] 像素。
* **[!UICONTROL Delimiter]**: `,`

基本 [!DNL URL] 示例： `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

从页面触发的示例像素。 此示例显示符合三个条件的用户 [!DNL Audience Manager] 具有ID的区段3401321、2993399、3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 参数 | 描述 |
|---------|----------|
| `id` | 您的 [!DNL Facebook] 像素ID，您可以在 [!DNL Facebook Ad Manager] 创建受众像素时的用户界面。 |
| `ev` | Event.     这是任意值，将显示在 [!DNL Facebook Ad Manager] 像素开始在网站上触发后的用户界面。 请参阅 [!UICONTROL Include] 项目 [步骤3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)，以了解更多信息。 |
| `cd[segID]` | 其他参数，将开始在 [!DNL Facebook Ad Manager] 像素开始在网站上触发后的用户界面。 `segID` 也是任意的。 |
| `%ALIAS%` | 安 [!DNL Audience Manager] 宏，将动态替换为 [!DNL Audience Manager] [!UICONTROL segment] 网站访客符合条件的ID，以逗号分隔， |

您的 [!UICONTROL URL destination] 配置应类似于下图所示：

![目标配置](/help/using/integration/assets/facebook-wca.png)

保存 [!UICONTROL destination]. 然后，您可以继续 **区段映射** 中。

## 步骤2 — 区段映射 — 将区段映射到目标 {#step-2-segment-mappings}

在 [配置URL目标](/help/using/features/destinations/create-url-destination.md) 工作流中，将适用的区段映射到您新创建的 [!UICONTROL destination]. 请注意，映射值会自动填充 [!DNL Audience Manager] [!UICONTROL segment ID].

输入结束日期（如果适用），否则留空，无结束日期。

## 步骤3 — 创建 [!UICONTROL Audience] within [!DNL Facebook Ads Manager] {#step-3-create-audience}

请参阅 [创建网站自定义受众](https://www.facebook.com/business/help/666509013483225) 在 [!DNL Facebook] 帮助文档。 选择 [!UICONTROL Create Audience] 选项：

| 项目 | 描述 |
|---------|----------|
| 网站流量 | 自定义组合 |
| 包含 | <ul><li>选择 **[!UICONTROL Event]** >选择 **[!UICONTROL Adobe-Audience-Manager-Segment]**. 这是 `ev` 参数。 请注意，如果像素尚未触发，则 **[!UICONTROL Event]** 选项或 **[!UICONTROL Adobe-Audience-Manager-Segment]** 可能不显示在 [!DNL Facebook] 用户界面。</li><li>添加参数：选择 `segID`.</li><li><p>选择 **包含** 运算符。</p><p>鉴于访客可能符合多个区段的资格条件，则可能有多个区段，因此这一点很重要 [!UICONTROL segment IDs] 在像素参数中。 使用等于(`=`)运算符可能无法使访客符合受众的条件，并且您会看到音量较低。</p></li><li>添加值：输入 [!DNL Audience Manager] 区段ID。</li></ul> |
| 添加新条件 | 可选设置。 |
| 最后 | 可选设置。 |
| 受众名称 | 我们建议您使用相同的 [!DNL Audience Manager] 区段名称以确保一致性，除非您向此受众添加其他条件。 |

## 步骤4 — 分配 [!UICONTROL Audience] 至 [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

创建 [!DNL Custom Audience]，将其分配给广告营销活动。 创建新营销活动或编辑现有营销活动，您会发现新创建的受众列在 [!DNL Facebook] 用户界面。 您的广告营销活动将定位那些在访问您的网站时浏览器中看到像素触发的用户(如果 [!DNL Audience Manager] 包括在区段中。

## 概要 {#summary}

现在，您已为 [!DNL Audience Manager] 区段到 [!DNL Facebook WCA] 目标， [!DNL Audience Manager] 会有选择地 [!DNL Facebook WCA] 像素，以填充给定区段的用户，其中每个区段ID位于像素中 [!DNL Facebook Audience]. 这会导致 [!DNL Facebook Audience] 向网站上的适用受众触发的标记越多。

>[!NOTE]
>
> 如果用户从 [!DNL Audience Manager] 区段，当前没有方法 [!DNL Audience Manager] 通知 [!DNL Facebook] 从 [!DNL Custom Audience].
