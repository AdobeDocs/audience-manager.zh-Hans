---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-title: Predictive Audiences 常见问题解答
solution: Audience Manager
title: Predictive Audiences 常见问题解答
feature: 算法模型
exl-id: 21073970-8457-470b-89fc-724a118a18d2
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 59%

---

# Predictive Audiences 常见问题解答

有关 [!UICONTROL Predictive Audiences] 的常见问题解答。

 

**什么时候应该使用 [!UICONTROL Predictive Audiences] 而不是 [!UICONTROL Look-alike modeling]？**

[!UICONTROL Predictive Audiences] 和 [!UICONTROL Look-alike modeling] 分别用于不同的用例。两种算法的主要区别如下：

1. [!UICONTROL Look-alike modeling] 输入少量受众并会扩展这些受众。[!UICONTROL Predictive Audiences] 输入大量受众，并将这些受众分成更小的独特受众，具体由您的角色定义。
1. 两种算法的基本区段数各不相同。[!UICONTROL Predictive Audiences] 至少需要两个基线，而 [!UICONTROL Look-alike modeling] 最多使用一个基线。
1. [!UICONTROL Predictive Audiences] 执行实时区段评估，而 [!UICONTROL Look-alike modeling] 则不执行。

根据您的用例，您应决定哪种模型与您更相关。

您可以考虑构建一个 [!UICONTROL Predictive Audiences] 模型，其中的基线数与构建相似人群拓展模型所需的基线数相同，只是不执行实时评估，并且其中访客很有可能属于多个不同角色，而不是一个独特角色。

 

**我可以创建多少个角色/模型？**

您最多可以创建 10 个 [!UICONTROL Predictive Audiences] 模型。对于每个模型，您最多可以定义 50 个基线特征或区段。

 

**如何从 [!UICONTROL Predictive Audiences] 区段构建新区段？**

转到 **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**,然后单击 **[!UICONTROL Predictive Audiences]** 文件夹。找到所需的区段，复制该区段，然后根据您的需求对其进行编辑。

 

**什么时候才能看到模型生成的第一个结果？**

如果 [!UICONTROL Predictive Audiences] 模型成功运行，则在创建模型后的 24 小时内即可获得模型结果。

如果模型在 24 小时内未生成结果，请联系 Adobe 代表。

 

**为什么我的模型既没有生成结果，也没有显示警告状态？**

[!UICONTROL Predictive Audiences] 模型可能由于以下原因而无法生成结果：

1. 所选角色[!UICONTROL traits] / [!UICONTROL segments]中没有足够的用户配置文件。 我们建议选择[!UICONTROL traits]或[!UICONTROL segments]，以便每个角色至少拥有几百个用户配置文件。
1. 所选角色[!UICONTROL traits] / [!UICONTROL segments]的用户配置文件中没有足够的数据（特征不足，无法分析）。
1. 目标受众特征/区段没有任何活动用户或已载入用户。
1. 过去 30 天内处于活动状态或已载入的目标受众用户在其用户配置文件中没有足够的数据（特征不足，无法进行分析）。
1. 目标受众区段使用与您为模型选择的[!UICONTROL Profile Merge Rule]不同的。
1. 目标受众特征的数据源可能未包含在您为模型选择的[!UICONTROL Profile Merge Rule]中。

为了获得最佳结果，请遵循[角色选择标准](../features/algorithmic-models/predictive-audiences.md#selection-personas)和[目标受众选择标准](../features/algorithmic-models/predictive-audiences.md#selection-audience)中的建议准则。

 

**为什么我的模型显示 [!UICONTROL Error] 状态？**

这表明模型运行失败。在这种情况下，请联系您的[!DNL Adobe]代表。

 

**如何更改 [!UICONTROL Profile Merge Rule] 的 [!UICONTROL Predictive Audiences] [!UICONTROL segment]?**

通过选择与上一个模型相同的角色和目标受众来创建新模型。 在模型创建过程中，分配一个不同的[!UICONTROL Profile Merge Rule]。

>[!WARNING]
> 或者，您也可以使用[区段生成器](../features/segments/segment-builder.md)手动创建具有现有预测[!UICONTROL trait]的[!UICONTROL segment]，并为其分配您选择的[!UICONTROL Profile Merge Rule]。
> 
> 但是，我们不建议这样做，因为预测型[!UICONTROL traits]会自动继承其所属模型的[!UICONTROL Profile Merge Rule]，并且这些模型是由符合模型[!UICONTROL Profile Merge Rule]的具有影响力的[!UICONTROL traits]构建的。

 

**我应 [!UICONTROL Profile Merge Rule] 该选择什么？**

为模型选择[!UICONTROL Profile Merge Rule]时，请仔细分析用例。

假设您的目标受众[!UICONTROL segment]使用基于已验证用户档案+ [!DNL Device Graph]用户档案的[!UICONTROL Profile Merge Rule]，并且为预测[!UICONTROL segments]选择相同的[!UICONTROL Profile Merge Rule]。 在这种情况下，设备级别和跨设备级别[!UICONTROL traits]都将用于训练模型和将用户放置到预测[!UICONTROL segment]中。

但是，如果您仅根据设备配置文件选择[!UICONTROL Profile Merge Rule]，则您的跨设备[!UICONTROL traits]都不会产生影响，并且不会对将用户放置到预测[!UICONTROL segment]中产生任何影响。 这可能会对模型的准确性和范围产生不利影响。

仔细分析用例，并确定希望模型从中学习的[!UICONTROL trait]类型以及希望模型用于分类的数据类型。

**目标受众中不属于任何角色特征/区段的用户是否无法分类？**

是的，如果用户在其配置文件中没有任何特征就不能被分类。在这种情况下，用户针对所有角色特征/区段获得的匹配得分为 0，因此不会被分类为任何预测区段。

 

**被分类为其中一个预测区段的用户能否被重新分类为其他 [!UICONTROL Predictive Audiences] 区段？**

能。由于该算法每天都会进行训练，因此就特征得分而言，它会根据每个角色进行更改。如果属于 [!UICONTROL Predictive Audiences] 区段的用户处于活动状态，则其特征得分会发生更改，从而可以根据过去 30 天的活动更改分类。

 

**我能否看到对受众进行分类所依据的特征？**

能，您可以在模型报表页中查看所有基线的全部具有影响力的特征。请参阅[具有影响力的特征](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits)。

 

**我是否可以更改预测特征的生存时间(TTL)?**

预测特征TTL设置为0（存留期），无法更改。 [!UICONTROL Predictive Audiences] 仅当用户符合基本区段的资格或被重新分类为其他预测区段时，才能从预测区段中取消分段用户。

如果需要，您可以通过创建一个新区段来解决此问题，该区段同时包含预测特征和具有指定TTL的活动特征。

 


**如果我编辑其中一个基线特征或区段，模型会发生什么情况？**

模型每天都会对特征或区段进行一次评估。您应会在更新后的第二天看到已更新的分类。

 

**我可以选择模型将从中学习的数据源吗？**

不可以，不支持选择数据源。[!UICONTROL Predictive Audiences] 算法会学习您的所有第一方特征。
