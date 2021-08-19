---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-title: Predictive Audiences 报表
solution: Audience Manager
title: Predictive Audiences 报表
feature: 算法模型
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 6%

---

# Predictive Audiences 报表

保存[!UICONTROL Predictive Audiences]模型后，Audience Manager会开始对其进行培训。 在几小时内，计算模型将开始分析[数据收集服务器](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)上的受众。 报告将于次日提供。

要查看[!UICONTROL Predictive Audiences]分类的结果，请转到&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，然后单击列表中的模型。

使用左侧的筛选选项搜索模型名称或根据模型类型筛选结果。

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

模型表显示以下信息：

* **[!UICONTROL ID]**:模型ID唯一标识您的Audience Manager帐户中的每个模型；
* **[!UICONTROL Name]**:在模型创建步骤中提供的名称；
* **[!UICONTROL Description]**:在模型创建步骤中提供的描述；
* **[!UICONTROL Model Type]**:每个模型的类型([!UICONTROL Look-Alike Modeling] 或 [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**:每个模型的状态：
   * **[!UICONTROL Pending]**:模型正在初始化，将很快开始产生结果；
   * **[!UICONTROL Active]**:该模型运行成功，取得了成效；
   * **[!UICONTROL Warning]**:由于数据不足（即基线数量低，用户配置文件不丰富），模型未能生成结果；
   * **[!UICONTROL Error]**:模型无法运行。您应该联系Adobe代表。

## 模型概述报表{#model-report}

选择模型后，将加载其报表页面。 在页面顶部，您可以根据1天的实时实现情况，看到排名前5的最大预测区段，即模型已按目标受众分类。 **[!UICONTROL Other]**&#x200B;类别包括其余的角色，这些角色未包含在前5个最大的预测区段中。

Audience Manager显示颜色编码的圆环图和[!UICONTROL Predictive Audiences]的时间轴图。

单击页面顶部的“角色”选项卡，以在图表和图表中添加或删除它们。

圆环图可显示目标受众的基于人物的划分，而图表则显示过去6天内预测区段的1天实时人口趋势。

如果模型状态为[!UICONTROL Pending]、[!UICONTROL Warning]或[!UICONTROL Error]，则会显示模型状态，而不是图形。

![smart-persona-report](assets/predictive-audiences-report.png)

报表表格显示每个[!UICONTROL Predictive Audiences]区段的以下信息。

1. **[!UICONTROL SEGMENT ID]**:自动创建的与每个角色关联的区段的区段ID;
1. **[!UICONTROL NAME]**:人物名称；
1. **[!UICONTROL STATUS]**:区段的状 [!UICONTROL Predictive Audiences] 态：
   * **[!UICONTROL Succeeded]**:用户被划分为此区段；
   * **[!UICONTROL Pending]**:区段仍在初始化；
   * **[!UICONTROL Insufficient Training Data]**:由于数据不足，用户未被分类到此区段。总基线人口太低，无法提供足够的数据供借鉴。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**:过去24小时内每个角色的区段实现次数。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**:过去24小时内每个角色在总模型人口中的区段实现百分比。

## 具有影响力的特征{#influential-traits}

[!UICONTROL Influential Traits] 是发现算法 [!UICONTROL Predictive Audiences] 是确定访客角色分类的最强预测器的特征。

其符号指示特征的存在是增加(+)还是减少(-)用户属于所选角色的可能性。

要查看您所有角色具有影响力的特征，请单击[!UICONTROL View All Influential Traits]。

[!UICONTROL Influential Traits]窗口显示选定模型中每个角色的以下信息：

![影响力特征](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**:选定角色中每个具有影响力特征的特征ID;
1. **[!UICONTROL NAME]**:所选角色中每个具有影响力的特征的名称；
1. **[!UICONTROL DESCRIPTION]**:所选角色的每个影响特征的描述；
1. **[!UICONTROL WEIGHT]**:所选角色的每个影响特征的权重。[!UICONTROL Influential Traits] 默认按权重以降序排序。权重的值表示其预测能力。 符号指示特征的存在是增加(+)还是减少(-)属于某个角色的可能性。
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**:过去30天中选定角色中每个具有影响力特征的独特特征实现次数。
