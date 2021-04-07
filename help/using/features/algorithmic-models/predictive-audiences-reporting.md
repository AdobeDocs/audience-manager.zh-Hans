---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-title: Predictive Audiences 报表
solution: Audience Manager
title: Predictive Audiences 报表
feature: 算法模型
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
translation-type: tm+mt
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 6%

---

# Predictive Audiences 报表

保存[!UICONTROL Predictive Audiences]型号后，Audience Manager开始会对其进行培训。 在几小时内，计算模型将开始分析[数据收集服务器](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)上的受众。 报告将在次日可用。

要查看[!UICONTROL Predictive Audiences]分类的结果，请转至&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，然后单击列表中的模型。

使用左侧的筛选选项搜索模型名称或根据模型类型筛选结果。

![预测受众过滤器](assets/predictive-audiences-filter-models.png)

“模型”(models)表格显示以下信息：

* **[!UICONTROL ID]**:模型ID可唯一标识您的Audience Manager帐户中的每个模型；
* **[!UICONTROL Name]**:您在模型创建步骤中提供的名称；
* **[!UICONTROL Description]**:在模型创建步骤中提供的描述；
* **[!UICONTROL Model Type]**:每种模型(或[!UICONTROL Look-Alike Modeling] )的 [!UICONTROL Predictive Audiences]类型；
* **[!UICONTROL Status]**:每个模型的状态：
   * **[!UICONTROL Pending]**:模型正在初始化，将很快开始产生结果；
   * **[!UICONTROL Active]**:模型运行成功，取得了成效；
   * **[!UICONTROL Warning]**:由于数据不足(即基线数量低，用户用户档案不丰富)，模型未能产生结果；
   * **[!UICONTROL Error]**:模型无法运行。您应联系您的Adobe代表。

## 模型概述报告{#model-report}

选择模型后，其报告页将加载。 在页面顶部，您可以看到前5个最大的预测细分，根据1天实时发现模型已按目标受众分类。 **[!UICONTROL Other]**&#x200B;类别包括其余角色，这些角色未包括在前5个最大预测区段中。

Audience Manager显示颜色编码的圆环图和[!UICONTROL Predictive Audiences]的时间轴图。

单击页面顶部的角色选项卡，将在图表和图形中添加或删除角色选项卡。

圆环图显示了目标受众的基于角色的细分，而图表显示了过去6天内预测区段的1天实时人口趋势。

如果模型状态为[!UICONTROL Pending]、[!UICONTROL Warning]或[!UICONTROL Error]，则显示模型状态而不是图形。

![智能人物报告](assets/predictive-audiences-report.png)

报表表格显示每个[!UICONTROL Predictive Audiences]区段的以下信息。

1. **[!UICONTROL SEGMENT ID]**:与每个人物关联的自动创建区段的区段ID;
1. **[!UICONTROL NAME]**:人物名称；
1. **[!UICONTROL STATUS]**:区段的状 [!UICONTROL Predictive Audiences] 态：
   * **[!UICONTROL Succeeded]**:用户被划分为此领域；
   * **[!UICONTROL Pending]**:段仍在初始化；
   * **[!UICONTROL Insufficient Training Data]**:由于数据不足，用户未被分类到此区段。总基线人口太低，无法提供足够的数据供参考。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**:过去24小时内每个角色的细分实现数。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**:过去24小时内每个角色的细分实现占模型总人口的百分比。

## 影响特征{#influential-traits}

[!UICONTROL Influential Traits] 是算法发 [!UICONTROL Predictive Audiences] 现为最强的预测器的特征，用于确定访客的人物分类。

其符号指示特征的存在是增加(+)还是降低(-)用户属于所选人物的可能性。

要视图所有角色的影响力特征，请单击[!UICONTROL View All Influential Traits]。

[!UICONTROL Influential Traits]窗口显示选定模型中每个人物的以下信息：

![影响特征](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**:所选人物的每个影响特征的特征ID;
1. **[!UICONTROL NAME]**:所选人物的每个影响特征的名称；
1. **[!UICONTROL DESCRIPTION]**:描述选定人物的每个影响特征；
1. **[!UICONTROL WEIGHT]**:所选人物的每个影响特征的权重。[!UICONTROL Influential Traits] 默认情况下按权重按降序排序。权重的值表示其预测能力。 该符号指示特征的存在是增加(+)还是降低(-)属于某个人物的可能性。
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**:过去30天中选定人物的每个影响特征的唯一特征实现次数。
