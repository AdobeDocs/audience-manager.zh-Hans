---
description: 预测受众可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: 预测受众可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-title: 预测受众概述
solution: Audience Manager
title: 受众经理预测受众
translation-type: tm+mt
source-git-commit: 8cf504fa811e4043f83d0b9f11754065efccf7bb

---


# 预测受众概述 {#predictive-audiences}

[!UICONTROL Predictive Audiences] 帮助您使用先进的数据科学技术将未知的受众实时分类为不同的角色。

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

在营销环境中，人物是由访客、用户或潜在购买者定义的受众细分，他们具有一组特定特征，如人口统计、浏览习惯、购物历史记录等。

[!UICONTROL Predictive Audiences] 模型使这一概念更进一步，使您能够使用受众管理器的机器学习功能将未知的受众分类为不同的角色。 受众管理器通过计算一组已知第一方受众的未知第一方受众的倾向来帮助您实现这一点。

创建模型时， [!UICONTROL Predictive Audiences] 第一步是选择希望目标受众分类的基线特征或区段。 这些特征或区段将定义您的角色。

在评估阶段，模型会为您定义为基 [!UICONTROL Predictive Audiences] 线的每个特征或区段创建新的区段。 下次受众管理者看到您的目标受众中未分类为人物（不符合任何基准特征或区段的条件）的访客时，该模型将确定该访客应属于哪个预测区段，并将访客添加到该区段。 [!UICONTROL Predictive Audiences]

您可以在页面中标识由模型创建的预测区 [!UICONTROL Segments] 段。 每个 [!UICONTROL Predictive Audiences] 模型在文件夹下都有自己的文件夹， [!UICONTROL Predictive Audiences] 单击模型文件夹即可查看每个模型的区段。

![预测受众细分](assets/predictive-audiences-segments.png)

## 用例 {#use-cases}

为了帮助您更好地了解如何使用和何时使用 [!UICONTROL Predictive Audiences]，以下是受众管理器客户可以通过此功能解决的几个使用案例。

### 用例#1

作为电子商务公司中的营销人员，我希望将我的所有Web和移动访客分类为各种品牌关联类别，以便个性化其用户体验。

### 用例#2

作为媒体公司中的营销人员，我希望按喜爱的类别对未经身份验证的Web和移动访客进行分类，以便向他们建议跨所有渠道的个性化内容。

### 用例#3

作为航空公司的广告商，我希望确保根据我的受众对旅游目的地的兴趣对其进行分类，以便在较短的重定向窗口中实时向他们投放广告。

### 用例#4

作为广告商，我要实时对第一方受众进行分类，以便对热门新闻做出快速反应。

### 用例#5

作为营销人员，我希望预测我的网站访客所处的客户旅程阶段，如发现、参与、购买或保留，以便我能够相应地目标这些客户。

### 用例#6

作为媒体公司，我希望将受众分类，以便以优惠价格销售广告空间，同时为访客提供相关广告。

## 预测受众模型的工作原理

创建模型时， [!UICONTROL Predictive Audiences] 需要执行三个步骤：

1. 首先，您至少选择两个特征或两个将定义您角色的区段。
1. 然后，选择一个特征或段，它定义要分类的目标受众。
1. 最后，为模型选择一个名称，并选择将存储预测段的数据源。

### 角色的选择标准 {#selection-personas}

您可以选择任何第一方特征或区段来定义您的角色。 但是，为获得最佳效果，以下是一组推荐的最佳实践：

* 选择您的人物特征或区段，以便每个人物至少拥有几百个设 [备ID](../../reference/ids-in-aam.md)。
* 如果您的特征基于跨设 [备ID](../../reference/ids-in-aam.md)，则可以使用使用设备ID的 [用户档案合并规则](../profile-merge-rules/merge-rules-overview.md) ( [例如](../../reference/ids-in-aam.md))将其包含在区段中 [!UICONTROL Device Graph]。 这将确保有足够 [的设备ID](../../reference/ids-in-aam.md) ，算法可以从中学习。
* 我们建议为您的个人选择特征或简单的区段，包括1到3个特征。
* 选择重叠程度最小的基线特征或区段。
* 确保在数字资产中捕获粒度特征。

### 目标受众的选择标准 {#selection-audience}

与人物选择类似，您应选择特征或区段来定义您的目标受众，以便其拥有具有丰富特征集的实时用户，以便将其分类到正确的人物。

### 预测受众模型培训阶段 {#model-training}

在算法将您的第一方受众分类为正确的角色之前，它需要根据您的数据进行自我培训。

对于您定义的每个人物，算法会分析其各自的受众，并评估过去30天内其用户的任何实时和／或载入的特征活动。
此步骤每24小时进行一次，以解决第一方受众中的更改。

### 预测受众模型分类阶段 {#model-classification}

当实时看到作为目标访客的一部分的访客时，模型评估该受众是否是定义角色的一部分。 对于不属于任何角色的每个访客，模型都会分配角色资格得分。

在评估第一方受众和分配分数时，该模型使用您帐户中定 **[!UICONTROL Profile Merge Rule]** 义的默认值。 最后，访客被归为他们获得最高分的角色。

![预测受众图](assets/predictive-audiences-graph.png)

## 注意事项和限制 {#considerations}

>[!IMPORTANT]
> 在进入实施阶段之前，请仔细阅读本文。

配置模 [!UICONTROL Predictive Audiences] 型时，请记住以下注意事项和限制：

* 最多可创建10种模 [!UICONTROL Predictive Audiences] 型。
* 对于每个模型，您最多可以选择50个基本特征／区段。
* 中目前不支持第二方和第三方数据 [!UICONTROL Predictive Audiences]。
* 受众分类仅针对实时第一方受众。 载入的第一方受众分类在将来的更新中可能受支持。
   >[!IMPORTANT]
   > 目前，您 [!UICONTROL Total Segment Population] 的预测区段显示为0，预测受众不 [支持“批量出站数据传输](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) ”。 此行为将在以后的更新中发生更改。
* [!UICONTROL Predictive Audiences] 根据您的第一方特征从所有第一方数据源执行受众分类。
* 针对的细分 [!UICONTROL Predictive Audiences] 评估使用您在帐 **[!UICONTROL Profile Merge Rule]** 户中定义的默认值。 要进一步了解 [!UICONTROL Profile Merge Rules] 专用文 [档](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/profile-merge-rules/merge-rules-overview.html)。
* 某些特征和区段不支持作为基准或目标受众。 [!UICONTROL Predictive Audiences] 当选择以下任一项作为基准或目标受众时，模型将无法保存：
   * 使用预测特征创建的预测特征和细分；
   * [Adobe Experience Platform特征](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) 或细分；
   * 算法特征；
   * 第二方和第三方特征。

## 数据导出控制{#dec}

由模型创建的 [!UICONTROL Predictive Audiences] 预测段会从以 [下第一方数据源继承“数据导出控制](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) ”:

1. 在构建模型时选择的第一方数据源。
1. 您的目标受众的第一方数据源。 具体而言，数据导出控制构成您的目标受众的特征或区段。

新创建的预测特征和区段将具有与上述第一方数据源的合并相同的隐私限制。

具有不属于区段隐私限制的其他限制的特 [!UICONTROL Predictive Audiences] 征将被排除在培训阶段之外，并且不会对模型产生影响。

## 基于角色的访问控制{#rbac}

您为角色和受众分类选择的特征和区段受受众经理基于角 [色的访问控制的约束](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)。

受众管理器用户只能为具有视图权限的角色和目标受众选择特征 [或区段](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)。
