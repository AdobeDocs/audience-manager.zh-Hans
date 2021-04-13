---
description: 受众 Lab允许您使用基线段创建测试组，从而支持多个用例。 您可以将测试组分成多个相互排斥的测试区段，将这些测试区段映射到不同的目标，然后确定哪个区段在提高转换方面最有效。
seo-description: 受众 Lab允许您使用基线段创建测试组，从而支持多个用例。 您可以将测试组分成多个相互排斥的测试区段，将这些测试区段映射到不同的目标，然后确定哪个区段在提高转换方面最有效。
seo-title: Audience Lab 用例
solution: Audience Manager
title: Audience Lab 用例
topic-edit: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# Audience Lab 用例 {#audience-lab-use-cases}

[!UICONTROL Audience Lab] 允许您使用基线段创建测试组，从而启用多个用例。您可以将测试组分成多个相互排斥的测试区段，将这些测试区段映射到不同的目标，然后确定哪个区段在提高转换方面最有效。

## 比较受众 Lab {#compare-models}中的模型

可以在[!DNL Audience Manager]中使用几种不同的模型类型和源。 [!UICONTROL Audience Lab] 优惠是在您的活动模型中比较客户转化率的简单方法。

<!-- audience-lab-compare-models.xml -->

在此用例中，您将比较不同的模型。 您可以使用通过内部data warehouse创建的模型，并将它们作为[载入的Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)导入[!DNL Audience Manager]中的[算法模型](../../features/algorithmic-models/understanding-models.md)功能。[!DNL Audience Manager]

1. 在[Model Builder](../../features/algorithmic-models/create-model.md)中或通过外部平台创建两种型号。
1. 根据算法模型创建[算法特征](../../features/traits/create-algorithmic-traits.md)或将您自己的模型导入为已载入的特征。
1. 创建互斥的细分，使两个模型中的用户不会重叠：

   * 创建&#x200B;*Model 1 Segment*&#x200B;和&#x200B;*Model 2 Segment*。
   * 使&#x200B;*Model 1 Segment*&#x200B;的段规则为模型1特征[!DNL AND NOT]模型2特征，对于&#x200B;*Model 2 Segment*&#x200B;则为反之。

1. [创建两个段测](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 试组 [!UICONTROL Audience Lab]，一个以 *Model 1 Segments* 为基线，另一个以Model 2 Segments *为* 基线。

   * 使两个测试组的变量保持相同：相同的目标、创意、转化特征。
   * 确保测试细分具有相似的用户数（例如160万和180万都可以，160万和1600万不可以）。
   * 在每个测试段测试组中保留一个控制段。 这样，您就可以搁置每个区段的一小部分，而不是在测试中显式目标它们。

1. 检查结果：

   * [受众 Lab报告视图](../../features/audience-lab/audience-lab-reporting-view.md)将显示每个型号驱动的转换数。 对于基于转化的活动，驱动转化率最高的测试区段将表示表现最佳的模型。
   * 由于您拥有控制区段，因此您还可以评估模型针对“标准定位”的操作方式。 您不仅测试一种模型，而且测试“此模型是否比常规模式做得更好？”

## 测试目标中的创意{#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

使用[!UICONTROL Audience Lab]测量创意人员在不同目标之间促成的转换数。 此用例还允许您根据自然发生的转化来衡量创意的转化率。

1. [创建“区段测试组](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)”，选择要针对创意进行测试的区段作为基线区段。
1. 将基线段拆分为测试段和控制段。
1. 将测试区段映射到您要测试的不同目标。
1. 可以预扣控制段，但不能将其映射到任何目标。 测试创意不应以控制区段为目标，为自然发生的转换设置结果基线。
1. 指定测试的开始日期和结束日期。
1. 在目标中设置区段和创意。
1. [受众 Lab报告视图](../../features/audience-lab/audience-lab-reporting-view.md)将显示创意人员在各个目标中促成的转换数。
1. 由于您创建了控制区段，因此您还可以评估创意针对自然发生的转换的效果。 您正在测试以下问题：“此创意是否产生了比常规做法更高的转化率？”
