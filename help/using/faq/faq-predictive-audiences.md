---
description: 预测受众可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: 预测受众可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-title: 预测受众常见问题解答
solution: Audience Manager
title: 受众经理预测受众
translation-type: tm+mt
source-git-commit: 8cf504fa811e4043f83d0b9f11754065efccf7bb

---


# 预测受众常见问题解答

有关的常见问题解答 [!UICONTROL Predictive Audiences]。

 

**我应该在什么时[!UICONTROL Predictive Audiences]候使用，而不是[!UICONTROL Look-alike modeling]?**

[!UICONTROL Predictive Audiences] 用 [!UICONTROL Look-alike modeling] 例不同。 两种算法的主要区别是：

1. [!UICONTROL Look-alike modeling] 将一个小受众作为输入并展开它。 [!UICONTROL Predictive Audiences] 将大受众作为输入，并将其分为由您的角色定义的较小的不同受众。
1. 每种算法的基段数各不相同。 [!UICONTROL Predictive Audiences] 至少需要两个基线，而最 [!UICONTROL Look-alike modeling] 多使用一个基线。
1. [!UICONTROL Predictive Audiences] 执行实时细分评估，而不 [!UICONTROL Look-alike modeling] 执行。

根据您的使用案例，您应决定哪个型号与您更相关。

您可以认为，使用多个基准来构建一个模型相当于构建相同数量的相似模型，只有不进行实时评估，并且访客很可能属于多个不同角色，而不是一个不同的角色。 [!UICONTROL Predictive Audiences]

 

**允许我创建多少个角色／模型？**

最多可创建10种模 [!UICONTROL Predictive Audiences] 型。 对于每个模型，您最多可以定义50个基线特征或区段。

 

**如何从区段构建新的区[!UICONTROL Predictive Audiences]段？**

转到 **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**，然后单击文 **[!UICONTROL Predictive Audiences]** 件夹。 找到所需的细分，重复它，然后根据您的需求编辑它。

 

**为什么我的一些访客没有保密？**

目前，受众分类仅适用于实时资格，但已验证的用户被定义为的一部分的用户除外 [!UICONTROL Profile Merge Rules]。

将在将来的更新中添加对已载入数据的完全支持。

 

**我什么时候才能看到模型产生的第一个结果？**

[!UICONTROL Predictive Audiences] 如果模型成功运行，则模型结果在创建模型后的24小时内可用。

如果该模型在24小时内未产生结果，请联系Adobe代表。

 

**为什么我的模型不生成结果或显示警告状态？**

[!UICONTROL Predictive Audiences] 模型可能由于多种原因而无法产生结果：

1. 所选人物特征／区段没有足够的用户用户档案。 我们建议选择您的特征或区段，以便每个人物至少拥有几百个用户用户档案。
1. 所选人物特征／区段中没有足够的用户用户档案数据（没有足够的特征进行分析）。
1. 目标受众特征／区段在过去30天内没有任何活动或已载入的用户。
1. 在过去30天内处于活动状态或已载入的目标受众用户在其用户用户档案中没有足够的数据（没有足够的特征进行分析）。

为了获得相关结果，该算 [!UICONTROL Predictive Audiences] 法根据DCS所看到的实时用户活动对特征和分段实现进行评估。 如果您选择新的基本特征和尚未拥有足够用户的区段，则算法可能需要几天时间才能对您的受众进行分类。

为获得最佳效果，请遵循“角色选择标准” [和“目标受众选](../features/algorithmic-models/predictive-audiences.md#selection-personas) 择标准”中的建议准则 [](../features/algorithmic-models/predictive-audiences.md#selection-audience)。

 

**为什么我的模型显示“错误”状态？**

模型无法运行。 在这种情况下，请联系您的Adobe代表。

 

**如何更改“预测用户档案”区段的“受众合并规则”?**

重复 [!UICONTROL Predictive Audiences] 区段，并更改复 [!UICONTROL Profile Merge Rule] 制区段的区段。

 

**不属于任何人物特征／区段的目标受众的用户是否可以被分类？**

是的，如果用户在其用户档案中没有任何特征。 在这种情况下，用户将获得0对所有人物特征／区段的匹配得分，因此不会被分类到任何预测区段。

 

**被分类为其中一个预测区段的用户是否可以被重新分类为另一个区[!UICONTROL Predictive Audiences]段？**

能。由于算法是每天进行培训的，因此它在特征评分方面会应用每个角色的更改。 如果属于区段的用户处于活 [!UICONTROL Predictive Audiences] 动状态，则其特征得分的更改可以根据过去30天的活动更改分类。

 

**我能否看到哪些特征是通过哪种受众分类进行的？**

是的，您可以在模型报告页中查看所有基准的所有影响特征。 查看有 [影响力的特征](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits)。

 

**如果我编辑了模型的某个基线特征或区段，该模型会发生什么情况？**

该模型每天评估一个特征或区段。 您应在更新后的第二天看到更新的分类。

 

**我是否可以选择模型将从中学习的数据源？**

否，不支持选择数据源。 该算 [!UICONTROL Predictive Audiences] 法会学习您的所有第一方特征。