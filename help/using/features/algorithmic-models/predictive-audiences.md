---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-title: Predictive Audiences 概述
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: 算法模型
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1505'
ht-degree: 8%

---

# [!UICONTROL Predictive Audiences] 概述 {#predictive-audiences}

[!UICONTROL Predictive Audiences] 可以帮助您使用高级数据科学技术将未知受众实时分类为不同的角色。

>[!IMPORTANT]
>本文包含旨在指导您完成此功能的设置和使用的产品文档。 这里没有任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

在营销环境中，角色是指由具有一系列相同特征（例如人口统计特征、浏览习惯、购物历史记录等）的访客、用户或潜在购买者构成的一个受众区段。

[!UICONTROL Predictive Audiences] 模型进一步扩展了角色这一概念的应用，允许您使用 Audience Manager 的机器学习功能将未知受众分类为不同的角色。Audience Manager 可以计算未知的第一方受众与一组已知的第一方受众之间的相似性，从而帮助您做到这一点。

创建[!UICONTROL Predictive Audiences]模型时，第一步是选择希望目标受众按其分类的基线特征或区段。 这些特征或区段将定义您的角色。

在评估阶段，模型会为您定义为基线的每个特征或区段创建一个新的[!UICONTROL Predictive Audiences]区段。 下次Audience Manager从目标受众查看未针对某个角色进行分类的访客（不符合任何基线特征或区段的资格）时，[!UICONTROL Predictive Audiences]模型将确定访客应属于的预测区段，并将访客添加到该区段。

您可以在[!UICONTROL Segments]页面中识别模型创建的预测区段。 每个[!UICONTROL Predictive Audiences]模型的[!UICONTROL Predictive Audiences]文件夹下都有其自己的文件夹，您可以通过单击模型文件夹来查看每个模型的区段。

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## 用例 {#use-cases}

为了帮助您更好地了解如何使用[!UICONTROL Predictive Audiences]以及何时使用，以下是Audience Manager客户可通过使用此功能解决的一些用例。

### 用例#1

作为一家电子商务公司的营销人员，我想将所有的Web访客和移动设备访客划分到不同的品牌亲和度类别，以便我可以个性化其用户体验。

### 用例#2

作为一家媒体公司的营销人员，我希望按最喜爱的流派对未经身份验证的Web访客和移动设备访客进行分类，以便我可以在所有渠道向他们建议个性化内容。

### 用例#3

作为一家航空公司的广告商，我想确保根据受众对旅游目的地的兴趣对其进行分类，以便我能够在一个较短的重定向窗口内向他们实时投放广告。

### 用例#4

作为广告商，我希望实时对第一方受众进行分类，以便能够对趋势新闻做出快速反应。

### 用例#5

作为营销人员，我想预测我的网站访客处于哪个客户旅程阶段，如发现、参与、购买或维系，以便我可以相应地定位他们。

### 用例#6

作为一家媒体公司，我希望对受众进行分类，以便我能够以优惠价格销售广告空间，同时为访客提供相关广告。

## [!UICONTROL Predictive Audiences]模型的工作原理 {#how-predictive-audiences-models-work}

创建[!UICONTROL Predictive Audiences]模型时，需要完成以下三个步骤：

1. 首先，您至少选择两个特征或两个将定义角色的区段。
1. 然后，您可以选择一个特征或区段来定义要分类的目标受众。
1. 最后，为模型选择名称、将存储预测区段的数据源和[!UICONTROL Profile Merge Rule]模型。

### 角色的选择标准 {#selection-personas}

您可以选择任何第一方特征或区段来定义角色。 但是，为了获得最佳结果，以下是一组推荐的最佳实践：

* 选择您的角色特征或区段，以便每个角色至少拥有几百个[设备ID](../../reference/ids-in-aam.md)。
* 如果您的特征基于[跨设备ID](../../reference/ids-in-aam.md)，则可以使用使用[设备ID](../../reference/ids-in-aam.md)的[配置文件合并规则](../profile-merge-rules/merge-rules-overview.md)（如[!UICONTROL Device Graph]）的区段将它们包装在区段中。 这将确保有足够的[设备ID](../../reference/ids-in-aam.md)可供算法学习。
* 我们建议为您的角色选择特征或简单区段，包括1到3个特征。
* 选择重叠程度最低的基线特征或区段。
* 确保在数字属性中捕获粒度特征。

### 目标受众的选择标准 {#selection-audience}

根据您的用例，无论您是要对用户进行实时、批量分类，还是同时对用户进行分类，都应选择具有大量实时和/或总群体的目标受众（[!UICONTROL trait]或[!UICONTROL segment]）。 与角色选择类似，我们建议目标受众[!UICONTROL trait]或[!UICONTROL segment]具有富配置文件（富集[!UICONTROL traits]）的用户。

选择目标受众时，分析您的用例并确定要分类的ID类型：[!UICONTROL device IDs]或[!UICONTROL cross-device IDs]。 在创建模型时选择的[!UICONTROL Profile Merge Rule]定义将用于将每个用户放入预测[!UICONTROL segments]的数据。

