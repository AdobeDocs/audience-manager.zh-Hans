---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences FAQ
solution: Audience Manager
title: Predictive Audiences 常见问题解答
feature: Algorithmic Models
exl-id: 21073970-8457-470b-89fc-724a118a18d2
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '949'
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

1. 未選取任何角色 [!UICONTROL traits] / [!UICONTROL segments] 擁有足夠的使用者設定檔。 建議您選擇您的 [!UICONTROL traits] 或 [!UICONTROL segments] 讓每個角色至少擁有幾百個使用者設定檔。
1. 未選取任何角色 [!UICONTROL traits] / [!UICONTROL segments] 使用者設定檔中有足夠的資料（沒有足夠的特徵可進行分析）。
1. 目標受眾特徵/區段沒有任何作用中或已上線的使用者。
1. 过去 30 天内处于活动状态或已载入的目标受众用户在其用户配置文件中没有足够的数据（特征不足，无法进行分析）。
1. 目標受眾區段使用不同的 [!UICONTROL Profile Merge Rule] 從您為模型選擇的模型開始。
1. 目標受眾特徵的資料來源可能未包含在 [!UICONTROL Profile Merge Rule] 您為模型選擇的引數。

为了获得最佳结果，请遵循[角色选择标准](../features/algorithmic-models/predictive-audiences.md#selection-personas)和[目标受众选择标准](../features/algorithmic-models/predictive-audiences.md#selection-audience)中的建议准则。

 

**為什麼我的模型顯示 [!UICONTROL Error] 狀態？**

这表明模型运行失败。在這種情況下，請洽詢您的 [!DNL Adobe] 代表。

 

**如何變更 [!UICONTROL Profile Merge Rule] 對於 [!UICONTROL Predictive Audiences] [!UICONTROL segment]？**

選取與先前模型相同的角色和目標對象，以建立新模型。 在建立模型期間，指派另一個 [!UICONTROL Profile Merge Rule].

>[!WARNING]
> 或者，您可以使用 [區段產生器](../features/segments/segment-builder.md) 手動建立 [!UICONTROL segment] 使用現有的預測性 [!UICONTROL trait] 並將其指派給 [!UICONTROL Profile Merge Rule] 隨心所欲。
> 
> 不過，我們不建議使用此做法，因為此做法具有預測性 [!UICONTROL traits] 自動繼承 [!UICONTROL Profile Merge Rule] 屬於的模型，而且是從具影響力的 [!UICONTROL traits] 符合 [!UICONTROL Profile Merge Rule] 模型的。

 

**什麼 [!UICONTROL Profile Merge Rule] 我應該選擇嗎？**

選擇 [!UICONTROL Profile Merge Rule] 針對您的模型，請密切分析您的使用案例。

假設您的目標對象 [!UICONTROL segment] 使用 [!UICONTROL Profile Merge Rule] 根據已驗證的設定檔+ [!DNL Device Graph] 設定檔，而您選取相同的設定檔 [!UICONTROL Profile Merge Rule] 用於預測性 [!UICONTROL segments]. 在此情況下，包括裝置層級和跨裝置層級 [!UICONTROL traits] 將用於訓練模型和將使用者放置到預測性中 [!UICONTROL segment].

但是，如果您選取 [!UICONTROL Profile Merge Rule] 僅根據裝置設定檔，您的所有跨裝置皆非 [!UICONTROL traits] 將具有影響力，且不會有助於將使用者放置到預測性位置 [!UICONTROL segment]. 這可能會對模型的精確度和觸及率產生不良影響。

仔細分析您的使用案例，並決定哪些 [!UICONTROL trait] 您希望模型從中學習的型別，以及您希望模型用於分類的資料型別。

**目标受众中不属于任何角色特征/区段的用户是否无法分类？**

是的，如果用户在其配置文件中没有任何特征就不能被分类。在这种情况下，用户针对所有角色特征/区段获得的匹配得分为 0，因此不会被分类为任何预测区段。

 

**被分类为其中一个预测区段的用户能否被重新分类为其他 [!UICONTROL Predictive Audiences] 区段？**

能。由于该算法每天都会进行训练，因此就特征得分而言，它会根据每个角色进行更改。如果属于 [!UICONTROL Predictive Audiences] 区段的用户处于活动状态，则其特征得分会发生更改，从而可以根据过去 30 天的活动更改分类。

 

**我能否看到对受众进行分类所依据的特征？**

能，您可以在模型报表页中查看所有基线的全部具有影响力的特征。请参阅[具有影响力的特征](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits)。

 

**我可以變更預測性特徵的存留時間(TTL)嗎？**

預測特徵TTL設為0 （期限），且無法變更。 [!UICONTROL Predictive Audiences] 只有當使用者符合基本區段的資格或重新分類為不同的預測區段時，才能從預測區段中取消使用者區段。

如有需要，您可以建立包含預測特徵和具有指定TTL的活動特徵的新區段來解決此問題。

 


**如果我编辑其中一个基线特征或区段，模型会发生什么情况？**

模型每天都会对特征或区段进行一次评估。您应会在更新后的第二天看到已更新的分类。

 

**我可以选择模型将从中学习的数据源吗？**

不可以，不支持选择数据源。[!UICONTROL Predictive Audiences] 算法会学习您的所有第一方特征。
