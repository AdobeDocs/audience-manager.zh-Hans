---
description: 本页说明了创建Facebook网站自定义受众(WCA)像素的过程，以便将基于Web的Audience manager受众细分发送到Facebook，以便通过改进的透明度实现在线广告定位。
seo-description: 本页说明了创建Facebook网站自定义受众(WCA)像素的过程，以便将基于Web的Audience manager受众细分发送到Facebook，以便通过改进的透明度实现在线广告定位。
seo-title: Facebook WCA集成
solution: Audience Manager
title: Facebook WCA集成
translation-type: tm+mt
source-git-commit: 28d1292140a56cf1627a8921876d9483221876ca

---


# Facebook WCA集成 {#facebook-wca-integration}

本页说明了创建Facebook网站自定义受众(WCA)像素的过程，以便将基于Web的Audience manager受众细分发送到Facebook，以便通过改进的透明度实现在线广告定位。

## 概述 {#overview}

[Facebook网站自定义受众(WCA)](https://www.facebook.com/business/help/449542958510885) 允许您创建访问过特定页面或在您的网站上执行特定操作的人员列表。 Audience manager支持使用URL目标在WCA中激活，您可以通过该目标配置基于像素的自定义集成，将基于Web的受众发送到Facebook进行定位。

![Facebook WCA集成](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 此功能要求您选择 [URL目标中的“社交平台的网站受众”选项](/help/using/features/destinations/create-url-destination.md)。 社交平台要求在发送到其平台时，解除对引用信息的遮罩。 请注意，这意味着目标平台／合作伙伴将能够查看您的引用URL中的信息。

## 先决条件 {#prerequisites}

1. Facebook广告帐户
2. Audience manager区段，可随时分配给您的新Facebook目标。 下面介 [绍如何在Audience Manager](/help/using/features/segments/segment-builder.md) UI中创建区段。
3. Adobe Experience Cloud ID服务(ECID)4.1.0版或更高版本。 在此处下载最新 **[版本](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**。
4. Audience Manager数据集成库(DIL)9.0版或更高版本，可从此处下 **[载](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。 或者，如果您使 [用服务器端转发(SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) ，将数据导入Audience Manager，则必须使用AppMeasurement版本2.12或更高版本。 使用Analytics代码管理器 [下载AppMeasurement](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)。

我们建议您使用 [Adobe Launch或](https://docs.adobelaunch.com/) Adobe Dynamic Tag Management在步骤3和4中安装或升级库 [](https://marketing.adobe.com/resources/help/en_US/dtm/)。

## 第1步——在Audience manager中创建Facebook目标 {#step-1-create-facebook-destination}

在Audience manager中新建一个URL目标，并将其命名为Facebook网站自定义受众。 创建目标时，请使用以下设置。 您还可以参阅配 [置URL目标页面](/help/using/features/destinations/create-url-destination.md) 。

**基本信息**

* **类别**:自定义
* **类型**:URL
* 选中“ **自动填充目标映射** ”复选框，然后选择 **区段ID**。

**数据导出标签**

选择选项此目 **标可能会启用包含个人识别信息(PII)的组合**。

>[!NOTE]
>
> 此导出标签可防止从设备图形派生的第三方数据和数据包含在区段中。

**配置**

* **URL类型**:为社 **交平台选择网站受众**。 通过选择此URL类型选项，Audience manager在触发Facebook WCA像素时不会遮掩引用URL信息。
* **序列化**:选择 **启用**。
* 在“基 **本URL** ”和“ **安全URL** ”字段中，输入Facebook WCA像素。
* **Delimiter（分隔符）**: ,

基本URL示例： `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

从页面触发的像素示例。 此示例显示有资格划分三个Audience manager区段的用户，其ID为3401321、2993399、3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| 参数 | 描述 |
---------|----------|
| `id` | 您的Facebook像素ID，创建受众像素时，您可以在Facebook广告管理器UI中找到该ID。 |
| `ev` | 事件. 这是一个任意值，当像素开始在站点上触发时，该值将显示在Facebook广告管理器UI中。 有关详细信息，请参 [阅步骤3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)中的包含项。 |
| `cd[segID]` | 一个附加参数，该参数将在像素开始在站点上触发后开始填充到Facebook广告管理器UI中。 `segID` 也是武断的。 |
| `%ALIAS%` | Audience manager宏，将动态替换为站点访客有资格使用的Audience manager区段ID，以逗号分隔。 |

您的URL目标配置应类似于下图：

![目标配置](/help/using/integration/assets/facebook-wca.png)

保存目标。 然后，您可以继续执行“区 **段映射** ”步骤。

## 第2步——区段映射——将区段映射到目标 {#step-2-segment-mappings}

在“配 [置URL目标”工作流中](/help/using/features/destinations/create-url-destination.md) ，将适用的区段映射到您新创建的目标。 请注意，映射值会自动填充Audience manager区段ID。

输入结束日期（如果适用），否则，在无结束日期时留空。

## 第3步——在Facebook广告管理器中创建受众 {#step-3-create-audience}

请参 [阅Facebook帮助文档中的创建网站](https://www.facebook.com/business/help/666509013483225) “自定义受众”。 在下表中选择创建受众选项：


| 项目 | 描述 |
---------|----------|
| 网站流量 | 自定义组合 |
| 包含 | <ul><li>选择 **“活动** ”&gt;“选 **择Adobe-Audience-Manager-区段”**。 这是步骤1中示例像素中ev参数的值。 请注意，如果像素尚未触发，则 **Event** （活动）选项或 **Adobe-Audience-Manager-Segment** (Adobe-Audience-Manager-Segment)可能不会显示在Facebook UI中。</li><li>添加参数：选择 `segID`。</li><li><p>选择contains运 **算符** 。</p><p>这很重要，因为访客可能有资格访问多个区段，因此像素参数中可能有多个区段ID。 使用等号(=)运算符可能无法使访客有资格访问受众，并且您会发现访客量较低。</p></li><li>添加值：输入Audience Manager区段ID。</li></ul> |
| 添加新条件 | 可选设置。 |
| 最后一个 | 可选设置。 |
| 受众名称 | 除非您向此Audience添加其他条件，否则建议您使用相同的Audience manager区段名称来保持一致性。 |

## 第4步——在Facebook广告管理器中将受众分配到营销活动 {#step-4-assign-audience-to-campaign}

在创建自定义受众后，将其分配给广告营销活动。 创建新营销活动或编辑现有营销活动，您会发现新创建的受众列在Facebook UI中。 如果您的广告营销活动在访问您的网站时看到浏览器上的像素点火，则这些用户将被定位到您的网站中（如果Audience manager将这些用户包括在区段中）。

## 概要 {#summary}

现在，您已将您的Audience manager区段分配到Facebook WCA目标，Audience Manager将选择性地将Facebook WCA像素激发给给定区段的用户，其中像素中具有相应的区段ID，以填充Facebook Audience。 这会导致Facebook受众逐渐增加，向您网站上的适用受众触发的标签越多。

>[!NOTE]
>
> 如果用户掉出Audience manager区段，则Audience manager当前无法通知Facebook将用户从自定义受众中删除。

