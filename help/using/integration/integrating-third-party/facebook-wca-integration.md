---
description: 本页说明了创建Facebook网站自定义受众(WCA)像素的过程，用于将基于Web的Audience Manager受众细分发送到Facebook，从而实现更高的透明度。
seo-description: 本页说明了创建Facebook网站自定义受众(WCA)像素的过程，用于将基于Web的Audience Manager受众细分发送到Facebook，从而实现更高的透明度。
seo-title: Facebook WCA集成
solution: Audience Manager
title: Facebook WCA集成
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Facebook WCA集成 {#facebook-wca-integration}

本页说明了创建Facebook网站自定义受众(WCA)像素的过程，用于将基于Web的Audience Manager受众细分发送到Facebook，从而实现更高的透明度。

## 概述 {#overview}

[Facebook网站自定义受众(WCA)](https://www.facebook.com/business/help/449542958510885) 允许您创建一个列出特定页面或在您的网站上执行特定操作的人员列表。Audience Manager支持使用URL目标在WCA中激活，您可以通过它配置基于像素的自定义集成，将基于Web的受众发送到Facebook以进行定位。

![Facebook WCA集成](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 此功能要求您在URL目标中 [选择社交平台选项的网站受众](/help/using/features/destinations/create-url-destination.md)。社交平台要求在发送到其平台时取消遮罩引用信息。请注意，这意味着目标平台/合作伙伴将能够在您的参考URL中看到信息。

## 先决条件 {#prerequisites}

1. Facebook广告帐户
2. Audience Manager细分，准备好分配到您的新Facebook目标。以下是如何在Audience [Manager UI](/help/using/features/segments/segment-builder.md) 中创建区段。
3. Adobe Experience Cloud ID Service(EID)版本4.1.0或更新版本。请在此处下载最新版本 **[](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**。
4. Audience Manager数据集成库(DIL)9.0或更新版本，可 **[从此处下载](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。或者，如果您使用 [服务器端转发(SSSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) 将数据导入Audience Manager，则必须使用AppMeasurement版本2.12或更新版本。使用 [Analytics代码管理器下载AppMeasurement](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)。

建议您使用 [Adobe Launch](https://docs.adobelaunch.com/) 或 [Adobe Dynamic Tag Management在步骤和步骤中安装或升级库](https://marketing.adobe.com/resources/help/en_US/dtm/)。

## 步骤-在Audience Manager中创建Facebook目标 {#step-1-create-facebook-destination}

在Audience Manager中创建新的URL目标，并将其命名为Facebook网站自定义受众。在创建目标时使用下面的设置。您还可以参阅 [配置URL目标](/help/using/features/destinations/create-url-destination.md) 页面。

**基本信息**

* **类别**：自定义
* **类型**：URL
* 选择 **自动填写目标映射** 复选框，然后选择 **区段ID**。

**数据导出标签**

选择此 **目标可启用与个人识别信息(PII)的组合**。

>[!NOTE]
>
> 此导出标签可防止从设备图表派生的第三方数据和数据包含在区段中。

**配置**

* **URL类型**：为社交平台选择 **网站受众**。通过选择此URL类型选项，Audience Manager不会在触发Facebook WCA像素时模糊引用URL信息。
* **序列化**：选择 **“启用**”。
* 在 **“基本URL** ”和 **“安全URL** ”字段中，输入Facebook WCA像素。
* **Delimiter（分隔符）**: ,

基本URL示例： `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

从页面触发的示例像素。此示例显示了一个符合Audience Manager细分条件的用户，该用户具有ID3401321、2993399、3263310：

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| 参数 | 描述 |
---------|----------|
| `id` | 您的Facebook像素ID，在创建受众像素时可在Facebook广告管理器UI中找到。 |
| `ev` | 事件. 这是一个随机值，一旦像素开始在站点上开火，该值就会显示在Facebook广告管理器UI中。有关详细信息，请参阅 [第步](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)中的“包含项目”。 |
| `cd[segID]` | 另一个参数，该参数在像素开始在站点上开始时开始填充Facebook广告管理器UI。`segID` 也是任意的。 |
| `%ALIAS%` | Audience Manager宏，该宏将动态替换为网站访问者符合条件、按逗号分隔的Audience Manager区段ID、 |

您的URL目标配置应如下图所示：

![目标配置](/help/using/integration/assets/facebook-wca.png)

保存目标。然后，您可以继续执行 **“区段映射”** 步骤。

## 步骤-区段映射-将区段映射到目标 {#step-2-segment-mappings}

在 [配置URL目标](/help/using/features/destinations/create-url-destination.md#) 工作流中，将适用的区段映射到新创建的目标。注意，映射值会自动填充Audience Manager区段ID。

输入结束日期(如果适用)，否则将留空以没有结束日期。

## 步骤-在Facebook Ads Manager中创建受众 {#step-3-create-audience}

请参阅 [Facebook帮助文档中的创建网站自定义受众](https://www.facebook.com/business/help/666509013483225) 。在下表中选择创建受众选项：


| 项目 | 描述 |
---------|----------|
| 网站流量 | 自定义组合 |
| 包含 | <ul><li>选择 **“活动** ”&gt;“选择 **Adobe受众管理器区段**”。这是第步中的示例像素中ev参数的值。请注意，如果该像素尚未触发，则“ **活动** ”选项或 **Adobe-Audience-Manager-区段** 可能不会显示在Facebook UI中。</li><li>添加参数：选择 `segID`。</li><li><p>选择 **包含** 运算符。</p><p>这很重要，考虑到访客可以有多个区段，因此像素参数中可能有多个区段ID。使用等于(=)运算符不能为受众限定访客资格，而且您会看到较低的音量。</p></li><li>添加值：输入Audience Manager区段ID。</li></ul> |
| 添加新条件 | 可选设置。 |
| 在最后一个 | 可选设置。 |
| 受众姓名 | 我们建议您使用相同的Audience Manager细分名称实现一致性，除非您向受众添加其他条件。 |

## 步骤-将受众分配到Facebook Ads Manager中的营销活动 {#step-4-assign-audience-to-campaign}

创建自定义受众后，将其分配给广告营销活动。创建新营销活动或编辑现有营销活动，您将发现新创建的受众在Facebook UI中列出。如果Audience Manager将其包含在区段中，则您的广告营销活动将定位在其浏览器上看到像素火的用户。

## 概要 {#summary}

现在，您已经将Audience Manager区段分配给Facebook WCA目标，Audience Manager将选择性地将Facebook WCA像素触发给给定区段的用户，以使用像素中的各个区段ID填充Facebook受众。这样，Facebook受众越多，标记就会被触发到您网站上的相应受众。

>[!NOTE]
>
> 如果用户脱离Audience Manager细分，则当前没有Audience Manager的方法可通知Facebook从自定义受众中删除该用户。

