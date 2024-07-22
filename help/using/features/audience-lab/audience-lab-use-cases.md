---
description: Audience Lab允许您使用基准区段来创建测试组，从而支持多种用例。 您可以将测试组划分为多个互斥的测试区段，将这些测试区段映射到不同的目标，然后确定哪些区段在提高转化率方面最有效。
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Audience Lab用例
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Audience Lab用例 {#audience-lab-use-cases}

[!UICONTROL Audience Lab]允许您使用基准区段来创建测试组，从而支持多个用例。 您可以将测试组划分为多个互斥的测试区段，将这些测试区段映射到不同的目标，然后确定哪些区段在提高转化率方面最有效。

## 在Audience Lab中比较模型 {#compare-models}

您可以在[!DNL Audience Manager]中使用多个不同类型的模型和模型源。 [!UICONTROL Audience Lab]提供了一种简单的方法来比较活跃模型中客户的转化率。

<!-- audience-lab-compare-models.xml -->

在此使用案例中，您将比较不同的模型。 您可以使用通过内部数据仓库创建的模型并将它们作为[载入的特征](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)导入到[!DNL Audience Manager]中，也可以在[!DNL Audience Manager]中使用[算法模型](../../features/algorithmic-models/understanding-models.md)功能。

1. 在[模型生成器](../../features/algorithmic-models/create-model.md)中或通过外部平台创建两个模型。
1. 从算法模型创建[算法特征](../../features/traits/create-algorithmic-traits.md)或将您自己的模型导入为载入的特征。
1. 创建互斥区段，使两个模型中的用户不会重叠：

   * 创建&#x200B;*模型1区段*&#x200B;和&#x200B;*模型2区段*。
   * 将&#x200B;*模型1区段*&#x200B;的区段规则设置为模型1特征[!DNL AND NOT]模型2特征，反之亦然，设置为&#x200B;*模型2区段*。

1. [在[!UICONTROL Audience Lab]中创建两个区段测试组](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)，一个以&#x200B;*模型1区段*&#x200B;作为基线，另一个以&#x200B;*模型2区段*&#x200B;作为基线。

   * 对于两个测试组，请保持变量相同：相同的目标、创意和转化特征。
   * 确保测试区段具有相似的用户数（例如，160万和180万正确，160万和1600万不正确）。
   * 在每个测试区段测试组中保留一个控制区段。 这样，您就可以预留每个区段的一小部分，而无需在测试中明确定向它们。

1. 检查结果：

   * [Audience Lab报表视图](../../features/audience-lab/audience-lab-reporting-view.md)将显示每个模型正在推动的转化次数。 对于基于转化的促销活动，产生最多转化的测试区段将表示表现最佳的模型。
   * 由于您具有控制区段，因此还可以根据“标准定位”评估模型的表现。 您不仅要测试一种模型与另一种模型，还要测试“此模型是否优于常规实践？”问题。

## 跨目标测试创意 {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

使用[!UICONTROL Audience Lab]测量创意内容在不同目标之间引发的转化次数。 此用例还允许您根据自然发生的转化来衡量创意的转化。

1. [创建区段测试组](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)，选择要对创意内容进行测试的区段作为基准区段。
1. 将基线区段拆分为测试区段和控制区段。
1. 将测试区段映射到您希望测试的不同目标。
1. 控制分部可扣留且不可映射到任何目的地。 测试创意不应以控制区段为目标，为自然发生的转化设置结果基线。
1. 指定测试的开始日期和结束日期。
1. 在目标中设置区段和创意。
1. [Audience Lab报告视图](../../features/audience-lab/audience-lab-reporting-view.md)将显示创意正在促进目标之间的转化次数。
1. 由于您创建了控制区段，因此您还可以根据自然发生的转化评估创意效果。 您正在测试以下问题：“此创意是否产生了比常规实践更高的转化率？”
