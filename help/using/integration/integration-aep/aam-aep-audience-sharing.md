---
description: 本文描述如何在受众和Adobe Experience Platform之间共享Audience Manager。
seo-description: 本文描述如何在受众和Adobe Experience Platform之间共享Audience Manager。
seo-title: 在 Audience Manager 与 Adobe Experience Platform 之间共享受众
solution: Audience Manager
title: 在 Audience Manager 与 Adobe Experience Platform 之间共享受众
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
translation-type: tm+mt
source-git-commit: 36c820de5ccb68da6d0e519467edc869064b6e81
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 4%

---


# 在 Audience Manager 与 Adobe Experience Platform 之间共享受众 {#aam-aep-audience-sharing}

>[!NOTE]
>
> 请联系您的Adobe销售代表以解锁对此功能的访问权限。

## 概述 {#overview}

受众和Adobe Experience Platform之间的Audience Manager共享功能允许您将Audience Manager特征和区段共享到Adobe Experience Platform，反之亦然。 您需要Audience Manager [连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) ，以启用Audience Manager和Adobe Experience Platform之间的受众共享。

您可以在Experience Platform中使用Audience Manager特征和细分，向客户用户档案添加Audience Manager数据并从Experience Platform细分服务 [中受益](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)。

在Audience Manager中，您可以将Experience Platform段用于数据管理Platform用例，例如：
* 将第 [三方数据添加](/help/using/overview/data-types-collected.md#third-party-data) 到您的细分中；
* [算法建模](/help/using/features/algorithmic-models/understanding-models.md);
* 将区段激活到Experience Platform目标目录中尚不支持的 [目标](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)。

此外，您的Experience Platform细分通过核心服务共享给其他Experience Cloud [解决方案](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)。

<br> 

有关受众共享用例的概述，请参阅下表：

| **用例** | **Adobe Experience Platform** | **Audience Manager** | **核心服务** |
---------|----------|---------|---------
| **受众共享** | <ul><li>利用Audience Manager数据丰富客户用户档案</li><li>在Audience Manager细分中使用Experience Platform数据</li></ul> | <ul><li>将第三方数据添加到区段</li><li>算法建模</li><li>激活到其他目标</li></ul> | 在Adobe Target或Analytics等其他Experience Cloud解决方案中使用Experience Platform细分。 |

<br> 

## Audience Manager细分和Adobe Experience Platform特征 {#aam-segments-traits-in-aep}

您的Audience Manager特征和区段在Experience Platform中显示为 **区段** 工作流中的受众。 有关Audience Manager区段和Experience Platform特征的详细信息，请参阅：

* [分段服务概述](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Experience Platform区段构建器用户指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Adobe Experience Platform细分Audience Manager {#aep-segments-in-aam}

您在Experience Platform中创建的区段在Audience Manager界面中以特征和区段的形式显示，并包含以下构成规则：
* 特征： 特征规则是Experience Platform段的ID。
* 细分： 段由上述特征组成。

### 特征 {#aep-segments-as-aam-traits}

Audience Manager会在您的特征存储中自 **动创建名为** “Experience Platform特征”的特征文件夹。

![来自Experience Platform仪表板的特征](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

您可以在区段中将自动创建的特征与其他特征一起使用。 例如，您可以将从Experience Platform区段创建的特征与通过Audience Marketplace获得的第三方特征混 [合在一起](/help/using/features/audience-marketplace/audience-marketplace.md)。

有关从Experience Platform段自动创建的特征的示例，请参阅以下屏幕截图：

![来自Experience Platform的特征](/help/using/integration/integration-aep/assets/aep-trait.png)


| 物料编号 | 名称 | 描述 |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | 从Experience Platform区段创建的特征是作为载入的特征在Audience Manager中创建的。 |
| 2 | [!UICONTROL Data Source] | 自动创建。 从Experience Platform段自动创建的所有特征和区段都存储在数据源中 **[!UICONTROL Adobe Experience Platform Audience Sharing]**。 |
| 3 | [!UICONTROL Integration Code] | 集成代码与Experience Platform中的段ID对应。 |
| 4 | [!UICONTROL Trait Expression] | 特征表达式为 `segID = segment ID in Experience Platform`。 |
| 5 | [!UICONTROL Segments with this Trait] | 自动创建的段，该段使用此特征作为其合成。 |

<br> 

### 区段 {#aep-segments-as-aam-segments}

Audience Manager会在您的区段Experience Platform中自 **动创建名为** “存储区段”的区段文件夹。

![仪表板屏幕截图](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

有关从Experience Platform区段自动创建的区段的示例，请参阅以下屏幕截图：

![区段屏幕截图](/help/using/integration/integration-aep/assets/aep-segment.png)

| 物料编号 | 名称 | 描述 |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | 集成代码与Experience Platform中的段ID对应。 |
| 2 | [!UICONTROL Data Source] | 自动创建。 从Experience Platform段自动创建的所有特征和区段都存储在数据源中 **[!DNL Adobe Experience Platform Audience Sharing]**。 |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** 指示自动创建的区段遵循在Experience Platform中设置的合并策略。 |
| 4 | [!UICONTROL Segment Rule] | 区段由“特征”部分中描述的 [特征组成](#aep-segments-as-aam-traits)。 |

## Audience ManagerExperience Platform数据导出控制支持 {#aam-data-export-control-in-aep}

为了在Experience Platform中强制实施数据使用合规性，必须为所有适用的数据集和字段提供适当的 [数据使用标签](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html)。 此外，必 [须启用数据使](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) 用策略，以针对这些标签执行特定的营销操作，如 [数据使用标签和执行(DULE)框架所述](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework)。

在Audience Manager与Experience Platform之间的受众共享过程中，已应用于Audience Manager段的任何数据导出控制均转换为由Experience Platform数据管理确认的对等标签和营销操作，反之亦然。

>[!NOTE] 有关“数据导出控制”的更多常规信息，请参阅“数 [据导出控制”文档](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)。
此文档提供有关特定Audience Manager数据导出控件如何映射到Platform中的数据使用标签和营销操作的参考。

### 数据导出控件到数据使用标签

下表概述了特定数据导出控件如何映射到可识别的数据使用标签：

| 数据导出控制 | 数据使用标签 |
| --- | --- |
| 不能与个人身份信息一起使用 | C3: 数据不能与直接可识别信息组合或以其他方式使用 |
| 无法用于异地广告定位 | C5: 数据不能用于基于兴趣的跨站点定位内容或广告 |
| 无法用于现场广告定位 | C6: 数据不能用于现场广告定位 |
| 无法用于现场个性化 | C7: 数据不能用于内容的现场定位 |

### 将数据导出控制导出到营销操作

下表概述特定数据导出标签如何与已识别的营销操作进行映射：

| 数据导出标签 | 营销活动 |
| --- | --- |
| 此目标可能启用与个人身份信息(PII)的组合 | 与PII结合 |
| 此目标可用于非现场广告定位 | 跨站点定位 |
| 此目标可用于现场广告定位 | 现场广告 |
| 此目标可用于在线广告个性化 | 现场个性化 |

## 了解Audience Manager和Experience Platform之间的细分群体差异

细分人口数可能因Audience Manager和Experience Platform细分而异。 虽然相似或相同受众的细分数应接近，但人口差异可能是由于：

* 分段作业运行时间。 Audience Manager每天运行一次分段作业来更新接口中的数字。 此作业很少与Experience Platform中的分段作业保持一致。
* [用户档案合并规则](/help/using/features/profile-merge-rules/merge-rules-overview.md) 和Audience Manager合 [并策略中的合](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) 并规则工作方式不同，每个Experience Platform使用的标识图形也不同。 因此，预计细分群体之间会有一些差异。

>[!MORELIKETHIS]
>
>* [分段服务概述](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform区段构建器用户指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)