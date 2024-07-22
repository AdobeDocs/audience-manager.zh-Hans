---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Overview
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1470'
ht-degree: 3%

---

# [!UICONTROL Predictive Audiences]概述 {#predictive-audiences}

[!UICONTROL Predictive Audiences]可帮助您使用高级数据科学技术将未知受众实时分类为不同的角色。

>[!IMPORTANT]
>本文包含产品文档，旨在指导您完成此功能的设置和使用。 此处不包含任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

在营销环境中，人物是由访客、用户或潜在购买者定义的受众区段，他们具有一组特定特征，如人口统计信息、浏览习惯、购物历史记录等。

[!UICONTROL Predictive Audiences] 模型进一步扩展了角色这一概念的应用，允许您使用 Audience Manager 的机器学习功能将未知受众分类为不同的角色。Audience Manager可以计算未知的第一方受众与一组已知的第一方受众之间的相似性，从而帮助您做到这一点。

创建[!UICONTROL Predictive Audiences]模型时，第一步是选择希望目标受众作为分类依据的基线特征或区段。 这些特征或区段将定义您的角色。

在评估阶段，模型将为您定义为基线的每个特征或区段创建一个新的[!UICONTROL Predictive Audiences]区段。 下次Audience Manager看到目标受众中未被分类为角色（不符合任何基线特征或区段条件）的访客时，[!UICONTROL Predictive Audiences]模型将确定访客应属于哪些预测区段，并将访客添加到该区段。

您可以在[!UICONTROL Segments]页面中识别模型创建的预测区段。 每个[!UICONTROL Predictive Audiences]模型在[!UICONTROL Predictive Audiences]文件夹下都有自己的文件夹，您可以通过单击模型文件夹来查看每个模型的区段。

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## 用例 {#use-cases}

为了帮助您更好地了解如何以及何时可以使用[!UICONTROL Predictive Audiences]，以下是Audience Manager客户可以使用此功能解决的几个用例。

### 用例#1

作为一家电子商务公司的营销人员，我想将我的所有Web和移动访客分类为各种品牌亲和力类别，以便我可以个性化他们的用户体验。

### 用例#2

作为一家媒体公司的营销人员，我想按最喜爱的流派对我未经身份验证的Web和移动访客进行分类，以便我可以跨所有渠道向他们建议个性化内容。

### 用例#3

作为一家航空公司的广告商，我想确保我的受众是根据他们对旅游目的地的兴趣进行分类，以便我可以在很短的重定位窗口内向他们实时广告。

### 用例#4

作为广告商，我想实时对第一方受众进行分类，以便能够对热门新闻做出快速反应。

### 用例#5

作为营销人员，我想预测我的网站访客处于哪个客户历程阶段，例如发现、参与、购买或保留，以便我可以相应地定位他们。

### 用例#6

作为一家媒体公司，我想对受众进行分类，以便能够以较高的价格销售我的广告空间，同时为访客提供相关的广告。

## [!UICONTROL Predictive Audiences]模型的工作方式 {#how-predictive-audiences-models-work}

创建[!UICONTROL Predictive Audiences]模型时，需执行以下三个步骤：

1. 首先，选择至少两个将定义角色的特征或两个区段。
1. 然后，选择一个特征或区段，以定义要分类的目标受众。
1. 最后，选择模型的名称、将存储预测区段的数据源以及模型的[!UICONTROL Profile Merge Rule]。

### 角色选择标准 {#selection-personas}

您可以选择任何第一方特征或区段来定义角色。 但是，为获得最佳结果，这里提供了一组推荐的最佳实践：

* 选择您的角色特征或区段，以便每个角色至少拥有几百个[设备ID](../../reference/ids-in-aam.md)。
* 如果您的特征基于[跨设备ID](../../reference/ids-in-aam.md)，则可以将其包含在使用[设备ID](../../reference/ids-in-aam.md)的[配置文件合并规则](../profile-merge-rules/merge-rules-overview.md)的区段中，如[!UICONTROL Device Graph]。 这将确保有足够的[设备ID](../../reference/ids-in-aam.md)可供算法学习。
* 我们建议为您的角色选择特征或简单区段，由1到3个特征组成。
* 选择基线特征或重叠程度最低的区段。
* 确保在数字资产中捕获粒度特征。

### 目标受众的选择标准 {#selection-audience}

根据您的用例，如果要实时、批量或同时以这两种方式对用户进行分类，请选择具有大量实时和/或总人口的目标受众（[!UICONTROL trait]或[!UICONTROL segment]）。 与角色选择类似，我们建议您的目标受众[!UICONTROL trait]或[!UICONTROL segment]具有具有丰富配置文件的用户（丰富的[!UICONTROL traits]集）。

选择目标受众时，分析您的用例，并决定要分类的ID类型：[!UICONTROL device IDs]或[!UICONTROL cross-device IDs]。 您在创建模型时选择的[!UICONTROL Profile Merge Rule]定义了用于将每个用户放入预测[!UICONTROL segments]的数据。

