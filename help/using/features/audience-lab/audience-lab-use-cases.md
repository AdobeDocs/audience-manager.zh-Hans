---
description: Audience Lab允许您使用基线段创建测试组，从而支持多个用例。 您可以将测试组分为多个相互排斥的测试段，将它们映射到不同的目标，然后确定哪个段在促进转化方面最有效。
seo-description: Audience Lab允许您使用基线段创建测试组，从而支持多个用例。 您可以将测试组分为多个相互排斥的测试段，将它们映射到不同的目标，然后确定哪个段在促进转化方面最有效。
seo-title: Audience Lab使用案例
solution: Audience Manager
title: Audience Lab使用案例
topic: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab使用案例 {#audience-lab-use-cases}

[!UICONTROL Audience Lab] 允许您使用基线段创建测试组，从而支持多个用例。 您可以将测试组分为多个相互排斥的测试段，将它们映射到不同的目标，然后确定哪个段在促进转化方面最有效。

## 在Audience Lab中比较模型 {#compare-models}

您可以在中使用几种不同的模型和来源 [!DNL Audience Manager]。 [!UICONTROL Audience Lab] 提供了一种轻松的方式来比较活动模型中客户的转化率。

<!-- audience-lab-compare-models.xml -->

在此用例中，您将比较不同的模型。 您可以使用通过内部数据仓库创建的模型并将其作为载入的特征导入 [!DNL Audience Manager] 中， [也可以使用中的“算法模](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 型 [”功能](../../features/algorithmic-models/understanding-models.md)[!DNL Audience Manager]。

1. 在 [Model Builder](../../features/algorithmic-models/create-model.md)，或通过外部平台创建两个模型。
1. 从算法 [模型创建算法特征](../../features/traits/create-algorithmic-traits.md) ，或将您自己的模型导入为载入的特征。
1. 创建互斥的细分，以便两种模型中的用户不会重叠：

   * 创建 *Model 1区段* ，创 *建Model 2区段*。
   * 使模型1区段的段 *规则成为模型* 1特征 [!DNL AND NOT] 模型2特征，而模型2区段的段规则 *相反*。

1. [在中创建两个区段测试组](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) ，一个以Model 1 Segment [!UICONTROL Audience Lab]（模型1区段）为基线 *，另一个以* Model 2 Segment ** （模型2区段）为基线。

   * 使两个测试组的变量保持相同：相同的目标、创意、转化特征。
   * 确保测试细分具有类似的用户数（例如160万和180万都可以，160万和1600万不可以）。
   * 在每个测试段测试组中保留一个控制段。 这样，您就可以留出每个区段的一小部分，而不是在测试中明确定位它们。

1. 检查结果：

   * Audience [Lab报告视图将显示](../../features/audience-lab/audience-lab-reporting-view.md) ，每个模型所驱动的转化率。 对于基于转化的营销活动，驱动转化率最高的测试区段将表示效果最佳的模型。
   * 由于您拥有控制区段，因此您还可以评估模型针对“标准定位”的效果。 您不仅要测试一个模型，还要测试“这个模型是否比常规做法做得更好？”

## 测试不同目标的创意 {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

使用 [!UICONTROL Audience Lab] 测量创意人员在不同目标之间推动的转化数。 此用例还允许您根据自然发生的转化来衡量创意的转化率。

1. [创建区段测试组](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)，选择要测试创作依据的区段作为基准区段。
1. 将基线段拆分为测试段和控制段。
1. 将测试区段映射到您要测试的不同目标。
1. 可以预扣控件段，但不能将其映射到任何目标。 测试创意者不应将控制段作为目标，以设置自然发生的转换的结果基准。
1. 指定测试的开始日期和结束日期。
1. 在目标中设置区段和创意。
1. Audience Lab [报告视图将显示](../../features/audience-lab/audience-lab-reporting-view.md) ，创意人员在各个目标中的转化率。
1. 由于您创建了控制区段，因此您还可以评估创意针对自然发生的转化的效果。 您正在测试问题：“这种创意是否产生了比常规方法更高的转化率？”
