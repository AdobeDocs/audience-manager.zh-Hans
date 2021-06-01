---
description: Audience Lab允许您使用基线区段创建测试组，从而支持多个用例。 您可以将测试组划分为多个相互排斥的测试区段，将这些区段映射到不同的目标，然后确定哪些区段在促进转化方面最有效。
seo-description: Audience Lab允许您使用基线区段创建测试组，从而支持多个用例。 您可以将测试组划分为多个相互排斥的测试区段，将这些区段映射到不同的目标，然后确定哪些区段在促进转化方面最有效。
seo-title: Audience Lab 用例
solution: Audience Manager
title: Audience Lab 用例
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# Audience Lab 用例 {#audience-lab-use-cases}

[!UICONTROL Audience Lab] 允许您使用基线区段创建测试组，从而启用多个用例。您可以将测试组划分为多个相互排斥的测试区段，将这些区段映射到不同的目标，然后确定哪些区段在促进转化方面最有效。

## 在Audience Lab中比较模型{#compare-models}

在[!DNL Audience Manager]中，可以使用多种不同类型的模型和模型源。 [!UICONTROL Audience Lab] 提供了一种比较活跃模型中客户转化率的简便方法。

<!-- audience-lab-compare-models.xml -->

在此用例中，您将比较不同的模型。 您可以使用通过内部data warehouse创建的模型，并将其导入[!DNL Audience Manager]作为[已载入的特征](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)，也可以使用[!DNL Audience Manager]中的[算法模型](../../features/algorithmic-models/understanding-models.md)功能。

1. 在[模型生成器](../../features/algorithmic-models/create-model.md)中创建两个模型，或通过外部平台创建两个模型。
1. 从算法模型创建[算法特征](../../features/traits/create-algorithmic-traits.md)或将您自己的模型导入为已载入的特征。
1. 创建互斥的区段，以便两个模型中的用户不会重叠：

   * 创建&#x200B;*模型1区段*&#x200B;和&#x200B;*模型2区段*。
   * 使&#x200B;*模型1区段*&#x200B;的区段规则成为模型1特征[!DNL AND NOT]模型2特征，反之亦然&#x200B;*模型2区段*。

1. [在中创建两个](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 区段 [!UICONTROL Audience Lab]测试组，一个以模 *型1* 区段作为基线，另一个以模型2区段 *作* 为基线。

   * 使两个测试组的变量保持相同：相同的目标、创意、转化特征。
   * 确保测试区段具有相似的用户数（例如160万和180万是正常的，160万和1600万不是正常的）。
   * 在每个测试区段测试组中保留一个控制区段。 这样，您就可以保留每个区段的一小部分，而不会在测试中明确定位它们。

1. 检查结果：

   * [Audience Lab报表视图](../../features/audience-lab/audience-lab-reporting-view.md)将显示每个模型的转化次数。 对于基于转化的营销活动，推动转化最多的测试区段将表示效果最佳的模型。
   * 由于您具有控制区段，因此您还可以针对“标准定位”评估模型的效果。 您不仅仅测试一种模型，而且测试“此模型是否比常规方法做得更好？”

## 跨目标测试创意{#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

使用[!UICONTROL Audience Lab]测量创意人员在不同目标之间促进的转化次数。 此用例还允许您根据自然发生的转化来测量创作元素的转化。

1. [创建区段测试组](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)，选择要测试创作元素的区段作为基准区段。
1. 将基线区段拆分为测试区段和控制区段。
1. 将测试区段映射到您希望测试的不同目标。
1. 控制区段可以预扣，且未映射到任何目标。 测试创意不应定位控制区段以设置自然发生的转化的结果基线。
1. 指定测试的开始日期和结束日期。
1. 在目标中设置区段和创作元素。
1. [Audience Lab报表视图](../../features/audience-lab/audience-lab-reporting-view.md)将显示创意在各个目标中推动的转化次数。
1. 由于您创建了控制区段，因此您还可以评估创作元素针对自然发生的转化的效果。 您正在测试以下问题：“此创意产生的转化率是否高于常规做法？”
