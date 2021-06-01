---
description: 本文介绍了如何在Audience Manager与Adobe Experience Platform之间共享受众。
seo-description: 本文介绍了如何在Audience Manager与Adobe Experience Platform之间共享受众。
seo-title: 在 Audience Manager 与 Adobe Experience Platform 之间共享受众
solution: Audience Manager
title: 在 Audience Manager 与 Adobe Experience Platform 之间共享受众
keywords: AEP受众共享， AEP区段，平台区段，区段共享，受众共享，共享区段
feature: 平台集成
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: 6900b56b4e0258ed0c4ddf94ef7b1f2c7e48a50d
workflow-type: tm+mt
source-wordcount: '1480'
ht-degree: 2%

---

# Experience Platform区段与Audience Manager和其他Experience Cloud解决方案共享{#aam-aep-audience-sharing}

>[!NOTE]
>
> 请联系您的Adobe销售代表以解锁对此功能的访问权限。

## 概述 {#overview}

在Audience Manager和Adobe Experience Platform之间共享受众功能，允许您将Audience Manager特征和区段共享到Adobe Experience Platform，反之亦然。 您需要[[!DNL Audience Manager Connector]](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)才能在Audience Manager和Adobe Experience Platform之间启用受众共享。

您可以在Experience Platform中使用Audience Manager特征和区段将Audience Manager数据添加到客户配置文件中，并从Experience Platform[分段服务](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)中受益。

