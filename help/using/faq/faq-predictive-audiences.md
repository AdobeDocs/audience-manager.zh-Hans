---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-title: Predictive Audiences 常见问题解答
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 8e43da4c8b890fc5f8468f3779918dbfbbf960b8
workflow-type: tm+mt
source-wordcount: '933'
ht-degree: 62%

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

 

**什么时候才能看到模型生成的第一个结果？**

如果 [!UICONTROL Predictive Audiences] 模型成功运行，则在创建模型后的 24 小时内即可获得模型结果。

如果模型在 24 小时内未生成结果，请联系 Adobe 代表。

 

**为什么我的模型既没有生成结果，也没有显示警告状态？**

[!UICONTROL Predictive Audiences] 模型可能由于以下原因而无法生成结果：

1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough user profiles. We recommend choosing your [!UICONTROL traits] or [!UICONTROL segments] so that each persona has at least a few hundred user profiles.
1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough data in their user profiles (not enough traits to analyze).
1. 目标受众特征／区段没有任何有效或已载入的用户。
1. 过去 30 天内处于活动状态或已载入的目标受众用户在其用户配置文件中没有足够的数据（特征不足，无法进行分析）。
1. 目标受众段使用的不 [!UICONTROL Profile Merge Rule] 同于您为模型选择的段。
1. 您为模型选择的目标受众特征的数 [!UICONTROL Profile Merge Rule] 据源可能不包括在中。

为了获得最佳结果，请遵循[角色选择标准](../features/algorithmic-models/predictive-audiences.md#selection-personas)和[目标受众选择标准](../features/algorithmic-models/predictive-audiences.md#selection-audience)中的建议准则。

 

**为什么我的模型显示[!UICONTROL Error]状态？**

这表明模型运行失败。In such cases, please reach out to your [!DNL Adobe] representative.

 

**如何更改[!UICONTROL Profile Merge Rule]为[!UICONTROL Predictive Audiences][!UICONTROL segment]?**

通过选择与上一个模型相同的角色和目标受众来创建新模型。 在模型创建过程中，指定其他 [!UICONTROL Profile Merge Rule]。

>[!WARNING]
> 或者，您也可以使 [用Segment Builder](../features/segments/segment-builder.md) （区段生成器）手 [!UICONTROL segment] 动创建具有现有预测 [!UICONTROL trait] 功能的区段，并为它指 [!UICONTROL Profile Merge Rule] 定您选择的一个。
> 
> 但是，我们不建议这种做法，因为预测 [!UICONTROL traits] 功能会自动继承 [!UICONTROL Profile Merge Rule] 它们所属的模型，而它们是从与模型相符的 [!UICONTROL traits] 有影响力的模型 [!UICONTROL Profile Merge Rule] 中构建的。

 

**我应[!UICONTROL Profile Merge Rule]该选择什么？**

选择模型 [!UICONTROL Profile Merge Rule] 时，请仔细分析用例。

假设您的目标受众使用 [!UICONTROL segment] 基于实 [!UICONTROL Profile Merge Rule] 名+ [!DNL Device Graph] 用户档案的，并且您为预测选 [!UICONTROL Profile Merge Rule] 择相同的用户档案 [!UICONTROL segments]。 在这种情况下，设备级和跨设备级 [!UICONTROL traits] 将用于训练模型和将用户放置到预测中 [!UICONTROL segment]。

但是，如果您只根据设 [!UICONTROL Profile Merge Rule] 备用户档案选择，则您的跨设备将不 [!UICONTROL traits] 会发挥任何影响力，也不会对将用户放置到预测型位置有所贡献 [!UICONTROL segment]。 这可能会对模型的准确性和范围产生不利影响。

仔细分析您的用例，并 [!UICONTROL trait] 确定您希望模型学习的类型以及希望模型用于分类的数据类型。

 

**目标受众中不属于任何角色特征/区段的用户是否无法分类？**

是的，如果用户在其配置文件中没有任何特征就不能被分类。在这种情况下，用户针对所有角色特征/区段获得的匹配得分为 0，因此不会被分类为任何预测区段。

 

**被分类为其中一个预测区段的用户能否被重新分类为其他[!UICONTROL Predictive Audiences]区段？**

能。由于该算法每天都会进行训练，因此就特征得分而言，它会根据每个角色进行更改。如果属于 [!UICONTROL Predictive Audiences] 区段的用户处于活动状态，则其特征得分会发生更改，从而可以根据过去 30 天的活动更改分类。

 

**能否向常规细分添加预测特征？**

将预测特征添加到常规区段时，它将成为预测区段。 因此，所有关联用户档案都被取消分段。 预测细分只能发送到实时目标。

 

**我能否看到对受众进行分类所依据的特征？**

能，您可以在模型报表页中查看所有基线的全部具有影响力的特征。请参阅[具有影响力的特征](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits)。

 

**如果我编辑其中一个基线特征或区段，模型会发生什么情况？**

模型每天都会对特征或区段进行一次评估。您应会在更新后的第二天看到已更新的分类。

 

**我可以选择模型将从中学习的数据源吗？**

不可以，不支持选择数据源。[!UICONTROL Predictive Audiences] 算法会学习您的所有第一方特征。