作为最佳实践，我们建议选择与目标受众[!UICONTROL Profile Merge Rule]具有相同配置的[!UICONTROL Profile Merge Rule]，或者选择包含目标受众的配置文件类型（设备配置文件或已验证的配置文件）的。

### [!UICONTROL Predictive Audiences] 模型培训阶段 {#model-training}

在算法将第一方受众分类为正确的角色之前，它需要根据您的数据进行自我培训。

对于您定义的每个角色，算法会分析其各自的受众，并评估其用户在过去30天内的任何实时和/或已载入的特征活动。
此步骤每24小时进行一次，以考虑第一方受众中的更改。

### [!UICONTROL Predictive Audiences] 模型分类阶段 {#model-classification}

对于实时受众和批量受众分类，模型首先会检查用户是否属于目标受众。 如果用户符合目标受众的条件并且不属于任何角色，则模型会为他们分配角色资格分数。

在评估第一方受众并分配得分时，模型使用您帐户中定义的默认&#x200B;**[!UICONTROL Profile Merge Rule]**。 最后，访客被分类为其获得最高分的角色。

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## 注意事项和限制 {#considerations}

>[!IMPORTANT]
> 在进入实施阶段之前，请仔细阅读此部分内容。

在配置[!UICONTROL Predictive Audiences]模型时，请记住以下注意事项和限制：

* 您最多可以创建 10 个 [!UICONTROL Predictive Audiences] 模型。
* 对于每个模型，您最多可以选择50个基本特征/区段。
* [!UICONTROL Predictive Audiences]当前不支持第二方和第三方数据。
* [!UICONTROL Predictive Audiences] 从所有第一方数据源中，根据您的第一方特征执行受众分类。
* [!UICONTROL Predictive Audiences]的区段评估使用在模型创建期间选择的&#x200B;**[!UICONTROL Profile Merge Rule]**。 要了解有关[!UICONTROL Profile Merge Rules]的更多信息，请参阅专用的[文档](../profile-merge-rules/merge-rules-overview.md)。
* 某些特征和区段不支持作为基线或目标受众。 [!UICONTROL Predictive Audiences] 在选择以下任一项作为基线或目标受众时，模型将无法保存：
   * 使用预测特征创建的预测特征和区段；
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) 特征或区段；
   * 算法特征；
   * 第二方和第三方特征。
* [!UICONTROL Predictive Audience] [!UICONTROL segments] 不能在中使 [!UICONTROL Audience Lab]用。

## [!UICONTROL Data Export Controls] {#dec}

由[!UICONTROL Predictive Audiences]模型创建的预测区段从以下第一方数据源继承[数据导出控制](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html):

1. 构建模型时您选择的第一方数据源。
1. 目标受众的第一方数据源。 具体而言，构成目标受众的[!UICONTROL traits]或[!UICONTROL segments]的数据导出控制。
1. 为模型选择的[!UICONTROL Profile Merge Rule]的[数据导出控件](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html)。

新创建的预测[!UICONTROL traits]和[!UICONTROL segments]将具有与上述第一方数据源并集相同的隐私限制。

具有其他限制且不属于[!UICONTROL Predictive Audiences]区段隐私限制的特征将从培训阶段中排除，并且不会对模型产生影响。

## [!UICONTROL Profile Merge Rules] {#pmr}

所有预测区段都将分配您在创建模型时选择的[!UICONTROL Profile Merge Rule]。 您选择的[!UICONTROL Profile Merge Rule]很重要，原因如下：

* 它定义当模型分析具有影响力的[!UICONTROL traits]时，在将用户分类为预测[!UICONTROL segment]时，应考虑哪些设备和/或经过验证的用户档案。
* 它控制在模型培训步骤中应使用哪种[!UICONTROL trait]类型（设备级别或跨设备级别），并作为具有影响力的[!UICONTROL traits]出现。 预测[!UICONTROL segments]是目标受众的子集。
   * 如果目标受众是区段，我们建议您为模型选择与分配给目标受众的模型相同的[!UICONTROL Profile Merge Rule]，或者选择包含目标受众配置文件类型的[!UICONTROL Profile Merge Rule]。
   * 如果目标受众为[!UICONTROL trait]，我们建议您选择一个[!UICONTROL Profile Merge Rule]，以便访问与目标受众特征（设备配置文件数据或跨设备配置文件数据）相同类型的数据。
* [!UICONTROL Profile Merge Rules] 仅 [!UICONTROL Current Authenticated Profiles] 支持 [!UICONTROL No Device Profile] 实时受众分类使用和选项。有关详细信息，请参阅[定义的配置文件合并规则选项](../profile-merge-rules/merge-rule-definitions.md)。

选择同时使用设备数据和跨设备数据的[!UICONTROL Profile Merge Rule]将最大化可用于模型培训和用户分类的[!UICONTROL traits]数量，并将其添加到预测[!UICONTROL segments]中。

## [!UICONTROL Role-Based Access Controls] {#rbac}

您为角色和受众分类选择的特征和区段受以下Audience Manager的约束：[基于角色的访问控制](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html)。

Audience Manager用户只能选择具有[查看](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)权限的角色和目标受众的特征或区段。