在Audience Manager中，您可以将Experience Platform区段用于数据管理平台用例，例如：
* 将[第三方数据](/help/using/overview/data-types-collected.md#third-party-data)添加到您的区段；
* [算法建模](/help/using/features/algorithmic-models/understanding-models.md);
* 将区段激活到Experience Platform[目标目录](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)中尚不支持的目标。

此外，您的Experience Platform区段会通过[核心服务](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)共享到其他Experience Cloud解决方案。

>[!IMPORTANT]
>
> * 您需要拥有Audience Manager许可证才能启用上述数据管理平台用例。
> * 您&#x200B;*无需* Audience Manager许可证，即可通过核心服务集成与Adobe Advertising Cloud、Adobe Target、Marketo和其他Experience Cloud解决方案共享Experience Platform区段。


有关受众共享用例的概述，请参阅下表：

| **用例** | **Adobe Experience Platform** | **Audience Manager** | **核心服务** |
---------|----------|---------|---------|
| **受众共享** | <ul><li>使用Audience Manager数据丰富客户用户档案</li><li>在Audience Manager分段中使用Experience Platform数据</li></ul> | <ul><li>将第三方数据添加到区段</li><li>算法建模</li><li>激活到其他目标</li></ul> | 在其他Experience Cloud解决方案(如Adobe Target、Advertising Cloud或Marketo)中使用Experience Platform区段。 |

{style=&quot;table-layout:auto&quot;}

## Audience ManagerAdobe Experience Platform中的区段和特征{#aam-segments-traits-in-aep}

您的Audience Manager特征和区段在Experience Platform中显示为区段工作流中的&#x200B;**受众**。 有关Audience Manager区段和Experience Platform特征的更多信息，请参阅：

* [Segmentation Service概述](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Experience Platform区段生成器用户指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

## Adobe Experience PlatformAudience Manager中的区段{#aep-segments-in-aam}

您在Experience Platform中创建的区段在Audience Manager界面中显示为信号、特征和区段，并具有以下组合规则：

* 信号：对于每个Experience Platform区段，您应会看到`segID = segment ID`格式的信号。
* 特征：特征规则是Experience Platform区段的ID。
* 区段：区段由上述特征组成。

### 信号{#aep-segments-as-aam-signals}

选择&#x200B;**[!UICONTROL Audience Data > Signals > General Online Data]**&#x200B;并按`SegId`搜索，以查找来自Experience Platform的信号。 您可以将此屏幕用于调试目的，以检查Experience Platform与Audience Manager之间的集成是否已正确设置。

![请参阅“信号”功能板中Audience Manager的Experience Platform信号](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### 特征 {#aep-segments-as-aam-traits}

Audience Manager会在您的特征存储中自动创建名为&#x200B;**Experience Platform特征**&#x200B;的特征文件夹。

![Experience Platform仪表板的特征](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

您可以在区段中将自动创建的特征与其他特征结合使用。 例如，您可以将从Experience Platform区段创建的特征与通过[Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md)获取的第三方特征混合使用。

有关从Experience Platform区段自动创建的特征示例，请参阅以下屏幕截图：

![来自Experience Platform的特征](/help/using/integration/integration-aep/assets/aep-trait.png)


| 项目编号 | 名称 | 描述 |
---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | 从Experience Platform区段创建的特征将作为载入的特征创建在Audience Manager中。 |
| 2 | [!UICONTROL Data Source] | 自动创建。 所有从Experience Platform区段自动创建的特征和区段都存储在数据源&#x200B;**[!UICONTROL Adobe Experience Platform Audience Sharing]**&#x200B;中。 |
| 3 | [!UICONTROL Integration Code] | 集成代码与Experience Platform中的区段ID相对应。 |
| 4 | [!UICONTROL Trait Expression] | 特征表达式为`segID = segment ID in Experience Platform`。 |
| 5 | [!UICONTROL Segments with this Trait] | 自动创建的区段，使用此特征作为其组合。 |

{style=&quot;table-layout:auto&quot;}

### 区段 {#aep-segments-as-aam-segments}

Audience Manager会在区段存储中自动创建名为&#x200B;**Experience Platform区段**&#x200B;的区段文件夹。

![功能板屏幕截图](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

有关从Experience Platform区段自动创建的区段的示例，请参阅以下屏幕截图：

![区段屏幕截图](/help/using/integration/integration-aep/assets/aep-segment.png)

| 项目编号 | 名称 | 描述 |
---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | 集成代码与Experience Platform中的区段ID相对应。 |
| 2 | [!UICONTROL Data Source] | 自动创建。 所有从Experience Platform区段自动创建的特征和区段都存储在数据源&#x200B;**[!DNL Adobe Experience Platform Audience Sharing]**&#x200B;中。 |
| 1 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** 指示自动创建的区段遵循在Experience Platform中设置的合并策略。 |
| 4 | [!UICONTROL Segment Rule] | 区段由[特征部分](#aep-segments-as-aam-traits)中描述的特征组成。 |

{style=&quot;table-layout:auto&quot;}

## Audience Manager{#aam-data-export-control-in-aep}中的Experience Platform数据导出控制支持

为了在Experience Platform中强制实施数据使用合规性，必须为所有适用的数据集和字段指定适当的[数据使用标签](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html)。 此外，必须为针对这些标签的特定营销操作启用[数据使用策略](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html)，如[数据使用标签和执行(DULE)框架](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework)中所述。

在Audience Manager和Experience Platform之间的受众共享流程中，任何应用于Audience Manager区段的数据导出控制都会转换为由Experience Platform数据管理确认的对等标签和营销操作，反之亦然。

>[!NOTE]
>
>有关数据导出控制的更多常规信息，请参阅[数据导出控制文档](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)。
>
>本文档提供了有关特定Audience Manager数据导出控制如何映射到Platform中的数据使用标签和营销操作的参考。

### 将数据导出控件导出到数据使用标签

下表概述了特定数据导出控件如何映射到已识别的数据使用标签：

| 数据导出控制 | 数据使用标签 |
| --- | --- |
| 不能与个人身份信息一起使用 | C3:数据不能合并或与直接可识别信息一起使用 |
| 不能用于站外广告定位 | C5:数据不能用于基于兴趣的内容或广告的跨站点定位 |
| 不能用于现场广告定位 | C6:数据不能用于现场广告定位 |
| 不能用于现场个性化 | C7:数据不能用于内容的现场定位 |

{style=&quot;table-layout:auto&quot;}

### 将数据导出控制到营销操作

下表概述了特定数据导出标签如何映射到可识别的营销操作：

| 数据导出标签 | 营销操作 |
| --- | --- |
| 此目标可能会启用包含个人身份信息(PII)的组合 | 与PII组合 |
| 此目标可用于站外广告定位 | 跨站点定位 |
| 此目标可用于现场广告定位 | 现场广告 |
| 此目标可用于网站广告个性化 | 现场个性化 |

{style=&quot;table-layout:auto&quot;}

## 了解Audience Manager和Experience Platform之间的区段群体差异{#aep-aam-segment-population-differences}

区段人口数可能因Audience Manager和Experience Platform区段而异。 虽然相似或相同受众的区段数量应该相近，但人口差异可能是由于以下所列因素所致。

### 区段评估Experience Platform

Audience Manager每天更新界面中的报表数量一次。   此更新的时间与Experience Platform中区段评估的时间很少一致。

### 配置文件合并规则与合并策略之间的差异

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) 在Audience Manager中和 [[!UICONTROL Merge Policies]](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) 在Experience Platform中的工作方式不同，而用于每个人的身份图会有所不同。因此，预计区段人口之间会存在一些差异。

### Experience Platform中的区段组成

Adobe Experience Platform与Audience Manager之间的集成共享所有客户的许多标准[身份命名空间](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html#identity-types):ECID、IDFA、GAID、经过哈希处理的电子邮件地址(EMAIL_LC_SHA256)、AdCloud ID。 如果您的Experience Platform区段使用其中任何一个作为符合条件的用户档案的主要标识，则用户档案将被计入Audience Manager特征和区段。

>[!NOTE]
>
> Experience Platform中身份与原始电子邮件无关的受众，永远不会显示在Audience Manager中。

例如，如果您有一个Experience Platform区段“我的所有客户”，且符合条件的用户档案将为CRM ID、ECID、IDFA、原始和哈希电子邮件地址，则Audience Manager中的相应区段将仅包含无ECID、IDFA和哈希电子邮件地址键入的用户档案。 Audience Manager中的区段人口将小于Experience Platform中的区段人口。

![Experience Platform到Audience Manager的区段共享 — 区段组成](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Segmentation Service概述](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform区段生成器用户指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

