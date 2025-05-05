---
description: 本页演示了创建Facebook网站自定义受众(WCA)像素的过程，这些像素用于将基于Web的Audience Manager受众区段发送到Facebook，以便通过提高透明度来实现在线广告定位。
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: facebook WCA集成
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 6dc931b88666515cf51ab89ce1a54bbcf9995679
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 1%

---

# [!DNL Facebook WCA]集成 {#facebook-wca-integration}

本页说明了创建[!DNL Facebook Website Custom Audiences] ([!DNL WCA])像素的过程，其目的是将基于Web的[!DNL Audience Manager]受众区段发送到[!DNL Facebook]，以用于提高透明度的在线广告定位。

>[!IMPORTANT]
>
>这不是Audience Manager与Facebook之间的产品化集成。

## 概述 {#overview}

[Facebook网站自定义受众(WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494)允许您创建访问过某些页面或在您的网站上执行了特定操作的人员的列表。 [!DNL Audience Manager]可使用[!DNL URL]目标在[!DNL WCA]中启用激活，通过目标，可配置基于像素的自定义集成以将基于Web的受众发送到[!DNL Facebook]以进行定位。

![Facebook WCA 集成](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 此功能要求您在[URL目标](/help/using/features/destinations/create-url-destination.md)中选择[!UICONTROL Website]社交平台受众选项。 社交平台要求在将反向链接信息发送到其平台时进行取消屏蔽。 请注意，这意味着目标平台/合作伙伴将能够查看您的反向链接[!DNL URL]中的信息。

## 先决条件 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager]个区段，已准备好分配给您的新[!DNL Facebook]目标。 以下是[如何在[!DNL Audience Manager] UI中创建区段](/help/using/features/segments/segment-builder.md)。
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID])版本4.1.0或更高版本。 在此处[&#128279;](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**下载最新版本**。
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL])版本9.0或更高版本，可从&#x200B;**[此处](https://github.com/Adobe-Marketing-Cloud/dil/releases)**&#x200B;下载。 或者，如果您使用[服务器端转发(SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html)将数据导入[!DNL Audience Manager]，则必须使用AppMeasurement版本2.12或更高版本。 使用[Analytics代码管理器](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html)下载[!DNL AppMeasurement]。

我们建议您使用[Adobe Experience Platform标记](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html)安装或升级步骤3和4中的库。

## 步骤1 — 在[!DNL Audience Manager]中创建[!UICONTROL Facebook Destination] {#step-1-create-facebook-destination}

在[!DNL Audience Manager]中创建新的[!UICONTROL URL Destination]并将其命名为[!DNL Facebook Website Custom Audiences]。 创建目标时，请使用以下设置。 您还可以参阅[配置URL目标](/help/using/features/destinations/create-url-destination.md)页面。

### 基本信息

* **[!UICONTROL Category]**：自定义
* **[!UICONTROL Type]**： [!DNL URL]
* 选中&#x200B;**[!UICONTROL Auto-fill Destination Mapping]**&#x200B;复选框，然后选择&#x200B;**[!UICONTROL Segment ID]**。

### [!UICONTROL Data Export Labels]

选择选项&#x200B;**[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**。

>[!NOTE]
>
> 此导出标签可防止在区段中包含从设备图派生的第三方数据和数据。

### 配置

* **[!UICONTROL URL type]**：选择&#x200B;**[!UICONTROL Website audience for social platforms]**。 通过选择此[!UICONTROL URL Type]选项，[!DNL Audience Manager]在触发[!DNL Facebook WCA]像素时不会遮蔽反向链接[!DNL URL]信息。
* **[!UICONTROL Serialize]**：选择&#x200B;**[!UICONTROL Enable]**。
* 在&#x200B;**[!UICONTROL Base URL]**&#x200B;和&#x200B;**[!UICONTROL Secure URL]**&#x200B;字段中，输入[!DNL Facebook WCA]像素。
* **[!UICONTROL Delimiter]**： `,`

