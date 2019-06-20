---
description: 本页说明了创建Facebook网站自定义受众(WCA)像素的过程，用于将基于Web的Audience Manager受众细分发送到Facebook，从而实现更高的透明度。
seo-description: 本页说明了创建Facebook网站自定义受众(WCA)像素的过程，用于将基于Web的Audience Manager受众细分发送到Facebook，从而实现更高的透明度。
seo-title: Facebook WCA集成
solution: Audience Manager
title: Facebook WCA集成
translation-type: tm+mt
source-git-commit: 56999c1968a486bed0e2e672a4de1774d049e09d

---


# Facebook WCA Integration {#facebook-wca-integration}

本页说明了创建Facebook网站自定义受众(WCA)像素的过程，用于将基于Web的Audience Manager受众细分发送到Facebook，从而实现更高的透明度。

## 概述 {#overview}

[Facebook网站自定义受众(WCA)](https://www.facebook.com/business/help/449542958510885) 允许您创建一个列出特定页面或在您的网站上执行特定操作的人员列表。Audience Manager支持使用URL目标在WCA中激活，您可以通过它配置基于像素的自定义集成，将基于Web的受众发送到Facebook以进行定位。

![Facebook WCA集成](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> This capability requires that you select the Website audience for social platforms option in [URL destinations](/help/using/features/destinations/manage-destinations.md#configure-url-destination). 社交平台要求在发送到其平台时取消遮罩引用信息。请注意，这意味着目标平台/合作伙伴将能够在您的参考URL中看到信息。

## 先决条件 {#prerequisites}

1. Facebook广告帐户
2. Audience Manager细分，准备好分配到您的新Facebook目标。Here is [how to create a segment](/help/using/features/segments/segment-builder.md) in the Audience Manager UI.
3. Adobe Experience Cloud ID Service(EID)版本4.1.0或更新版本。Download the latest version **[here](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Audience Manager Data Integration Library (DIL) version 9.0 or newer, downloadable from **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternatively, if you use [Server-Side Forwarding (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) to import data into Audience Manager, you must use AppMeasurement version 2.12 or newer. Download AppMeasurement using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

We recommend that you install or upgrade the libraries in steps 3 and 4 using [Adobe Launch](https://docs.adobelaunch.com/) or [Adobe Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

## Step 1 - Create a Facebook Destination in Audience Manager {#step-1-create-facebook-destination}

在Audience Manager中创建新的URL目标，并将其命名为Facebook网站自定义受众。在创建目标时使用下面的设置。You can also refer to the [Configure a URL Destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) page.

**基本信息**

* **类别**：自定义
* **类型**：URL
* Select the **Auto-fill Destination Mapping** check box, then select **Segment ID**.

**数据导出标签**

Select the option **This destination may enable a combination with personally identifiable information (PII)**.

>[!NOTE]
>
> 此导出标签可防止从设备图表派生的第三方数据和数据包含在区段中。

**配置**

* **URL类型**：为社交平台选择 **网站受众**。通过选择此URL类型选项，Audience Manager不会在触发Facebook WCA像素时模糊引用URL信息。
* **序列化**：选择 **“启用**”。
* In the **Base URL** and **Secure URL** field, enter the Facebook WCA pixel.
* **Delimiter（分隔符）**: ,

Base URL example: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

从页面触发的示例像素。此示例显示了一个符合Audience Manager细分条件的用户，该用户具有ID3401321、2993399、3263310：

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| 参数 | 描述 |
---------|----------|
| `id` | 您的Facebook像素ID，在创建受众像素时可在Facebook广告管理器UI中找到。 |
| `ev` | 事件. 这是一个随机值，一旦像素开始在站点上开火，该值就会显示在Facebook广告管理器UI中。See the Include item in [Step 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), for more information. |
| `cd[segID]` | 另一个参数，该参数在像素开始在站点上开始时开始填充Facebook广告管理器UI。`segID` 也是任意的。 |
| `%ALIAS%` | Audience Manager宏，该宏将动态替换为网站访问者符合条件、按逗号分隔的Audience Manager区段ID、 |

您的URL目标配置应如下图所示：

![目标配置](/help/using/integration/assets/facebook-wca.png)

保存目标。Then, you can proceed to the **Segment Mappings** step.

## Step 2 - Segment Mappings - Map Segment to Destination {#step-2-segment-mappings}

In the [Configure URL destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) workflow, map the applicable segment to your newly created destination. 注意，映射值会自动填充Audience Manager区段ID。

输入结束日期(如果适用)，否则将留空以没有结束日期。

## Step 3 - Create an Audience within Facebook Ads Manager {#step-3-create-audience}

See [Create a Website Custom Audience](https://www.facebook.com/business/help/666509013483225) in the Facebook help documentation. 在下表中选择创建受众选项：


| 项目 | 描述 |
---------|----------|
| 网站流量 | 自定义组合 |
| 包含 | <ul><li>Select **Event** &gt; Select **Adobe-Audience-Manager-Segment**. 这是第步中的示例像素中ev参数的值。Note that if the pixel is yet to fire, the **Event** option or **Adobe-Audience-Manager-Segment** may not appear in the Facebook UI.</li><li>Add a parameter: Select `segID`.</li><li><p>Select the **contains** operator.</p><p>这很重要，考虑到访客可以有多个区段，因此像素参数中可能有多个区段ID。使用等于(=)运算符不能为受众限定访客资格，而且您会看到较低的音量。</p></li><li>添加值：输入Audience Manager区段ID。</li></ul> |
| 添加新条件 | 可选设置。 |
| 在最后一个 | 可选设置。 |
| 受众姓名 | 我们建议您使用相同的Audience Manager细分名称实现一致性，除非您向受众添加其他条件。 |

## Step 4 - Assign the Audience to a Campaign in Facebook Ads Manager {#step-4-assign-audience-to-campaign}

创建自定义受众后，将其分配给广告营销活动。创建新营销活动或编辑现有营销活动，您将发现新创建的受众在Facebook UI中列出。如果Audience Manager将其包含在区段中，则您的广告营销活动将定位在其浏览器上看到像素火的用户。

## 概要 {#summary}

现在，您已经将Audience Manager区段分配给Facebook WCA目标，Audience Manager将选择性地将Facebook WCA像素触发给给定区段的用户，以使用像素中的各个区段ID填充Facebook受众。这样，Facebook受众越多，标记就会被触发到您网站上的相应受众。

>[!NOTE]
>
> 如果用户脱离Audience Manager细分，则当前没有Audience Manager的方法可通知Facebook从自定义受众中删除该用户。

