---
description: 本页说明了创建Facebook网站自定义受众(WCA)像素的过程，以便将基于Web的受众管理器受众段发送到Facebook，以便通过提高透明度实现在线广告定位。
seo-description: 本页说明了创建Facebook网站自定义受众(WCA)像素的过程，以便将基于Web的受众管理器受众段发送到Facebook，以便通过提高透明度实现在线广告定位。
seo-title: Facebook WCA集成
solution: Audience Manager
title: Facebook WCA集成
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Facebook WCA集成 {#facebook-wca-integration}

本页说明了创建Facebook网站自定义受众(WCA)像素的过程，以便将基于Web的受众管理器受众段发送到Facebook，以便通过提高透明度实现在线广告定位。

## 概述 {#overview}

[Facebook网站自定义受众](https://www.facebook.com/business/help/449542958510885) (WCA)允许您创建访问过特定页面或在您的网站上执行特定操作的人员的列表。 受众管理器启用WCA中使用URL目标的激活，您可以通过URL目标配置基于像素的自定义集成，将基于Web的受众发送到Facebook进行定位。

![Facebook WCA集成](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 此功能要求您选择URL目标中的“社交平台的网站受众 [”选项](/help/using/features/destinations/create-url-destination.md)。 社交平台要求在将推荐人信息发送到其平台时解除遮罩。 请注意，这意味着目标平台／合作伙伴将能够在您的推荐人URL中查看信息。

## 先决条件 {#prerequisites}

1. Facebook广告帐户
2. 受众管理器区段，随时可分配到新Facebook目标。 下面介 [绍如何在受众管理器](/help/using/features/segments/segment-builder.md) UI中创建区段。
3. Adobe Experience Platform Identity Service(ECID)4.1.0版或更高版本。 在此处下载最新 **[版本](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**。
4. 受众管理器数据集成库(DIL)9.0版或更高版本，可从此处 **[下载](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。 或者，如果您使[用服务器端转发(SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)，将数据导入受众管理器，则必须使用AppMeasurement版本2.12或更高版本。 使用Analytics Code Manager[下载AppMeasurement](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)。

我们建议您使用Adobe Experience Platform Launch或Adobe Dynamic Tag Management在步骤3和 [步骤4中安装](https://docs.adobelaunch.com/)[或升级这些库](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html)。

## 步骤1 —— 在受众管理器中创建Facebook目标 {#step-1-create-facebook-destination}

在受众管理器中新建一个URL目标，并将其命名为Facebook网站自定义受众。 创建目标时，请使用下面的设置。 您还可以参阅配 [置URL目标页](/help/using/features/destinations/create-url-destination.md) 。

**基本信息**

* **类别**: 自定义
* **类型**: URL
* 选中“ **自动填充目标映射** ”复选框，然后选 **择段ID**。

**数据导出标签**

选择选项此 **目标可能启用与个人身份信息(PII)的组合**。

>[!NOTE]
>
> 此导出标签可防止从设备图形派生的第三方数据和数据包含在区段中。

**配置**

* **URL类型**: 选择 **社交平台的网站受众**。 通过选择此URL类型选项，受众管理器在触发Facebook WCA像素时不会模糊推荐人URL信息。
* **序列化**: 选择 **启用**。
* 在“基 **本URL** ”和 **“安全URL** ”字段中，输入Facebook WCA像素。
* **Delimiter（分隔符）**: ,

基本URL示例： `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

从页面触发的示例像素。 此示例显示有资格划分三个“受众管理器”区段（ID为3401321、2993399、3263410）的用户：

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| 参数 | 描述 |
---------|----------|
| `id` | 您的Facebook像素ID，创建受众像素时，您可以在Facebook广告管理器UI中找到。 |
| `ev` | 事件. 这是任意值，当像素开始在站点上触发时，该值将显示在Facebook广告管理器UI中。 有关详细信息，请 [参阅](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)步骤3中的包括项。 |
| `cd[segID]` | 一个附加参数，在像素开始在网站上触发后，该参数将开始填充到Facebook广告管理器UI中。 `segID` 也是武断的。 |
| `%ALIAS%` | 受众管理器宏，将动态替换为站点访客符合的受众管理器区段ID，用逗号分隔， |

您的URL目标配置应类似于下图：

![目标配置](/help/using/integration/assets/facebook-wca.png)

保存目标。 然后，您可以继续执行“ **段映射** ”步骤。

## 第2步——段映射——将段映射到目标 {#step-2-segment-mappings}

在“配 [置URL目标](/help/using/features/destinations/create-url-destination.md) ”工作流中，将适用的区段映射到您新创建的目标。 请注意，映射值会自动填充受众管理器区段ID。

输入终止日期（如果适用），否则不保留终止日期为空。

## 步骤3 —— 在Facebook广告管理器中创建受众 {#step-3-create-audience}

请参 [阅Facebook帮助文档中](https://www.facebook.com/business/help/666509013483225) 的创建网站自定义受众。 在下表中选择创建受众选项：


| 项目 | 描述 |
---------|----------|
| 网站流量 | 自定义组合 |
| 包含 | <ul><li>选择 **事件** >选择 **Adobe受众管理器区段**。 这是步骤1中示例像素中ev参数的值。 请注意，如果像素尚未触发， **事件** 选 **项或Adobe受众管** 理器区段可能不会显示在Facebook UI中。</li><li>添加参数： 选择 `segID`。</li><li><p>选择包含 **运算符** 。</p><p>考虑到访客可能有资格使用多个段，这一点很重要，因为像素参数中可能有多个段ID。 使用等号(=)运算符可能不能使访客符合受众的条件，您将观察到较小的音量。</p></li><li>添加值： 输入受众管理器区段ID。</li></ul> |
| 添加新条件 | 可选设置。 |
| 最后一个 | 可选设置。 |
| 受众名称 | 建议您使用相同的受众管理器区段名称来保持一致性，除非您要向此受众添加其他条件。 |

## 步骤4 —— 在Facebook广告管理器中将受众分配给活动 {#step-4-assign-audience-to-campaign}

创建自定义受众后，将其分配给广告活动。 创建新活动或编辑现有受众，您会发现新创建的列在Facebook UI中。 如果您的广告活动将目标在访问您的网站时看到浏览器上出现像素火的用户(如果受众管理器将他们包括在区段中)。

## 概要 {#summary}

现在，您已将您的受众管理器区段分配给Facebook WCA目标，受众管理器将选择性地将Facebook WCA像素激发给给定区段的用户，其中该像素中具有相应的区段ID，以填充Facebook受众。 这会导致Facebook受众逐渐增加，向您网站上的适用受众触发的标记越多。

>[!NOTE]
>
> 如果用户掉出受众管理器区段，则受众管理器当前无法通知Facebook将用户从自定义受众中删除。

