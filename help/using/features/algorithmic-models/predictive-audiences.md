---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-title: Predictive Audiences 概述
solution: Audience Manager
title: Audience Manager Predictive Audiences
translation-type: tm+mt
source-git-commit: f52321f3621d9eb6b9c5b643a3516f39f35466c2
workflow-type: tm+mt
source-wordcount: '1251'
ht-degree: 9%

---


# [!UICONTROL Predictive Audiences] 概述 {#predictive-audiences}

[!UICONTROL Predictive Audiences] 帮助您使用高级数据科学技术将未知受众实时分类为不同的角色。

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

在营销环境中，角色是指由具有一系列相同特征（例如人口统计特征、浏览习惯、购物历史记录等）的访客、用户或潜在购买者构成的一个受众区段。

[!UICONTROL Predictive Audiences] 模型进一步扩展了角色这一概念的应用，允许您使用 Audience Manager 的机器学习功能将未知受众分类为不同的角色。Audience Manager 可以计算未知的第一方受众与一组已知的第一方受众之间的相似性，从而帮助您做到这一点。

创建模型 [!UICONTROL Predictive Audiences] 时，第一步是选择希望目标受众分类的基线特征或区段。 这些特征或细分将定义您的角色。

在评估阶段，模型会为您定义为 [!UICONTROL Predictive Audiences] 基线的每个特征或区段创建新区段。 下次Audience Manager看到目标受众访客未被分类为人物（未符合任何基准特征或区段的资格）时，该模型将确定访客应属于哪个预测区段，并将访客添加到该区段。 [!UICONTROL Predictive Audiences]

您可以在页面中标识由模型创建的预测区 [!UICONTROL Segments] 段。 每个 [!UICONTROL Predictive Audiences] 模型在文件夹下都有其自己的 [!UICONTROL Predictive Audiences] 文件夹，单击模型文件夹即可查看每个模型的段。

![预测受众细分](assets/predictive-audiences-segments.png)

## 用例 {#use-cases}

为了帮助您更好地了解如何以及何时使用， [!UICONTROL Predictive Audiences]以下是Audience Manager客户可通过使用此功能解决的几个使用案例。

### 用例#1

作为电子商务公司的营销人员，我希望将我的所有Web和移动访客分类为不同的品牌关联类别，以便个性化其用户体验。

### 用例#2

作为媒体公司的营销人员，我希望按最喜爱的类别对未经身份验证的Web和移动访客进行分类，以便向他们建议跨所有渠道的个性化内容。

### 用例#3

作为航空公司的广告商，我想确保根据受众对旅游目的地的兴趣对其进行分类，以便在一个较短的重新定位窗口内实时向他们投放广告。

### 用例#4

作为广告商，我想实时对第一方受众进行分类，以便能够对热门新闻做出快速反应。

### 用例#5

作为营销人员，我希望预测我的网站访客处于哪个客户旅程阶段，如发现、参与、购买或保留，以便我能够相应地目标他们。

### 用例#6

作为媒体公司，我希望将受众分类，以便以优惠价格销售广告空间，同时为访客提供相关广告。

## 模型 [!UICONTROL Predictive Audiences] 的工作方式 {#how-predictive-audiences-models-work}

创建模型 [!UICONTROL Predictive Audiences] 时，需要执行三个步骤：

1. 首先，您至少选择两个特征或两个将定义您角色的区段。
1. 然后，选择一个特征或区段，它定义要分类的目标受众。
1. 最后，为模型选择一个名称，并选择将存储预测段的数据源。

### 角色的选择标准 {#selection-personas}

您可以选择任何第一方特征或细分来定义您的角色。 但是，为获得最佳效果，以下是一组推荐的最佳实践：

