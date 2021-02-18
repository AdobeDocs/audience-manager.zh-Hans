---
description: 本文介绍如何在Audience Manager和Adobe Experience Platform之间共享受众。
seo-description: 本文介绍如何在Audience Manager和Adobe Experience Platform之间共享受众。
seo-title: 在 Audience Manager 与 Adobe Experience Platform 之间共享受众
solution: Audience Manager
title: 在 Audience Manager 与 Adobe Experience Platform 之间共享受众
keywords: AEP受众共享、AEP细分、平台细分、细分共享、受众共享、共享细分
feature: Integration with Platform
translation-type: tm+mt
source-git-commit: 62938e95fa9eed3e747fa4dabf8695c5dbefde17
workflow-type: tm+mt
source-wordcount: '1504'
ht-degree: 2%

---


# Experience Platform段与Audience Manager和其他Experience Cloud解决方案共享{#aam-aep-audience-sharing}

>[!NOTE]
>
> 请联系您的Adobe销售代表以解锁对此功能的访问权限。

## 概述 {#overview}

Audience Manager和Adobe Experience Platform之间的受众共享功能允许您将Audience Manager特征和区段共享到Adobe Experience Platform，反之亦然。 您需要[[!DNL Audience Manager Connector]](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)才能在Audience Manager和Adobe Experience Platform之间启用受众共享。

您可以在Experience Platform中使用Audience Manager特征和细分，将Audience Manager数据添加到客户用户档案，并从Experience Platform[分段服务](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)受益。

