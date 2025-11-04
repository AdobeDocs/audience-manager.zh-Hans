---
description: 了解如何启用数据共享以及如何在Audience Manager和Adobe Experience Platform之间共享受众
solution: Audience Manager
title: Experience Platform区段与Audience Manager和其他Experience Cloud解决方案共享
keywords: AEP受众共享、AEP区段、Platform区段、区段共享、受众共享、共享区段、AAM AEP区段共享
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 1%

---

# Experience Platform区段与Audience Manager和其他Experience Cloud解决方案共享

## 概述 {#overview}

通过Audience Manager和Adobe Experience Platform之间的受众共享功能，您可以将Audience Manager特征和区段共享到Adobe Experience Platform，将Experience Platform区段共享到Audience Manager。

您需要Experience Platform中的[[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)和[Experience Cloud受众](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html)目标才能在Audience Manager和Adobe Experience Platform之间启用受众共享。

您可以使用Experience Platform中的Audience Manager特征和区段将Audience Manager数据添加到您的客户配置文件中，并从Experience Platform [分段服务](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=en)中受益。

在Audience Manager中，您可以将Experience Platform区段用于Data Management Platform用例，例如：

* 将[第三方数据](/help/using/overview/data-types-collected.md#third-party-data)添加到您的区段；
* [算法建模](/help/using/features/algorithmic-models/understanding-models.md)；
* 将区段激活到Experience Platform [目标目录](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)中尚不受支持的目标。

此外，您的Experience Platform区段已通过[核心服务](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html)共享到其他Experience Cloud解决方案。

>[!IMPORTANT]
>
> * 您需要拥有Audience Manager许可证才能启用上述数据管理平台用例。
> * 您&#x200B;*不需要* Audience Manager许可证即可通过核心服务集成与Adobe Advertising Cloud、Adobe Target、Marketo和其他Experience Cloud解决方案共享Experience Platform区段。

请参阅下表，了解受众共享用例的概述：

| **用例** | **Adobe Experience Platform** | **Audience Manager** | **核心服务** |
|---------|----------|---------|---------|
| **受众共享** | <ul><li>利用Audience Manager数据丰富客户配置文件</li><li>在Experience Platform分段中使用Audience Manager数据</li></ul> | <ul><li>将第三方数据添加到区段</li><li>算法建模</li><li>激活到其他目标</li></ul> | 在其他Experience Cloud解决方案(如Adobe Target、Advertising Cloud或Marketo)中使用Experience Platform区段。 |

{style="table-layout:auto"}

## Adobe Experience Platform中的Audience Manager区段和特征 {#aam-segments-traits-in-aep}

以下部分介绍了如何启用从Audience Manager到Experience Platform的数据共享，以及如何在Experience Platform中使用Audience Manager特征和区段。

### 启用从Audience Manager到Experience Platform的数据共享 {#enable-aam-to-aep-data}

要将区段和特征从Audience Manager发送到Experience Platform，必须在Experience Platform源目录中设置Audience Manager源连接器。 这是一个自助式工作流程，无需Adobe客户关怀或工程团队的参与。 要设置Audience Manager源连接器，请阅读：

* [Audience Manager源](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
* [在UI中创建Adobe Audience Manager源连接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=en)

>[!IMPORTANT]
>
>Adobe鼓励客户在不选择&#x200B;**[!UICONTROL Select all segments]**&#x200B;和&#x200B;**[!UICONTROL Select all traits]**&#x200B;选项的情况下配置连接，如下所示。 当您首次使用Audience Manager源将Audience Manager区段发送到Platform时，大量的Audience Manager区段人口的摄取会直接影响您的总配置文件计数。 这意味着选择所有区段可能会导致配置文件计数超过您的许可证使用授权。
>
>![该屏幕快照显示在工作流中取消选中以连接到Audience Manager源连接器的“选择所有区段”和“选择所有特征”选项。](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### 在Experience Platform中使用Audience Manager特征和区段 {#use-aam-data-in-aep}

设置Audience Manager源连接器以从Audience Manager导入特征和区段后，Audience Manager数据在Experience Platform中的区段工作流中显示为&#x200B;**受众**。 有关Experience Platform中Audience Manager区段和特征的更多信息，请阅读：

* [分段服务概述](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
* [Experience Platform Segment Builder用户指南](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)

## Audience Manager中的Adobe Experience Platform区段 {#aep-segments-in-aam}

以下部分介绍了如何启用从Experience Platform到Audience Manager的数据共享，以及如何在Audience Manager中使用Experience Platform区段。

### 启用从Experience Platform到Audience Manager的数据共享 {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> 此部分介绍了从Experience Platform到Audience Manager的旧版区段共享集成。 您现在可以设置此集成，而无需Adobe客户代表的支持。 有关详细信息，请阅读[Experience Cloud受众](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html)目标文档。

>[!NOTE]
>
> 请联系您的Adobe客户成功经理或客户关怀团队以解锁此功能的访问权限。

要将区段从Experience Platform发送到Audience Manager，您必须联系客户关怀部门或您的客户成功经理。 客户关怀团队和客户支持管理团队必须提交票证(请参阅模板票证AAM-52354)以启用从Platform到Audience Manager的连接。

请务必共享从Platform到Audience Manager的数据传输计划，以确保正确设置了连接。 例如，如果您需要为发送到Adobe Target的区段共享区域数据，则需要在票证中传达此信息。 从Experience Platform到Audience Manager的数据共享连接是在提交请求后的6个工作日内设置的。

### 在Audience Manager中使用Experience Platform区段 {#use-aep-data-in-aam}

您在Experience Platform中创建的区段在Audience Manager界面中显示为信号、特征和区段，并遵循以下构成规则：

* 信号：对于每个Experience Platform区段，您应会看到格式为`segID = segment ID`的信号。
* 特征：特征规则是Experience Platform区段的ID。
* 区段：区段包含上述特征。

### 信号 {#aep-segments-as-aam-signals}

选择&#x200B;**[!UICONTROL Audience Data > Signals > General Online Data]**&#x200B;并按`SegId`进行搜索以查找来自Experience Platform的信号。 您可以使用此屏幕进行调试，以检查Experience Platform与Audience Manager之间的集成是否已正确设置。

![在信号仪表板中查看Audience Manager中的Experience Platform信号](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### 特征 {#aep-segments-as-aam-traits}

Audience Manager会在您的特征存储中自动创建一个名为&#x200B;**Experience Platform特征**&#x200B;的特征文件夹。

来自Experience Platform仪表板的![特征](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

您可以在区段中将自动创建的特征与其他特征结合使用。 例如，您可以将从Experience Platform区段创建的特质与通过[Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md)获得的第三方特征混合在一起。

有关自动从Experience Platform区段创建的特征的示例，请参阅下面的屏幕快照：

来自Experience Platform的![特征](/help/using/integration/integration-aep/assets/aep-trait.png)


| 项目编号 | 名称 | 描述 |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | 从Experience Platform区段创建的特征，将作为载入的特征在Audience Manager中创建。 |
| 2 | [!UICONTROL Data Source] | 已自动创建。 自动从Experience Platform区段创建的所有特征和区段都存储在数据源&#x200B;**[!UICONTROL Adobe Experience Platform Audience Sharing]**&#x200B;中。 |
| 3 | [!UICONTROL Integration Code] | 集成代码对应于Experience Platform中的区段ID。 |
| 4 | [!UICONTROL Trait Expression] | 特征表达式为`segID = segment ID in Experience Platform`。 |
| 5 | [!UICONTROL Segments with this Trait] | 一个自动创建的区段，它使用此特征作为其合成。 |

{style="table-layout:auto"}

### 区段 {#aep-segments-as-aam-segments}

Audience Manager会在您的区段存储中自动创建一个名为&#x200B;**Experience Platform区段**&#x200B;的区段文件夹。

![仪表板的屏幕截图](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

有关自动从Experience Platform区段创建的区段的示例，请参阅下面的屏幕快照：

![区段的屏幕快照](/help/using/integration/integration-aep/assets/aep-segment.png)

| 项目编号 | 名称 | 描述 |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | 集成代码对应于Experience Platform中的区段ID。 |
| 2 | [!UICONTROL Data Source] | 已自动创建。 自动从Experience Platform区段创建的所有特征和区段都存储在数据源&#x200B;**[!DNL Adobe Experience Platform Audience Sharing]**&#x200B;中。 |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]**&#x200B;指示自动创建的区段遵循Experience Platform中设置的合并策略。 |
| 4 | [!UICONTROL Segment Rule] | 该区段包含[特征部分](#aep-segments-as-aam-traits)中描述的特征。 |

{style="table-layout:auto"}

## Experience Platform中的Audience Manager数据导出控制支持 {#aam-data-export-control-in-aep}

为了在Experience Platform中强制实施数据使用合规性，必须为所有适用的数据集和字段指定适当的[数据使用标签](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html)。 此外，必须启用[数据使用策略](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html#)以便针对这些标签执行特定的营销操作，如[数据使用标签和执行(DULE)框架](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html#dule-framework)中所述。

在Audience Manager和Experience Platform之间的受众共享流程中，已应用于Audience Manager区段的任何数据导出控件都会转换为Experience Platform数据管理识别的等效标签和营销操作，反之亦然。

>[!NOTE]
>
>有关数据导出控制的详细信息，请参阅[数据导出控制文档](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html)。
>
>本文档提供了有关如何将特定的Audience Manager数据导出控件映射到Platform中的数据使用标签和营销操作的参考。

### 数据导出控件到数据使用标签

下表概述了特定数据导出控件如何映射到已识别的数据使用标签：

| 数据导出控制 | 数据使用情况标签 |
| --- | --- |
| 无法与个人身份信息一起使用 | C3：数据不能与直接可识别的信息组合或一起使用 |
| 无法用于站外广告定位 | C5：数据无法用于基于兴趣的跨站点内容或广告定位 |
| 无法用于现场广告定位 | C6：数据无法用于现场广告定位 |
| 无法用于现场个性化 | C7：数据无法用于现场内容定位 |

{style="table-layout:auto"}

### 将数据导出控件导出到营销操作

下表概述了特定数据导出标签如何映射到已识别的营销操作：

| 数据导出标签 | 营销操作 |
| --- | --- |
| 此目标可能会启用与个人身份信息(PII)的组合 | 与PII结合 |
| 此目标可用于非现场广告定位 | 跨站点定位 |
| 此目标可用于现场广告定位 | 现场Advertising |
| 此目标可用于现场广告个性化 | 现场Personalization |

{style="table-layout:auto"}

## 了解Audience Manager和Experience Platform之间的区段人口差异 {#aep-aam-segment-population-differences}

区段人口数量可能因Audience Manager区段和Experience Platform区段而异。 虽然类似或相同受众的区段数字应该接近，但群体的差异可能是由下面列出的因素造成的。

### Experience Platform中的区段评估

Audience Manager每天会更新界面中的报表编号一次。 此更新的时间很少与Experience Platform中区段评估的时间一致。

### 配置文件合并规则和合并策略之间的差异

Audience Manager中的[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md)与Experience Platform中的[[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html)工作方式不同，且用于每个人的标识图也不同。 因此，预计区段人口之间存在一些差异。

>[!NOTE]
>
> 将区段从Experience Platform共享到Audience Manager时，您的Platform组织[默认合并策略](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en#default-merge-policy)优先于与Audience Manager共享的区段[使用的](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#merge-policies)合并策略。 例如，如果共享区段的合并策略允许[ID拼接](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=en#configure)，而组织的默认合并策略不允许，则可能会导致平台和Audience Manager之间的群体差异。

### Experience Platform中的区段构成

Adobe Experience Platform与Audience Manager之间的集成为所有客户共享大量标准的[身份命名空间](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#identity-types)：ECID、IDFA、GAID、哈希电子邮件地址(EMAIL_LC_SHA256)、AdCloud ID。 如果您的Experience Platform区段将任何此类区段用作符合条件的用户档案的主要标识，则用户档案将被计入Audience Manager特征和区段中。

>[!NOTE]
>
> Experience Platform中标识与原始电子邮件不相关的受众永远不会出现在Audience Manager中。

例如，如果您的Experience Platform区段为“我的所有客户”，并且符合条件的用户档案为CRM ID、ECID、IDFA、原始电子邮件地址和哈希电子邮件地址，则Audience Manager中的相应区段将仅包含以ECID、IDFA和哈希电子邮件地址作为关键字的用户档案。 Audience Manager中的区段人口将小于Experience Platform中的区段人口。

![Experience Platform到Audience Manager区段共享 — 区段组合](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [分段服务概述](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform Segment Builder用户指南](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
