---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-title: Predictive Audiences 常见问题解答
solution: Audience Manager
title: Audience Manager Predictive Audiences
translation-type: ht
source-git-commit: 8cf504fa811e4043f83d0b9f11754065efccf7bb
workflow-type: ht
source-wordcount: '773'
ht-degree: 100%

---


# Predictive Audiences 常见问题解答

有关 [!UICONTROL Predictive Audiences] 的常见问题解答。

 

**什么时候应该使用[!UICONTROL Predictive Audiences]而不是[!UICONTROL Look-alike modeling]？**

[!UICONTROL Predictive Audiences] 和 [!UICONTROL Look-alike modeling] 分别用于不同的用例。两种算法的主要区别如下：

1. [!UICONTROL Look-alike modeling] 输入少量受众并会扩展这些受众。[!UICONTROL Predictive Audiences] 输入大量受众，并将这些受众分成更小的独特受众，具体由您的角色定义。
1. 两种算法的基本区段数各不相同。[!UICONTROL Predictive Audiences] 至少需要两个基线，而 [!UICONTROL Look-alike modeling] 最多使用一个基线。
1. [!UICONTROL Predictive Audiences] 执行实时区段评估，而 [!UICONTROL Look-alike modeling] 则不执行。

根据您的用例，您应决定哪种模型与您更相关。

您可以考虑构建一个 [!UICONTROL Predictive Audiences] 模型，其中的基线数与构建相似人群拓展模型所需的基线数相同，只是不执行实时评估，并且其中访客很有可能属于多个不同角色，而不是一个独特角色。

 

**我可以创建多少个角色/模型？**

您最多可以创建 10 个 [!UICONTROL Predictive Audiences] 模型。对于每个模型，您最多可以定义 50 个基线特征或区段。

 

**如何从[!UICONTROL Predictive Audiences]区段构建新区段？**

转到 **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**,然后单击 **[!UICONTROL Predictive Audiences]** 文件夹。找到所需的区段，复制该区段，然后根据您的需求对其进行编辑。

 

**为什么我的一些已载入访客没有被分类？**

目前，受众分类仅适用于具有实时资格的用户，但定义为 [!UICONTROL Profile Merge Rules] 一部分的经过身份验证的用户除外。

将来的更新中将添加对已载入数据的完全支持。

 

**什么时候才能看到模型生成的第一个结果？**

如果 [!UICONTROL Predictive Audiences] 模型成功运行，则在创建模型后的 24 小时内即可获得模型结果。

如果模型在 24 小时内未生成结果，请联系 Adobe 代表。

 

**为什么我的模型既没有生成结果，也没有显示警告状态？**

[!UICONTROL Predictive Audiences] 模型可能由于以下原因而无法生成结果：

1. 所选角色特征/区段均没有足够的用户配置文件。我们建议选择您的特征或区段，以便每个角色至少拥有几百个用户配置文件。
1. 所选角色特征/区段的用户配置文件中均没有足够的数据（特征不足，无法进行分析）。
1. 目标受众特征/区段在过去 30 天内没有任何活动或已载入的用户。
1. 过去 30 天内处于活动状态或已载入的目标受众用户在其用户配置文件中没有足够的数据（特征不足，无法进行分析）。

为了生成相关结果，[!UICONTROL Predictive Audiences] 算法会根据 DCS 所看到的实时用户活动来评估特征和区段实现。如果您选择的新基本特征和区段还没有足够的用户，则算法可能需要几天时间才能对受众进行分类。

为了获得最佳结果，请遵循[角色选择标准](../features/algorithmic-models/predictive-audiences.md#selection-personas)和[目标受众选择标准](../features/algorithmic-models/predictive-audiences.md#selection-audience)中的建议准则。

 

**为什么我的模型显示“错误”状态？**

这表明模型运行失败。对于这种情况，请联系 Adobe 代表。

 

**如何更改 Predictive Audiences 区段的配置文件合并规则？**

复制 [!UICONTROL Predictive Audiences] 区段，并更改所复制的区段的 [!UICONTROL Profile Merge Rule]。

 

**目标受众中不属于任何角色特征/区段的用户是否无法分类？**

是的，如果用户在其配置文件中没有任何特征就不能被分类。在这种情况下，用户针对所有角色特征/区段获得的匹配得分为 0，因此不会被分类为任何预测区段。

 

**被分类为其中一个预测区段的用户能否被重新分类为其他[!UICONTROL Predictive Audiences]区段？**

能。由于该算法每天都会进行训练，因此就特征得分而言，它会根据每个角色进行更改。如果属于 [!UICONTROL Predictive Audiences] 区段的用户处于活动状态，则其特征得分会发生更改，从而可以根据过去 30 天的活动更改分类。

 

**我能否看到对受众进行分类所依据的特征？**

能，您可以在模型报表页中查看所有基线的全部具有影响力的特征。请参阅[具有影响力的特征](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits)。

 

**如果我编辑其中一个基线特征或区段，模型会发生什么情况？**

模型每天都会对特征或区段进行一次评估。您应会在更新后的第二天看到已更新的分类。

 

**我可以选择模型将从中学习的数据源吗？**

不可以，不支持选择数据源。[!UICONTROL Predictive Audiences] 算法会学习您的所有第一方特征。