---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-title: Predictive Audiences 报表
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 6%

---


# Predictive Audiences 报表

保存模型后， [!UICONTROL Predictive Audiences] Audience Manager开始会对其进行培训。 在几小时内，计算模型将开始分析数据收集服务器 [上的受众](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)。 报告将在次日可用。

要查看分类结 [!UICONTROL Predictive Audiences] 果，请转到 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，然后在列表中单击模型。

使用左侧的筛选选项搜索模型名称或根据模型类型筛选结果。

![预测受众过滤器](assets/predictive-audiences-filter-models.png)

“模型”(models)表格显示以下信息：

* **[!UICONTROL ID]**: 模型ID可唯一标识您的Audience Manager帐户中的每个模型；
* **[!UICONTROL Name]**: 您在模型创建步骤中提供的名称；
* **[!UICONTROL Description]**: 在模型创建步骤中提供的描述；
* **[!UICONTROL Model Type]**: 每种模型的类型([!UICONTROL Look-Alike Modeling] 或 [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: 每个模型的状态：
   * **[!UICONTROL Pending]**: 模型正在初始化，很快将开始产生结果；
   * **[!UICONTROL Active]**: 模型运行成功，取得了良好效果；
   * **[!UICONTROL Warning]**: 由于数据不足(即基线数量低，用户用户档案不丰富)，模型无法产生结果；
   * **[!UICONTROL Error]**: 模型无法运行。 您应联系您的Adobe代表。

## 模型概述报告{#model-report}

选择模型后，其报告页面将加载。 在页面顶部，您可以看到前5个最大的预测细分，这些预测细分基于1天的实时实现，该模型已按目标受众对您的进行分类。 该类别 **[!UICONTROL Other]** 包括其余的角色，这些角色并不包括在前5大预测细分中。

Audience Manager显示颜色编码的圆环图和时间轴图表 [!UICONTROL Predictive Audiences]。

单击页面顶部的角色选项卡，将在图表和图形中添加或删除角色选项卡。

甜圈图显示了您的目标受众的基于角色的细分，而图表则显示了过去6天内预测区段的1天实时人口趋势。

如果模型状态 [!UICONTROL Pending]为、 [!UICONTROL Warning]或 [!UICONTROL Error]，则显示模型状态而不是图形。

![智能角色报告](assets/predictive-audiences-report.png)

报表表格显示每个区段的以下 [!UICONTROL Predictive Audiences] 信息。

1. **[!UICONTROL SEGMENT ID]**: 与每个人物关联的自动创建的区段的区段ID;
1. **[!UICONTROL NAME]**: 人物名称；
1. **[!UICONTROL STATUS]**: 区段的状 [!UICONTROL Predictive Audiences] 态：
   * **[!UICONTROL Succeeded]**: 用户被划分为此领域；
   * **[!UICONTROL Pending]**: 段仍在初始化；
   * **[!UICONTROL Insufficient Training Data]**: 由于数据不足，用户未被分类到此区段。 总基线总量太低，无法提供足够的数据供您学习。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: 过去24小时内每个角色的细分实现数。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: 过去24小时内每个角色的细分实现占模型总人口的百分比。

## 影响力特征{#influential-traits}

[!UICONTROL Influential Traits] 是算法发现 [!UICONTROL Predictive Audiences] 的最强的用于确定访客人物分类的预测符。

其符号指示特征的存在是增加(+)还是减少(-)属于所选人物的用户的可能性。

要视图所有角色的影响力特征，请单击 [!UICONTROL View All Influential Traits]。

该窗 [!UICONTROL Influential Traits] 口会显示选定模型中每个人物的以下信息：

![影响特征](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: 所选人物的每个影响特征的特征ID;
1. **[!UICONTROL NAME]**: 所选人物的每个影响特征的名称；
1. **[!UICONTROL DESCRIPTION]**: 对所选人物的每个影响特征的描述；
1. **[!UICONTROL WEIGHT]**: 所选人物的每个影响特征的权重。 [!UICONTROL Influential Traits] 默认按权重以降序排序。  权重的值表示其预测能力。 该符号指示特征的存在是增加(+)还是减少(-)属于某个人物的可能性。
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: 过去30天内所选人物的每个影响特征的唯一特征实现数。
