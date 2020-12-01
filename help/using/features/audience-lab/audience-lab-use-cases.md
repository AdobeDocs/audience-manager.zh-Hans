---
description: 受众实验室允许您使用基线段创建测试组，从而启用多个用例。 您可以将测试组分为多个相互排斥的测试区段，将这些测试区段映射到不同的目标，然后确定哪个区段最有效地促进转化。
seo-description: 受众实验室允许您使用基线段创建测试组，从而启用多个用例。 您可以将测试组分为多个相互排斥的测试区段，将这些测试区段映射到不同的目标，然后确定哪个区段最有效地促进转化。
seo-title: Audience Lab 用例
solution: Audience Manager
title: Audience Lab 用例
topic: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 1%

---


# Audience Lab 用例 {#audience-lab-use-cases}

[!UICONTROL Audience Lab] 允许您使用基线段创建测试组，从而启用多个用例。您可以将测试组分为多个相互排斥的测试区段，将这些测试区段映射到不同的目标，然后确定哪个区段最有效地促进转化。

## 比较受众实验室{#compare-models}中的型号

可以在[!DNL Audience Manager]中使用几种不同的型号类型和型号来源。 [!UICONTROL Audience Lab] 优惠是比较活跃模型中客户转化率的简单方法。

<!-- audience-lab-compare-models.xml -->

在此用例中，您将比较不同的模型。 您可以使用通过内部data warehouse创建的模型并将它们作为[载入的Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)导入[!DNL Audience Manager]，也可以使用[!DNL Audience Manager]中的[算法模型](../../features/algorithmic-models/understanding-models.md)功能。

1. 在[Model Builder](../../features/algorithmic-models/create-model.md)中或通过外部平台创建两种型号。
1. 根据算法模型创建[算法特征](../../features/traits/create-algorithmic-traits.md)或将您自己的模型导入为载入的特征。
1. 创建互斥的细分，使两个模型中的用户不会重叠：

   * 创建&#x200B;*模型1段*&#x200B;和&#x200B;*模型2段*。
   * 使&#x200B;*模型1区段*&#x200B;的区段规则为模型1特征[!DNL AND NOT]模型2特征，而&#x200B;*模型2区段*&#x200B;的区段规则反之亦然。

1. [创建两个段测](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 试组 [!UICONTROL Audience Lab]，一个以模 *型1段* 为基线，另一个以模型2段 *为基* 线。

   * 使两个测试组的变量保持相同：相同的目标、创意、转化特征。
   * 确保测试细分的用户数量相似（例如160万和180万都可以，160万和1600万都不能）。
   * 在每个测试段测试组中保留一个控制段。 这样，您就可以保留每个区段的一小部分，而不是在测试中显式目标它们。

1. 检查结果：

   * [受众实验室报告视图](../../features/audience-lab/audience-lab-reporting-view.md)将显示每个模型所驱动的转换数。 对于基于转化的活动，驱动最多转化的测试段将表示性能最佳的模型。
   * 由于您拥有控制区段，因此您还可以评估模型针对“标准定位”的效果。 您不仅测试一种模型，测试另一种模型，还测试“此模型是否比常规模式做得更好？”

## 测试目标中的创意{#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

使用[!UICONTROL Audience Lab]测量创意人员在不同目标之间推动的转化率。 此用例还允许您根据自然发生的转化率衡量创意的转化率。

1. [创建区段测试组](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)，选择要针对创意进行测试的区段作为基准区段。
1. 将基线段拆分为测试段和控制段。
1. 将测试区段映射到您要测试的不同目标。
1. 控制段可以预扣，而不映射到任何目标。 测试创意者不应将控制段作为目标，以为自然发生的转换设置结果基线。
1. 指定测试的开始日期和结束日期。
1. 在目标中设置区段和创意。
1. [受众实验室报告视图](../../features/audience-lab/audience-lab-reporting-view.md)将显示创意人员在各个目标地点推动的转换次数。
1. 由于您创建了一个控制区段，因此您还可以评估创意对自然发生的转化的效果。 您正在测试问题：“此创意是否产生了比正常做法更高的转化率?”
