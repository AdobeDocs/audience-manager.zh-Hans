---
description: 使用“特征推荐”，在区段生成器中构建或编辑区段时，您能够获得可包含的其他推荐特征（与区段规则中的特征类似）。将推荐的特征添加到区段中，可增加目标受众。
seo-description: 在构建区段时获取实时特征推荐。
seo-title: 特征推荐
solution: Audience Manager
title: 特征推荐
uuid: null
translation-type: tm+mt
source-git-commit: a67998b925002438b20fdde81f1abec4acbd5602

---


# 特征推荐

在构建区段时获取实时特征推荐。

## 视频演示

首先观看以 [!UICONTROL Trait Recommendations] 下视频，然后阅读以了解更多信息。

>[!VIDEO](https://video.tv.adobe.com/v/26228/?captions=chi_hans)

下一个视频概述了工作流 [!UICONTROL Marketplace Recommendations]程，向您展示如何从中的数据馈送向区段添加特征推荐 [!UICONTROL Audience Marketplace]。

>[!VIDEO](https://video.tv.adobe.com/v/29363/?captions=chi_hans)

## 概述

[!UICONTROL Trait Recommendations]由Audience Manager提 [!DNL Adobe Sensei]供支持，将数据科学引入Audience manager的日常工作流程中。
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule.

Audience manager会根据您的第一方特征、部分特征和部分特 **[!UICONTROL Recommendations]** 征来显示 **[!UICONTROL Audience Marketplace]**&#x200B;推荐的特 **[!UICONTROL Recommendations from Marketplace]** 征。

![特征推荐概述](assets/trait-recommendations-overview-full.png)

将推荐的特征添加到区段中，可增加目标受众。

**简而言之：**

* Audience manager在部分中显示第一方 [!UICONTROL Recommendations] 特征。 您未订阅的公共和私有源的市场推荐显示在该部 [!UICONTROL Recommendations from Marketplace] 分。
* Audience manager最多显示50个与区段规则中相似的特征。
* 您可以过滤掉不想从中看到任何推荐的数据源。
* 在计算相似性时，Audience Manager会考虑 [在过去](../../reference/ids-in-aam.md) 30天内符合该特征的UUID。
* 如果看到错误消息“未找到类似特征。 特征可能太新。”，这表示过去30天中该特征没有活动，或者Audience manager尚未更新该特征的推荐。 请在24小时后重试。

## 用例

您 [!UICONTROL Trait Recommendations]可以改进工作流程，具体取决于您使用Audience Manager的方式：

* 作为营销人员，您可以借助类似特征快速找到对补充产品感兴趣的受众，从而扩大受众范围。
* 如果您将Audience manager用作出版商，则可了 [!UICONTROL Trait Recommendations]解受众行为并为广告销售或用户赢取构建更好的细分。

## 特质推荐与算法模型的区别

### 算法模型

[!UICONTROL Algorithmic Models] 不仅可以找到最具影响力的特征，而且还可以根据这些特征对用户进行分数，并为每个用户分配一个单独的分数。 然后，您创建算法特征来定位用户。 借助中的准确性和范围控 [!UICONTROL Trait Builder]件，您可以指定所有具有要定位的影响力特征的用户中的哪些用户。

[!UICONTROL Algorithmic Models] 使您能够选择不同准确度级别的用户并测试哪 [!UICONTROL Audience Lab] 组用户转换效果更好。 请参阅Audience lab中的比较模 [型中的详细用例](../../features/audience-lab/audience-lab-use-cases.md#compare-models)。

在 [!UICONTROL Algorithmic Models]中，该模型每8天运行一次，并刷新符合算法特征的用户。

### 特征推荐

[!UICONTROL Trait Recommendations] 是一种快速获取与您在区段中使用的特征类似的其他特征洞察的方法。

您应当在以下情况下 [!UICONTROL Trait Recommendations] 使用：

* 在构建细分时，您需要快速洞察；
* 您使用细分进行简短的营销活动，或者您希望快速抑制转化受众；
* 您正在尝试将触及力最大化。

## 工作流

在区段生成器中构建或编 [辑区段时](segment-builder.md)，您可以探索与区段规则中的特征相似的特征。 “区 [段生成器](segment-builder.md) ”工作流对于新区段和现有区段非常相似：

### 新细分

1. 转到“受 **众数据”&gt;“区段**”，然后单 **击“添加新”**。
2. 在“特 **征** ”下拉框中，向段规则添加至少一个特征。
3. 您可以在部分中看到第一方推荐的 **[!UICONTROL Recommendations]** 特征，在部分中看到第三方推荐的 **[!UICONTROL Recommendations from Marketplace]** 特征。 所有这些推荐都与您添加到区段规则的特征相似。 向下滚动以查看所有推荐的特征。
4. （可选）要从某些数据源中排除推荐的第一方特征，请单击要排除的数据源的 **X** 符号。
   > [!NOTE]
   >
   > 被排除的数据源显示在建议特征列表的正上方。 单击 **灰色框中的X** ，删除排除项并再次查看各个数据源的结果。
5. 要向区段规则添加推荐的特征，请单击 **+符号** 。

> [!IMPORTANT]
> 在向区 [!UICONTROL Marketplace] 段添加特征时，这些特征仅用于区段估计，直到您订阅相应的数据源。 来自您未订阅的数据馈送的特征在特征列表中用购物车图标进行标记。 单击特征名称可转到数据馈送页面并订阅该页面。
> ![marketplace-not-subscripted](assets/trait-recommendations-marketplace.png)
> 仅在订阅相应的数据源后，才可保存具有第三方特征的区段。

### 现有细分

1. 转到 **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**，选择要编辑的区段，然后单击编 ![辑](assets/edit-button.png)。
1. 向下滚动到 [!UICONTROL Traits] 下拉框。
1. 您可以看到推荐的特征，这与区段规则中已有的特征类似。 向下滚动以查看所有推荐的特征。
1. （可选）要从某些数据源中排除推荐的特征，请单击要排除的 **X** 符号。
   > [!NOTE]
   >
   > 被排除的数据源显示在建议特征列表的正上方。 单击 **灰色框中的X** ，删除排除项并再次查看各个数据源的结果。
1. 要向区段规则添加推荐的特征，请单击 **+符号** 。

在创建或编辑区段并向区段规则添加特征时，您会看到最多50个推荐特征，与您添加的特征类似。 如果区段规则包含多个特征，Audience Manager会在区段规则中使用循环法来显示每个特征的最佳匹配项，然后显示每个特征的次佳匹配项，依此类推，在区段规则中，每个特征的最大50个特征的匹配项按人口划分。

![三个基本特征](assets/three-base-traits.png)

例如，当区段规则中有三个特征时，建议的特征为：

1. 最适合特征3（人口最多的特征）;
2. 特征1的最佳匹配；
3. 特征2的最佳匹配；
4. 特征3的次优匹配；
5. 特征1的次优匹配，等等，直到达到50个特征。

要获取特定特征的推荐，您可以单击区段规则(1)或推荐的特征视图(2)中的特征。

![base-traits-example](assets/three-base-traits-numbered.png)

单击第一方特征可打开一个弹出窗口，如下图所示。 如果建议的特征不是区段的一部分，则可以按 **+将其添加到区段**。

![添加到区段](assets/add_to_segments.png)

> [!TIP]
>
>在特征信息弹出窗口中生成推荐时，会考虑主页中被排除的数据源。 此外，如果在此视图中排除数据源，则排除将应用于主页。

> [!NOTE]
>
> 建议的特征可以是您订阅的数据源中的第一方特征或第三方特征 [!UICONTROL Audience Marketplace]。

## 工作原理

要生成特征推荐，Audience Manager会计算目标特征与您帐户有权访问的每个其他特征（包括第三方数据）之间的 [](https://en.wikipedia.org/wiki/Jaccard_index) Jaccard相似性。 然后，Audience manager显示最多50个相似性最高的特征。

## 特征相似性得分

Audience manager通过 [!UICONTROL Trait Similarity Score] 计算交叉点和并数来计算两个特征之 [!UICONTROL UUID]间的数量，然后将两个特征相除。 对于两个特征A和B，计算如下所示：

![Jaccard相似性](assets/jaccard_similarity.png)

另请参见下面的两个示例。

### 示例1 —— 低特征相似性得分

给定两个特征A和B，假设每个特征的人口为1,000,000 [!UICONTROL UUID]s，其中25,000 [!UICONTROL UUID]s符合这两个特征。
使用上述公式，这将导致：25,000 / 1,975,000 = 0.012。这个低，这 [!UICONTROL Trait Similarity Score]两个特征是非常不一样的。

![trait-recommendations-low-overlap](assets/Trait-Recommendations-Low-overlap.png)

### 示例2 —— 特征相似性得分

如果相同的特征A和B具有400,000个UUID, [!UICONTRL ]则符合这两个特征， [!UICONTROL Trait Similarity Score] 则其值要高得多：400,000 / 1,600,000 = 0.25

![trait-recommendations-high-overlap](assets/Trait-Recommendations-High-overlap.png)

### 如何解读特征相似性得分

使用下表作为特征相似性的粗略指南。 本指南基于在大多数特征上观察到的相似性得分。

| [!UICONTROL Trait Similarity Score] | 重要性 |
---------|----------|
| 0.1及更高版本 | 特征之间的高相似性 |
| 0.03 - 0.1 | 特征之间的中等相似性 |
| 0.01 - 0.03 | 特征之间的低相似性 |
| 0 - 0.01 | 特征之间的相似性很低 |

## 基于角色的访问控制(RBAC)

对于使用( [!UICONTROL Role-Based Access Controls][!UICONTROL RBAC])的公司，您需要具有创建和编辑区段的权限才能查看推荐的特征。 而且，您看到的推荐特征只是您有权通过访问的数据源中的特征 [!UICONTROL RBAC]。 阅读此处有关控 [!UICONTROL RBAC] 件的 [更多信息](../administration/administration-overview.md)。

## 限制

* 目前，Audience manager不将文件夹特征显示为建议的特征。 阅读此处有关文件夹特征的 [更多信息](../traits/manage-folder-traits.md)。
* 在显示特征推荐时，Audience manager不会考虑区段规 [!DNL Boolean] 则中的[!DNL AND]运 [!DNL OR]算符(、 [!DNL NOT]、)。