基础[!DNL URL]示例： `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

从页面触发的示例像素。 此示例显示一个用户符合三个[!DNL Audience Manager]区段的条件，ID为3401321、2993399、3263410：

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 参数 | 描述 |
|---------|----------|
| `id` | 您的[!DNL Facebook]像素ID，在创建受众像素时可在[!DNL Facebook Ad Manager]用户界面中找到该ID。 |
| `ev` | 事件。 这是一个任意值，一旦像素开始在网站上触发，该值将出现在[!DNL Facebook Ad Manager]用户界面中。 有关详细信息，请参阅[步骤3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)中的[!UICONTROL Include]项。 |
| `cd[segID]` | 一个附加参数，一旦像素开始在网站上触发，该参数即开始填充到[!DNL Facebook Ad Manager]用户界面中。 `segID`也是任意的。 |
| `%ALIAS%` | [!DNL Audience Manager]宏，它将动态替换为网站访客有资格的[!DNL Audience Manager] [!UICONTROL segment] ID，以逗号分隔， |

您的[!UICONTROL URL destination]配置应如下图所示：

![目标配置](/help/using/integration/assets/facebook-wca.png)

保存[!UICONTROL destination]。 然后，您可以继续执行&#x200B;**区段映射**&#x200B;步骤。

## 步骤2 — 区段映射 — 将区段映射到目标 {#step-2-segment-mappings}

在[配置URL目标](/help/using/features/destinations/create-url-destination.md)工作流中，将适用的区段映射到新创建的[!UICONTROL destination]。 请注意，映射值已使用[!DNL Audience Manager] [!UICONTROL segment ID]自动填充。

输入结束日期（如果适用），否则留空将不输入结束日期。

## 步骤3 — 在[!DNL Facebook Ads Manager]中创建[!UICONTROL Audience] {#step-3-create-audience}

请参阅[!DNL Facebook]帮助文档中的[创建网站自定义受众](https://www.facebook.com/business/help/666509013483225)。 选择下表中的[!UICONTROL Create Audience]选项：

| 项目 | 描述 |
|---------|----------|
| 网站流量 | 自定义组合 |
| 包含 | <ul><li>选择&#x200B;**[!UICONTROL Event]** >选择&#x200B;**[!UICONTROL Adobe-Audience-Manager-Segment]**。 这是步骤1中示例像素中`ev`参数的值。 请注意，如果像素尚未触发，则&#x200B;**[!UICONTROL Event]**&#x200B;选项或&#x200B;**[!UICONTROL Adobe-Audience-Manager-Segment]**&#x200B;可能不会显示在[!DNL Facebook]用户界面中。</li><li>添加参数：选择`segID`。</li><li><p>选择&#x200B;**contains**&#x200B;运算符。</p><p>这一点很重要，因为考虑到访客可能有资格使用多个区段，像素参数中可能会有多个[!UICONTROL segment IDs]。 使用equals (`=`)运算符可能无法使访客符合受众资格，而且您会看到较小的访问量。</p></li><li>添加值：输入[!DNL Audience Manager]区段ID。</li></ul> |
| 添加新完成情况 | 可选设置。 |
| 过去 | 可选设置。 |
| 受众名称 | 除非您向此受众添加其他条件，否则我们建议您使用相同的[!DNL Audience Manager]区段名称以保持一致性。 |

## 步骤4 — 在[!DNL Facebook Ads Manager]中将[!UICONTROL Audience]分配给[!UICONTROL Campaign] {#step-4-assign-audience-to-campaign}

创建[!DNL Custom Audience]后，将其分配给广告营销活动。 创建新营销活动或编辑现有营销活动，您会发现新创建的受众列在[!DNL Facebook]用户界面中。 您的广告营销活动将定向那些访问您的网站时看到其浏览器上触发像素的用户（如果[!DNL Audience Manager]将这些用户包含在区段中）。

## 摘要 {#summary}

现在，您已将[!DNL Audience Manager]区段分配到[!DNL Facebook WCA]目标，[!DNL Audience Manager]将选择性地向给定区段的用户触发[!DNL Facebook WCA]像素（该像素中具有相应的区段ID）以填充[!DNL Facebook Audience]。 标记向网站上的适用受众触发的次数越多，则导致[!DNL Facebook Audience]的逐渐增加。

>[!NOTE]
>
> 如果用户从[!DNL Audience Manager]区段中流失，[!DNL Audience Manager]当前无法通知[!DNL Facebook]从[!DNL Custom Audience]中删除该用户。
>
