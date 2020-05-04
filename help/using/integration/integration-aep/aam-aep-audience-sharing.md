---
description: 本文介绍如何在受众管理器和Adobe Experience Platform之间共享受众。
seo-description: 本文介绍如何在受众管理器和Adobe Experience Platform之间共享受众。
seo-title: 受众管理器与Adobe Experience Platform之间的受众共享
solution: Audience Manager
title: 受众管理器与Adobe Experience Platform之间的受众共享
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
translation-type: tm+mt
source-git-commit: 7dddf19aa3b0fc0655b1b206d9c8f0c772190601

---


# 受众管理器与Adobe Experience Platform之间的受众共享 {#aam-aep-audience-sharing}

>[!NOTE]
>
> 请联系您的Adobe销售代表以解锁对此功能的访问权限。

## 概述 {#overview}

受众管理器和Adobe Experience Platform之间的受众共享功能允许您将受众管理器特征和区段共享到Adobe Experience Platform，反之亦然。 您需要受众 [管理器连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) ，以在受众管理器和Adobe Experience Platform之间启用受众共享。

您可以使用Experience Platform中的受众管理器特征和细分，将受众管理器数据添加到您的客户用户档案，并从Experience Platform细分服务 [中受益](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)。

在受众管理器中，您可以将Experience Platform细分用于数据管理平台使用案例，例如：
* 将第 [三方数据添加](/help/using/overview/data-types-collected.md#third-party-data) 到您的细分中；
* [算法建模](/help/using/features/algorithmic-models/understanding-models.md);
* 将您的区段激活到Experience Platform目标目录中尚不支持的 [目标](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)。

此外，您的Experience Platform细分通过核心服务共享给其他Experience Cloud解 [决方案](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)。

<br> 

有关受众共享用例的概述，请参阅下表：

| **用例** | **Adobe Experience Platform** | **Audience Manager** | **核心服务** |
---------|----------|---------|---------
| **受众共享** | <ul><li>利用受众经理数据丰富客户用户档案</li><li>将受众管理器数据用于Experience Platform细分</li></ul> | <ul><li>将第三方数据添加到区段</li><li>算法建模</li><li>激活到其他目标</li></ul> | 在Experience Cloud解决方案(如Adobe目标或Analytics)中使用Experience Platform细分。 |

<br> 

## 受众管理器在Adobe Experience Platform中的细分和特征 {#aam-segments-traits-in-aep}

您的受众管理器特征和区段在Experience Platform中显示为 **区段** 工作流中的受众。 有关Experience Platform中受众管理器细分和特征的更多信息，请参阅：

* [分段服务概述](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Experience Platform Segment Builder用户指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [受众管理器连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## 受众管理器中的Adobe Experience Platform细分 {#aep-segments-in-aam}

您在Experience Platform中创建的区段会作为特征和区段显示在受众管理器界面中，具有以下组合规则：
* 特征： 特征规则是Experience Platform区段的ID。
* 细分： 段由上述特征组成。

### 特征 {#aep-segments-as-aam-traits}

受众管理器在您的特征存储中自 **动创建名为Experience Platform** Traits的特征文件夹。

![Experience Platform的特征仪表板](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

您可以在区段中将自动创建的特征与其他特征一起使用。 例如，您可以将从Experience Platform细分创建的特征与通过受众市场获得的第三方特征 [混合使用](/help/using/features/audience-marketplace/audience-marketplace.md)。

有关从Experience Platform区段自动创建的特征的示例，请参阅以下屏幕截图：

![Experience Platform的特点](/help/using/integration/integration-aep/assets/aep-trait.png)


| 物料编号 | 名称 | 描述 |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | 通过Experience Platform区段创建的特征在受众管理器中创建为载入的特征。 |
| 2 | [!UICONTROL Data Source] | 自动创建。 从Experience Platform区段自动创建的所有特征和区段都存储在数据源中 **[!UICONTROL Adobe Experience Platform Audience Sharing]**。 |
| 3 | [!UICONTROL Integration Code] | 集成代码与Experience Platform中的区段ID相对应。 |
| 4 | [!UICONTROL Trait Expression] | 特征表达式为 `segID = segment ID in Experience Platform`。 |
| 5 | [!UICONTROL Segments with this Trait] | 自动创建的段，该段使用此特征作为其合成。 |

<br> 

### 区段 {#aep-segments-as-aam-segments}

受众管理器会在您的区段存储中自 **动创建一个名为** “Experience Platform Segments”的区段文件夹。

![仪表板屏幕截图](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

有关从Experience Platform区段自动创建的区段的示例，请参阅以下屏幕截图：

![区段屏幕截图](/help/using/integration/integration-aep/assets/aep-segment.png)

| 物料编号 | 名称 | 描述 |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | 集成代码与Experience Platform中的区段ID相对应。 |
| 2 | [!UICONTROL Data Source] | 自动创建。 从Experience Platform区段自动创建的所有特征和区段都存储在数据源中 **[!DNL Adobe Experience Platform Audience Sharing]**。 |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** 指示自动创建的区段遵循在Experience Platform中设置的合并策略。 |
| 4 | [!UICONTROL Segment Rule] | 区段由“特征”部分中描述的 [特征组成](#aep-segments-as-aam-traits)。 |

## 了解受众经理与Experience Platform之间的细分群体差异

受众经理和Experience Platform细分的细分群体数量可能有所不同。 虽然相似或相同受众的细分数应接近，但人口差异可能是由于：

* 分段作业运行时间。 受众管理器每天运行一次分段作业来更新界面中的数字。 此作业很少与Experience Platform中的分段作业保持一致。
* [用户档案合并规则](/help/using/features/profile-merge-rules/merge-rules-overview.md) (在受众管理器中 [)和合并策略](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) （在Experience Platform中）的工作方式不同，每种使用的标识图形也不同。 因此，预计细分群体之间会有一些差异。

>[!MORELIKETHIS]
>
>* [分段服务概述](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform Segment Builder用户指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [受众管理器连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)