作为最佳实践，我们建议您选择与目标受众[!UICONTROL Profile Merge Rule]具有相同配置的[!UICONTROL Profile Merge Rule]，或者选择包含目标受众的配置文件类型（设备配置文件或经过身份验证的配置文件）的配置。

### [!UICONTROL Predictive Audiences]模型训练阶段 {#model-training}

在算法能够将您的第一方受众分类为正确的角色之前，它需要根据您的数据进行自我训练。

对于您定义的每个角色，算法将分析其各自的受众，并评估其用户在过去30天内的任何实时和/或载入的特征活动。
此步骤每24小时执行一次，以确保您的第一方受众发生变化。

### [!UICONTROL Predictive Audiences]模型分类阶段 {#model-classification}

对于实时和批量受众分类，模型首先会检查用户是否属于目标受众。 如果用户符合目标受众资格且不属于任何角色，则模型将为他们分配角色资格分数。

在评估第一方受众并分配得分时，模型使用您在帐户中定义的默认&#x200B;**[!UICONTROL Profile Merge Rule]**。 最后，访客被分类为获得最高分数的角色。

![预测受众图形](assets/predictive-audiences-graph.png)

## 注意事项和限制 {#considerations}

>[!IMPORTANT]
> 在进入实施阶段之前，请仔细阅读此部分。

在配置[!UICONTROL Predictive Audiences]模型时，请牢记以下注意事项和限制：

* 您最多可以创建10个[!UICONTROL Predictive Audiences]模型。
* 对于每个模型，您最多可以选择50个基本特征/区段。
* [!UICONTROL Predictive Audiences]当前不支持第二方和第三方数据。
* [!UICONTROL Predictive Audiences]根据您的第一方特征，从您的所有第一方数据源执行受众分类。
* [!UICONTROL Predictive Audiences]的区段评估使用您在模型创建期间选择的&#x200B;**[!UICONTROL Profile Merge Rule]**。 要了解有关[!UICONTROL Profile Merge Rules]的更多信息，请参阅专用的[文档](../profile-merge-rules/merge-rules-overview.md)。
* 不支持将某些特征和区段用作基线或目标受众。 选择下列模型之一作为基线或目标受众时，[!UICONTROL Predictive Audiences]模型将无法保存：
   * 使用预测特征创建的预测特征和区段；
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md)特征或区段；
   * 算法特征；
   * 第二方和第三方特征。
* [!UICONTROL Predictive Audience] [!UICONTROL segments]不能在[!UICONTROL Audience Lab]中使用。

## [!UICONTROL Data Export Controls] {#dec}

由[!UICONTROL Predictive Audiences]模型创建的预测区段从以下第一方数据源继承了[数据导出控件](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html)：

1. 您在构建模型时选择的第一方数据源。
1. 目标受众的第一方数据源。 具体而言，构成目标受众的[!UICONTROL traits]或[!UICONTROL segments]的数据导出控件。
1. 您为模型选择的[!UICONTROL Profile Merge Rule]的[数据导出控件](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html)。

新创建的预测[!UICONTROL traits]和[!UICONTROL segments]将与上面描述的第一方数据源的并集具有相同的隐私限制。

具有不属于[!UICONTROL Predictive Audiences]区段隐私限制的其他限制的特征将从训练阶段中排除，并且不会影响模型。

## [!UICONTROL Profile Merge Rules] {#pmr}

将为所有预测区段分配您在创建模型时选择的[!UICONTROL Profile Merge Rule]。 您选择的[!UICONTROL Profile Merge Rule]很重要，原因如下：

* 它定义在模型分析具有影响力的[!UICONTROL traits]时，将用户分类为预测性[!UICONTROL segment]时，应考虑哪些设备和/或验证的配置文件。
* 它控制在模型训练步骤中应该使用哪些[!UICONTROL trait]类型（设备级别或跨设备级别）并显示为具有影响力的[!UICONTROL traits]。 预测[!UICONTROL segments]是目标受众的子集。
   * 如果目标受众是区段，我们建议您为模型选择与分配给目标受众的相同的[!UICONTROL Profile Merge Rule]，或者选择包含目标受众的配置文件类型的[!UICONTROL Profile Merge Rule]。
   * 如果目标受众是[!UICONTROL trait]，我们建议您选择一个[!UICONTROL Profile Merge Rule]，以访问与目标受众特征相同的数据类型（设备配置文件数据或跨设备配置文件数据）。
* 实时受众分类仅支持使用[!UICONTROL Current Authenticated Profiles]和[!UICONTROL No Device Profile]选项的[!UICONTROL Profile Merge Rules]。 有关详细信息，请参阅[定义的配置文件合并规则选项](../profile-merge-rules/merge-rule-definitions.md)。

选择同时使用设备数据和跨设备数据的[!UICONTROL Profile Merge Rule]，可将可用于模型训练和用户分类的[!UICONTROL traits]数量最大化到预测的[!UICONTROL segments]中。

## [!UICONTROL Role-Based Access Controls] {#rbac}

您为角色和受众分类选择的特征和区段受基于Audience Manager[角色的访问控制](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html)的约束。

Audience Manager用户只能为角色和Target受众选择他们具有[查看权限](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)的特征或区段。
