---
description: Audience Lab允许您使用基准区段创建测试组，从而实现多个用例。您可以将测试组分为几个互斥的测试区段，将这些测试细分映射到不同目标，然后确定哪些区段最有效地促进转化率。
seo-description: Audience Lab允许您使用基准区段创建测试组，从而实现多个用例。您可以将测试组分为几个互斥的测试区段，将这些测试细分映射到不同目标，然后确定哪些区段最有效地促进转化率。
seo-title: 受众实验室使用案例
solution: Audience Manager
title: 受众实验室使用案例
topic: DIL API
uuid: 727bec8a-df9 a-40cc-b8 a7-e1980 d146 a84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab Use Cases {#audience-lab-use-cases}

[!UICONTROL Audience Lab] 允许您使用基准区段创建测试组，从而实现多个用例。您可以将测试组分为几个互斥的测试区段，将这些测试细分映射到不同目标，然后确定哪些区段最有效地促进转化率。

## Compare Models in Audience Lab {#compare-models}

You can use several different types and sources of models in [!DNL Audience Manager]. [!UICONTROL Audience Lab] 提供一种简单的方式来比较客户的转化率，使其在您的活动模型中。

<!-- audience-lab-compare-models.xml -->

在此用例中，您将比较不同的模型。You can either use models created via an in-house data warehouse and import them in [!DNL Audience Manager] as [Onboarded Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or you can use the [Algorithmic Models](../../features/algorithmic-models/understanding-models.md) feature in [!DNL Audience Manager].

1. Create two models, either in the [Model Builder](../../features/algorithmic-models/create-model.md), or via an outside platform.
1. Create [algorithmic traits](../../features/traits/create-algorithmic-traits.md) from the algorithmic model or import your own models as onboarded traits.
1. 创建互斥的细分，使这两个模型中的用户不会重叠：

   * Create a *Model 1 Segment* and a *Model 2 Segment*.
   * Have the segment rule for *Model 1 Segment* be model 1 trait [!DNL AND NOT] model 2 trait, and vice-versa for *Model 2 Segment*.

1. [在](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 其中 [!UICONTROL Audience Lab]创建两个区段测试组，一个使用 *Model区段* 作为基准，另一个使用 *Model区段* 作为基准。

   * 将变量保留在两个测试组中：相同的目标、创意、转化特征。
   * 确保测试区段的用户数相近(例如，1.600万个和1.8万个，而不是160万和160万个)。
   * 在每个测试区段测试组中保留一个控制区段。这样，您就可以将每个区段的一小部分留出一部分，而不是明确地将其定位在测试中。

1. 检查结果：

   * [受众实验室报告视图](../../features/audience-lab/audience-lab-reporting-view.md) 将显示每种模式驱动的转化率。对于基于转化的营销活动，驱动转化率最高的测试细分将表示表现最佳的模型。
   * 由于您具有控制细分，您还可以评估模型针对“标准定位”的方式。不仅仅是测试一个模型，而是测试另一个模型，而测试“此模型是否优于正常的做法？”

## Testing Creatives Across Destinations {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Use [!UICONTROL Audience Lab] to measure the number of conversions a creative is driving across different destinations. 使用此用例，您还可以测量创意转化对自然产生的转化率的反映。

1. [创建区段测试组](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)，选择要作为基准区段测试创意的区段。
1. 将基线区段拆分为测试区段和控制段。
1. 将测试区段映射到要测试的不同目标。
1. 控件段可以被隐藏而不会映射到任何目标。测试创意不应被测试创意定位，以为自然发生的转化设置结果基准。
1. 指定测试的开始日期和结束日期。
1. 在目标中设置细分和创意。
1. [受众实验室报告视图](../../features/audience-lab/audience-lab-reporting-view.md) 将显示创意在目的地之间的转化次数。
1. 由于您创建了控制区段，您还可以评估创意如何针对自然产生的转化进行评估。您正在测试问题：“这种创意产生的转化率比普通实践高吗？”
