---
description: 本文介绍如何在受众和Adobe Experience Platform之间共享Audience Manager。
seo-description: 本文介绍如何在受众和Adobe Experience Platform之间共享Audience Manager。
seo-title: 在 Audience Manager 与 Adobe Experience Platform 之间共享受众
solution: Audience Manager
title: 在 Audience Manager 与 Adobe Experience Platform 之间共享受众
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
feature: Integration with Platform
translation-type: tm+mt
source-git-commit: b3ff5ca68022cc30632d6b647ffde507533b5ddf
workflow-type: tm+mt
source-wordcount: '1441'
ht-degree: 3%

---


# 在 Audience Manager 与 Adobe Experience Platform 之间共享受众 {#aam-aep-audience-sharing}

>[!NOTE]
>
> 请与Adobe销售代表联系以解锁对此功能的访问权限。

## 概述 {#overview}

Audience Manager和Adobe Experience Platform之间的受众共享功能允许您将Audience Manager特征和区段共享到Adobe Experience Platform，反之亦然。 您需要[[!DNL Audience Manager Connector]](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) ，以启用Audience Manager与Adobe Experience Platform之间的受众共享。

您可以在Experience Platform中使用Audience Manager特征和细分，向客户用户档案添加Audience Manager数据并从Experience Platform细分服务 [中受益](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)。

在Audience Manager中，您可以将Experience Platform细分用于数据管理平台用例，例如：
* 将第 [三方数据添加](/help/using/overview/data-types-collected.md#third-party-data) 到您的细分中；
* [算法建模](/help/using/features/algorithmic-models/understanding-models.md);
* 将区段激活到Experience Platform目标目录中尚不支持的 [目标](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)。

此外，您的Experience Platform细分通过核心服务共享给其他Experience Cloud [解决方案](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)。

<br> 

有关受众共享用例的概述，请参阅下表：

| **用例** | **Adobe Experience Platform** | **Audience Manager** | **核心服务** |
---------|----------|---------|---------
| **受众共享** | <ul><li>利用Audience Manager数据丰富客户用户档案</li><li>在Audience Manager细分中使用Experience Platform数据</li></ul> | <ul><li>将第三方数据添加到区段</li><li>算法建模</li><li>激活到其他目标</li></ul> | 在其他Experience Platform解决方案(如Adobe Target或分析)中使用Experience Cloud细分。 |

<br> 

## Adobe Experience PlatformAudience Manager区段及特征 {#aam-segments-traits-in-aep}

您的Audience Manager特征和区段在Experience Platform中显示为 **区段** 工作流中的受众。 有关Audience Manager区段和Experience Platform特征的详细信息，请参阅：

* [分段服务概述](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Experience Platform区段构建器用户指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Adobe Experience PlatformAudience Manager {#aep-segments-in-aam}

您在Experience Platform中创建的区段在Audience Manager界面中以信号、特征和区段的形式显示，并包含以下构成规则：

* 信号： 对于每个Experience Platform段，您应在表单中看到信号 `segID = segment ID`。
* 特征： 特征规则是Experience Platform段的ID。
* 细分： 段由上述特征组成。

### 信号 {#aep-segments-as-aam-signals}

选 **[!UICONTROL Audience Data > Signals > General Online Data]** 择并搜索 `SegId` 以查找来自Experience Platform的信号。 您可以将此屏幕用于调试目的，检查Experience Platform和Audience Manager之间的集成是否已正确设置。

![在信号Experience Platform中查看Audience Manager信号](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

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

>[!NOTE]
>
>有关“数据导出控制”的更多常规信息，请参阅“数 [据导出控制”文档](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)。
此文档提供有关特定Audience Manager数据导出控制如何映射到平台中的数据使用标签和营销操作的参考。

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

## 了解Audience Manager和Experience Platform之间的细分群体差异 {#aep-aam-segment-population-differences}

细分人口数可能因Audience Manager和Experience Platform细分而异。 虽然相似或相同受众的细分数应接近，但人口差异可能是由于以下所列因素造成的。

### Experience Platform中的细分评估

Audience Manager每天更新接口中的报告号一次。   此更新的时间与Experience Platform中的细分评估时间很不一致。

### 用户档案合并规则与合并策略之间的差异

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) 在Audience Manager和 [[!UICONTROL Merge Policies]](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) Experience Platform中，工作方式各不相同，每个人使用的标识图也各不相同。 因此，预计细分群体之间会有一些差异。

### Experience Platform中的细分组成

Adobe Experience Platform和Audience Manager之间的集成为所有客户共 [享了许多标](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html#identity-types) 准身份命名空间: ECID、IDFA、GAID、散列电子邮件地址(EMAIL_LC_SHA256)、AdCloud ID，等等。 如果您的Experience Platform区段将其中任何一个用作合格用户档案的主要标识，则用户档案计入Audience Manager特征和区段。

此外，Audience Manager可以为您在Experience Platform段中使用的任何自定义标识命名空间注册传入的实现，前提是您已经在键入该标识符的Audience Manager中具有相应的数据源。

>[!NOTE]
>
> 受众在Experience Platform中，与原始电子邮件关联的身份永远不会出现在Audience Manager中。

例如，如果您有一个Experience Platform区段“我的所有客户”，且符合条件的用户档案将是CRM ID、ECID、IDFA、原始和散列电子邮件地址，则Audience Manager中的相应区段将仅包括已键入CRM ID、ECID、IDFA和散列电子邮件地址的用户档案。 Audience Manager的细分人口将比Experience Platform的细分人口少。

![Experience Platform至Audience Manager分部分享——分部组成](/help/using/integration/integration-aep/assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [分段服务概述](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform区段构建器用户指南](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
