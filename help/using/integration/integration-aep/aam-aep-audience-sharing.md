---
description: 本文介绍如何在Audience manager和Adobe Experience Platform之间共享受众。
seo-description: 本文介绍如何在Audience manager和Adobe Experience Platform之间共享受众。
seo-title: Audience manager与Adobe Experience Platform之间的受众共享
solution: Audience Manager
title: Audience manager与Adobe Experience Platform之间的受众共享
keywords: AEP受众共享、AEP细分、平台细分
translation-type: tm+mt
source-git-commit: e081e31380d4600883f927b5ecef3b38be2a676e

---


# Audience manager与Adobe Experience Platform之间的受众共享 {#aam-aep-audience-sharing}

>[!NOTE]
>
>本页包含测试版文档，其中描述了Audience Manager和 *Adobe* Experience Platform客户可用的功能。 本文档可能会在最终产品发布之前进行更改。
>
> 请联系Adobe销售代表以解锁对此功能的访问权限。

## 概述 {#overview}

Audience manager和Adobe Experience Platform之间的受众共享功能允许您将Audience manager特征和区段共享到Adobe Experience Platform，反之亦然。

您可以使用Experience platform中的Audience manager特征和细分将Audience manager数据添加到客户档案中并从Experience platform细分服务中 [受益](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)。

在Audience Manager中，您可以将Experience platform细分用于数据管理平台使用案例，例如：
* 将第 [三方数据添加](/help/using/overview/data-types-collected.md#third-party-data) 到您的细分；
* [算法建模](/help/using/features/algorithmic-models/understanding-models.md);
* 将区段激活到Experience platform当前不支持的目标。

此外，您的Experience platform细分会通过核心服务共享到其他Experience cloud解 [决方案](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)。

<br> 

有关受众共享用例的概述，请参阅下表：

| **用例** | **Adobe Experience Platform** | **Audience Manager** | **核心服务** |
---------|----------|---------|---------
| **受众共享** | <ul><li>利用Audience manager数据丰富客户档案</li><li>在Experience platform细分中使用Audience Manager数据</li></ul> | <ul><li>将第三方数据添加到区段</li><li>算法建模</li><li>激活到其他目标</li></ul> | 在Adobe target或Analytics等其他Experience cloud解决方案中使用Experience platform细分。 |

<br> 

## Adobe Experience Platform中的Audience manager细分和特征 {#aam-segments-traits-in-aep}

您的Audience Manager特征和区段在Experience Platform中显示为区段 **工作流** 中的“受众”。 有关Audience Manager细分和Experience Platform中特征的详细信息，请参阅：

* [分段服务概述](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)
* [Experience Platform Segment Builder用户指南](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segment-builder-guide.md)

<br> 

## Audience manager中的Adobe Experience platform细分 {#aep-segments-in-aam}

您在Experience platform中创建的区段在Audience manager界面中显示为特征和区段，具有以下构成规则：
* 特征：特征规则是Experience platform区段的ID。
* 细分：段由上述特征组成。

### 特征 {#aep-segments-as-aam-traits}

Audience manager会在您的特征存储中自动创建一个名 **为Experience Platform Traits** 的特征文件夹。

![Experience platform仪表板中的特征](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

您可以在区段中与其他特征一起使用自动创建的特征。 例如，您可以将从Experience Platform细分创建的特征与通过Audience Marketplace获得的第三方特征混 [合在一起](/help/using/features/audience-marketplace/audience-marketplace.md)。

有关从Experience Platform区段自动创建的特征示例，请参阅以下屏幕截图：

![Experience platform的特点](/help/using/integration/integration-aep/assets/aep-trait.png)


| 项目编号 | 名称 | 描述 |
---------|----------|---------
| 1 | 特征类型 | 从Experience Platform区段创建的特征是作为Audience manager中的已载入特征创建的。 |
| 2 | 数据源 | 自动创建。 从Experience Platform细分自动创建的所有特征和细分都存储在数据源 **Adobe Experience Platform Audience Sharing中**。 |
| 3 | 集成代码 | 集成代码与Experience Platform中的区段ID相对应。 |
| 4 | 特征表达 | 特征表达式为 `segID = segment ID in Experience Platform`。 |
| 5 | 具有此特征的区段 | 自动创建的段，该段使用此特征作为其合成。 |

<br> 

### 区段 {#aep-segments-as-aam-segments}

Audience manager会在您的区段存储中自动创建一个名为 **Experience Platform Segments的区段文件** 。

![功能板屏幕截图](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

有关从Experience Platform区段自动创建的区段的示例，请参阅以下屏幕截图：

![区段屏幕截图](/help/using/integration/integration-aep/assets/aep-segment.png)

| 项目编号 | 名称 | 描述 |
---------|----------|---------
| 1 | 集成代码 | 集成代码与Experience Platform中的区段ID相对应。 |
| 2 | 数据源 | 自动创建。 从Experience Platform细分自动创建的所有特征和细分都存储在数据源 **Adobe Experience Platform Audience Sharing中**。 |
| 3 | 个人资料合并规则 | **外部合并策略** 表示自动创建的区段遵循在Experience platform中设置的合并策略。 |
| 4 | 区段规则 | 段由“特征”部分中描述的特 [征组成](#aep-segments-as-aam-traits)。 |