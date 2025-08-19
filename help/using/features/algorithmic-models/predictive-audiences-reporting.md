---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Reporting
solution: Audience Manager
title: Predictive Audiences报表
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 2%

---

# Predictive Audiences报表

保存[!UICONTROL Predictive Audiences]模型后，Audience Manager会开始对其进行训练。 在几个小时内，计算模型将开始分析[数据收集服务器](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)上的受众。 报告将在第二天提供。

若要查看[!UICONTROL Predictive Audiences]分类的结果，请转到&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，然后在列表中单击您的模型。

使用左侧的筛选选项搜索模型名称或根据模型类型筛选结果。

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

模型表显示以下信息：

* **[!UICONTROL ID]**：模型ID唯一标识Audience Manager帐户中的每个模型；
* **[!UICONTROL Name]**：您在模型创建步骤中提供的名称；
* **[!UICONTROL Description]**：您在模型创建步骤中提供的描述；
* **[!UICONTROL Model Type]**：每个模型的类型（[!UICONTROL Look-Alike Modeling]或[!UICONTROL Predictive Audiences]）；
* **[!UICONTROL Status]**：每个模型的状态：
   * **[!UICONTROL Pending]**：模型正在初始化，将很快开始生成结果；
   * **[!UICONTROL Active]**：模型已成功运行并产生结果；
   * **[!UICONTROL Warning]**：模型无法生成结果，因为数据不足（即，基线人口较少，用户配置文件不丰富）；
   * **[!UICONTROL Error]**：模型无法运行。 您应联系Adobe代表。

## 模型概述报表{#model-report}

选择模型后，将加载其报表页面。 在页面顶部，您可以根据1天的实时实现情况查看前5个最大的预测区段，该模型已按来对目标受众进行分类。 **[!UICONTROL Other]**&#x200B;类别包含其余角色，这些角色未包含在前5个最大的预测区段中。

Audience Manager会为您的[!UICONTROL Predictive Audiences]显示一个带有颜色编码的圆环图和时间线图。

单击页面顶部的角色选项卡可在图表和图形中添加或删除这些角色。

圆环图可向您显示目标受众基于角色的细分，而圆环图则可向您显示过去6天内预测区段的1天实时人口趋势。

如果模型状态为[!UICONTROL Pending]、[!UICONTROL Warning]或[!UICONTROL Error]，则将显示模型状态而不是图形。

![smart-persona-report](assets/predictive-audiences-report.png)

报告表显示每个[!UICONTROL Predictive Audiences]区段的以下信息。

1. **[!UICONTROL SEGMENT ID]**：与每个角色关联的自动创建区段的区段ID；
1. **[!UICONTROL NAME]**：角色名称；
1. **[!UICONTROL STATUS]**： [!UICONTROL Predictive Audiences]区段的状态：
   * **[!UICONTROL Succeeded]**：用户被分类到此区段；
   * **[!UICONTROL Pending]**：区段仍在初始化；
   * **[!UICONTROL Insufficient Training Data]**：由于数据不足，用户未分类到此区段。 总基线人口太少，无法提供足够的数据来学习。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**：过去24小时内每个角色的区段实现次数。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**：过去24小时内每个角色的区段实现在模型总人口中的百分比。

## 影响特征{#influential-traits}

[!UICONTROL Influential Traits]是[!UICONTROL Predictive Audiences]算法发现为确定访客角色分类的最强预测值的特征。

它们的符号指示特征的存在是增加(+)还是减少(-)用户属于所选角色的可能性。

要查看所有角色具有影响力的特征，请单击[!UICONTROL View All Influential Traits]。

[!UICONTROL Influential Traits]窗口显示所选模型中每个角色的以下信息：

![具影响力的特征](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**：所选角色每个影响特征的特征ID；
1. **[!UICONTROL NAME]**：所选角色的每个具有影响力特征的名称；
1. **[!UICONTROL DESCRIPTION]**：所选角色的每个影响特征的描述；
1. **[!UICONTROL WEIGHT]**：所选角色每个具有影响力特征的权重。 [!UICONTROL Influential Traits]默认按权重降序排序。  权重的值表示它们的预测能力。 该符号指示特征的存在是增加(+)还是减少(-)属于某个角色的可能性。
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**：过去30天内选定角色每个影响特征实现的唯一特征数。