* 选择您的人物特征或区段，以便每个人物至少拥有几百个 [设备ID](../../reference/ids-in-aam.md)。
* 如果您的特征基于 [跨设备ID](../../reference/ids-in-aam.md)，则可以使用使用设备ID的 [用户档案合并规则](../profile-merge-rules/merge-rules-overview.md) (例 [如](../../reference/ids-in-aam.md))将其包 [!UICONTROL Device Graph]含在区段中。 这将确保有足够 [的设备](../../reference/ids-in-aam.md) ID可供算法学习。
* 我们建议为您的个人选择特征或简单区段，由1到3个特征组成。
* 选择重叠最小的基线特征或区段。
* 确保在您的数字资产中捕获粒度特征。

### Target受众的选择标准 {#selection-audience}

与人物选择类似，您应选择特征或区段来定义您的目标受众，使其具有具有丰富特征集的实时用户，以便将其分类到正确的人物。

### [!UICONTROL Predictive Audiences] 模型培训阶段 {#model-training}

在算法将第一方受众分类为正确的角色之前，它需要根据您的数据进行自我培训。

对于您定义的每个人物，算法会分析其各自的受众，并评估过去30天内其用户的任何实时和／或载入的特征活动。
此步骤每24小时执行一次，以说明第一方受众中的更改。

### [!UICONTROL Predictive Audiences] 模型分类阶段 {#model-classification}

当实时看到属于目标受众的访客时，模型会评估访客是否是已定义角色的一部分。 对于不属于任何角色的访客，模型会分配角色资格得分。

在评估第一方受众和分配分数时，该模型使用在帐户中 **[!UICONTROL Profile Merge Rule]** 定义的默认值。 最后，访客被归为他们获得最高分的角色。

![预测受众图](assets/predictive-audiences-graph.png)

## 注意事项和限制 {#considerations}

>[!IMPORTANT]
> 进入实施阶段前，请仔细阅读本节内容。

配置模 [!UICONTROL Predictive Audiences] 型时，请注意以下注意事项和限制：

* 您最多可以创建 10 个 [!UICONTROL Predictive Audiences] 模型。
* 对于每个模型，您最多可以选择50个基本特征／区段。
* 目前不支持第二方和第三方数据 [!UICONTROL Predictive Audiences]。
* 受众分类只针对实时的第一方受众。 载入的第一方受众分类在将来的更新中可能受支持。
   >[!IMPORTANT]
   > 当前，预 [!UICONTROL Total Segment Population] 测区段显示为0，不支 [持批出站数据传输](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) 。 [!UICONTROL Predictive Audiences]此行为将在以后的更新中发生更改。
* [!UICONTROL Predictive Audiences] 根据您的第一方特征从所有第一方数据源执行受众分类。
* 区段评估 [!UICONTROL Predictive Audiences] 使用您在 **[!UICONTROL Profile Merge Rule]** 帐户中定义的默认值。 要了解有关详细信 [!UICONTROL Profile Merge Rules] 息，请参阅专 [用文档](../profile-merge-rules/merge-rules-overview.md)。
* 某些特征和区段不支持作为基准或目标受众。 [!UICONTROL Predictive Audiences] 当选择以下某项作为基准或目标受众时，模型将无法保存：
   * 利用预测特征创建的预测特征和细分；
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) 特征或细分；
   * 算法特征；
   * 第二方和第三方特征。

## [!UICONTROL Data Export Controls] {#dec}

由模型创建的 [!UICONTROL Predictive Audiences] 预测区段 [会从以下第一方](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) 数据源继承“数据导出控制”:

1. 在构建模型时选择的第一方数据源。
1. 您的目标受众的第一方数据源。 具体而言，数据导出控制构成您的目标受众的特征或区段。

新创建的预测特征和区段将具有与上述第一方数据源的合并相同的隐私限制。

具有不属于区段隐私限制的其他限 [!UICONTROL Predictive Audiences] 制的特征将被排除在培训阶段，并且不会对模型产生影响。

## [!UICONTROL Role-Based Access Controls] {#rbac}

您为角色和受众分类选择的特征和区段受基于访问控制 [角色的Audience Manager的约束](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)。

Audience Manager用户只能为具有视图权限的角色和目标受众选择特 [征或区段](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)。