在Audience Manager中，您可以将Experience Platform区段用于数据管理 Platform使用案例，例如：
* 将[第三方数据](/help/using/overview/data-types-collected.md#third-party-data)添加到您的区段；
* [算法建模](/help/using/features/algorithmic-models/understanding-models.md);
* 将区段激活到Experience Platform[目标目录](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)中尚不支持的目标。

此外，您的Experience Platform区段会通过[核心服务](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)共享到其他Experience Cloud解决方案。

>[!IMPORTANT]
>
> * 您需要一个Audience Manager许可证才能启用上述数据管理平台使用案例。
> * 您&#x200B;*不需要* Audience Manager许可证，即可通过核心服务集成与Adobe Advertising Cloud、Adobe Target、Marketo和其他Experience Cloud解决方案共享Experience Platform细分。


<br> 

有关受众共享用例的概述，请参阅下表：

| **用例** | **Adobe Experience Platform** | **Audience Manager** | **核心服务** |
---------|----------|---------|---------
| **受众共享** | <ul><li>利用Audience Manager数据丰富客户用户档案</li><li>在Audience Manager细分中使用Experience Platform数据</li></ul> | <ul><li>将第三方数据添加到区段</li><li>算法建模</li><li>激活到其他目标</li></ul> | 在Adobe Target、Advertising Cloud或Marketo等其他Experience Cloud解决方案中使用Experience Platform细分。 |

<br> 

## Audience Manager区段和Adobe Experience Platform中的特征{#aam-segments-traits-in-aep}

您的Audience Manager特征和区段在Experience Platform中显示为区段工作流中的&#x200B;**受众**。 有关Audience Manager区段和Experience Platform特征的更多信息，请参阅：

* [分段服务概述](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Experience Platform区段生成器用户指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Adobe Experience PlatformAudience Manager{#aep-segments-in-aam}中的区段

您在Experience Platform中创建的区段在您的Audience Manager界面中以信号、特征和区段的形式显示，并具有以下合成规则：

* 信号：对于每个Experience Platform段，应以`segID = segment ID`形式显示信号。
* 特征：特征规则是Experience Platform段的ID。
* 细分：区段由上述特征组成。

### 信号{#aep-segments-as-aam-signals}

选择&#x200B;**[!UICONTROL Audience Data > Signals > General Online Data]**&#x200B;并按`SegId`搜索以查找来自Experience Platform的信号。 您可以将此屏幕用于调试目的，以检查Experience Platform与Audience Manager之间的集成是否已正确设置。

![在“信号”仪表板中查看Experience Platform信号Audience Manager](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### 特征 {#aep-segments-as-aam-traits}

Audience Manager会在您的特征存储中自动创建一个名为&#x200B;**Experience Platform特征**&#x200B;的特征文件夹。

![Experience Platform仪表板](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

您可以在区段中使用自动创建的特征以及其他特征。 例如，您可以将从Experience Platform区段创建的特征与通过[Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md)获取的第三方特征混合。

有关从Experience Platform区段自动创建的特征的示例，请参阅以下屏幕截图：

![来自Experience Platform的特征](/help/using/integration/integration-aep/assets/aep-trait.png)


| 项目编号 | 名称 | 描述 |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | 从Experience Platform区段创建的特征是作为载入的特征在Audience Manager中创建的。 |
| 2 | [!UICONTROL Data Source] | 自动创建。 从Experience Platform区段自动创建的所有特征和区段都存储在数据源&#x200B;**[!UICONTROL Adobe Experience Platform Audience Sharing]**&#x200B;中。 |
| 3 | [!UICONTROL Integration Code] | 集成代码与Experience Platform中的区段ID相对应。 |
| 4 | [!UICONTROL Trait Expression] | 特征表达式为`segID = segment ID in Experience Platform`。 |
| 5 | [!UICONTROL Segments with this Trait] | 使用此特征作为其合成的自动创建的区段。 |

<br> 

### 区段 {#aep-segments-as-aam-segments}

Audience Manager会在您的区段存储中自动创建名为&#x200B;**Experience Platform区段**&#x200B;的区段文件夹。

![仪表板屏幕截图](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

有关从Experience Platform区段自动创建的区段的示例，请参阅以下屏幕截图：

![区段屏幕截图](/help/using/integration/integration-aep/assets/aep-segment.png)

| 项目编号 | 名称 | 描述 |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | 集成代码与Experience Platform中的区段ID相对应。 |
| 2 | [!UICONTROL Data Source] | 自动创建。 从Experience Platform区段自动创建的所有特征和区段都存储在数据源&#x200B;**[!DNL Adobe Experience Platform Audience Sharing]**&#x200B;中。 |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** 指示自动创建的区段遵循在Experience Platform中设置的合并策略。 |
| 4 | [!UICONTROL Segment Rule] | 区段由[Traits部分](#aep-segments-as-aam-traits)中描述的特征组成。 |

## Audience Manager {#aam-data-export-control-in-aep}中的Experience Platform数据导出控制支持

为了在Experience Platform中强制实施数据使用合规性，必须为所有适用的数据集和字段提供适当的[数据使用标签](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html)。 此外，必须为针对这些标签的特定营销操作启用[数据使用策略](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html)，如[数据使用标签和强制(DULE)框架](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework)所述。

在Audience Manager和Experience Platform之间的受众共享过程中，已应用于Audience Manager区段的任何数据导出控制都会转换为由Experience Platform数据管理确认的对等标签和营销操作，反之亦然。

>[!NOTE]
>
>有关“数据导出控制”的更多一般信息，请参阅[“数据导出控制”文档](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)。
>
>此文档提供了有关特定Audience Manager数据导出控件如何映射到平台中的数据使用标签和营销操作的参考。

### 将数据导出控件导出到数据使用标签

下表概述了具体的数据导出控件如何映射到可识别的数据使用标签：

| 数据导出控制 | 数据使用标签 |
| --- | --- |
| 不能与个人身份信息一起使用 | C3:数据不能与直接可识别信息组合或以其他方式使用 |
| 无法用于异地广告定位 | C5:数据不能用于基于兴趣的跨站点定位内容或广告 |
| 无法用于现场广告定位 | C6:数据不能用于现场广告定位 |
| 无法用于现场个性化 | C7:数据不能用于内容的现场定位 |

### 将数据导出控制导出到营销操作

下表概述了具体数据导出标签如何映射到可识别的营销操作：

| 数据导出标签 | 营销活动 |
| --- | --- |
| 此目标可能允许结合个人身份信息(PII) | 与PII组合 |
| 此目标可用于非现场广告定位 | 跨站点定位 |
| 此目标可用于现场广告定位 | 现场广告 |
| 此目标可用于在线广告个性化 | 现场个性化 |

## 了解Audience Manager和Experience Platform之间的细分群体差异{#aep-aam-segment-population-differences}

细分数量可能因Audience Manager和Experience Platform细分而异。 虽然类似或相同受众的细分数应接近，但人口差异可能是由于以下所列因素造成的。

### Experience Platform中的细分评估

Audience Manager每天更新接口中的报告号一次。   此更新的时间很少与Experience Platform中区段评估的时间一致。

### 用户档案合并规则与合并策略之间的差异

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) 在Audience Manager和 [[!UICONTROL Merge Policies]](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) Experience Platform中，工作方式不同，每种方式使用的标识图也不同。因此，预计会出现部分群体之间的差异。

### Experience Platform中的细分组合

Adobe Experience Platform与Audience Manager之间的集成共享了许多适用于所有客户的标准[标识命名空间](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html#identity-types):ECID、IDFA、GAID、散列电子邮件地址(EMAIL_LC_SHA256)、AdCloud ID。 如果您的Experience Platform区段将其中任意一个用作合格用户档案的主要标识，则用户档案将计入Audience Manager特征和区段。

此外，在以下情况下，Audience Manager可以为您在Experience Platform段中使用的任何自定义标识命名空间注册传入实现：
* 标识标记为主&#x200B;*和*
* 您已经有一个相应的跨设备数据源在Audience Manager中。

>[!NOTE]
>
> 使用与原始电子邮件关联的身份的Experience Platform受众永远不会出现在Audience Manager中。

例如，如果您有一个Experience Platform区段“我的所有客户”，且符合条件的用户档案将是CRM ID、ECID、IDFA、原始和散列电子邮件地址，则Audience Manager中的相应区段将仅包括与CRM ID、ECID、IDFA和散列电子邮件地址关联的用户档案。 Audience Manager的细分数量将小于Experience Platform的细分数量。

![Experience Platform至Audience Manager分部分享 — 分部组成](/help/using/integration/integration-aep/assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [分段服务概述](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform区段生成器用户指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)