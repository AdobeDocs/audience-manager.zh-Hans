---
description: 使用“特征推荐”，在区段生成器中构建或编辑区段时，您能够获得可包含的其他推荐特征（与区段规则中的特征类似）。将推荐的特征添加到区段中，可增加目标受众。
seo-description: 在构建细分时获得实时特征推荐。
seo-title: 特征推荐
solution: Audience Manager
title: 特征推荐
uuid: null
translation-type: tm+mt
source-git-commit: e369038fbc83e28d10da24060699488faf783511

---


# 特征推荐

在构建细分时获得实时特征推荐。

## 概述

[!UICONTROL Trait Recommendations]以数据科学为后盾，将数据科学引入Audience [!DNL Adobe Sensei]Manager日常工作流程中。
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. 将推荐的特征添加到区段中，可增加目标受众。

![特征推荐概述](assets/trait-recommendations-overview.png)

**在nutshell中：**

* Audience Manager将当前订阅数据源中的第一方特征和第三方特征显示为建议的特征。
* Audience Manager最多可显示与区段规则类似的50个特征。
* 您可以过滤出不希望查看任何推荐的数据源。
* When calculating similarities, Audience Manager considers [UUIDs](../../reference/ids-in-aam.md) that qualified for the trait during the last 30 days.
* 如果看到错误消息“找不到类似的特征。特征可能过于新。“这意味着，过去30天内该特征没有活动，或者Audience Manager尚未更新该特征的建议。请在24小时后重试。

## 用例

With [!UICONTROL Trait Recommendations], you can improve your workflows, depending on how you use Audience Manager:

* 作为营销人员，您可以通过类似特征快速找到对互补产品感兴趣的受众，从而提高受众范围。
* If you use Audience Manager as a publisher, with [!UICONTROL Trait Recommendations], you can understand audience behavior and build better segments for ad sales or user acquisition.

## 特征推荐与算法模型之间的差异

### 算法模型

[!UICONTROL Algorithmic Models] 不仅找到最有影响力的特征，而且还根据这些特征给用户评分，为每个用户分配一个单独的分数。然后创建算法特征以定位用户。With accuracy and reach controls in the [!UICONTROL Trait Builder], you can specify which users amongst all those who have the influential traits you want to target.

[!UICONTROL Algorithmic Models] 使您能够选择不同准确性级别的用户，并测试 [!UICONTROL Audience Lab] 用户组的转换效果。See the detailed use case in [Compare Models in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models], the model runs every 8 days and refreshes the users qualified for algorithmic traits.

### 特征推荐

[!UICONTROL Trait Recommendations] 是一种快速获取其他特征的方法，它类似于您在区段中使用的其他特征。

You should use [!UICONTROL Trait Recommendations] when:

* 您需要在构建区段时快速洞察；
* 您正在将细分用于简短营销活动，或者在您希望快速抑制转化受众时使用细分；
* 您正在尝试最大化覆盖面。

## 工作流

When building or editing a segment in [Segment Builder](segment-builder.md), you can explore traits similar to the traits in the segment rule. 区段生成器工作流对于新的和现有的区段非常相似：

### 新区段

1. In **Audience Data &gt; Segments**, select **Add New**.
1. In the **Traits** drop-down box, add at least one trait to the segment rule.
1. 您现在可以看到类似于您添加到区段规则的特征的推荐特征。向下滚动以查看所有推荐的特征。
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
   > [!NOTE]
   > 
   >被排除的数据源显示在建议特征列表上方。Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

### 现有区段

1. Go to **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**, select the segment you want to edit and press ![Edit](assets/edit-button.png).
1. Scroll down to the [!UICONTROL Traits] drop-down box.
1. 您可以看到推荐的特征，这类似于区段规则中已有的特征。向下滚动以查看所有推荐的特征。
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
   > [!NOTE]
   > 
   >被排除的数据源显示在建议特征列表上方。Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

创建或编辑区段并将特征添加到区段规则时，最多可看到50个推荐的特征，类似于已添加的特征。如果区段规则包含多个特征，Audience Manager使用圆形Robin方法为每个特征显示最佳匹配项，然后为每个特征显示第二个最佳匹配项，在区段规则中为每个特征的第二个最佳匹配项。

![三个基本特征](assets/three-base-traits.png)

例如，如区段规则中有三个特征，如下所示，建议的特征如下所示：

1. 特征3(特征数量最大的特征)；
2. 特征1；
3. 特征2的最佳匹配；
4. 适用于特征的第二个最佳匹配项；
5. 特征1的第二个最佳匹配项，依此类推直至达到50个特征。

要获取特定特征的推荐，您可以单击区段规则(1)中的特征或建议的特征视图(2)。

![](assets/three-base-traits-numbered.png)

单击特征将打开一个弹出窗口，如下图所示。If the recommended traits are not part of the segment, you can add them to the segment by pressing **+**.

![](assets/add_to_segments.png)

> [!TIP]
>
>在特征信息弹出窗口中生成推荐时，将考虑主页中被排除的数据源。如果您在此视图中排除数据源，排除将应用于主页。

> [!NOTE]
>
> 建议的特征可能是您订阅的源的第一方特征或第三方特征。

## 工作原理

To produce trait recommendations, Audience Manager computes the [Jaccard similarity](https://en.wikipedia.org/wiki/Jaccard_index) between the target trait and every other trait that your account has access to, including third-party data. Audience Manager随后最多可显示最相似的50个特征。

## 特征相似性得分

Audience Manager calculate the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL UUID]s and then divide the two. 对于两个特征A和B，计算如下：

![](assets/jaccard_similarity.png)

另请参见下面的两个示例。

### 示例-低特征相似性得分

Given two traits A and B, let's say each of the traits has a population of 1,000,000 [!UICONTROL UUID]s, 25,000 [!UICONTROL UUID]s of which qualify for both traits.
Using the formula above, this will result in: 25,000 / 1,975,000 = 0.012. This is a low [!UICONTROL Trait Similarity Score], the two traits are very dissimilar.

![](assets/Trait-Recommendations-Low-overlap.png)

### 示例-特征相似性得分

If the same traits A and B had 400,000 [!UICONTRL UUID]s that qualify for both traits, the [!UICONTROL Trait Similarity Score] is much higher:
400,000 / 1,600,000 = 0.25

![](assets/Trait-Recommendations-High-overlap.png)

### 如何解释特征相似性得分

使用下表作为特征相似性的粗略指南。本指南基于大多数特征中观察到的相似性分数。

| [!UICONTROL Trait Similarity Score] | 重要性 |
---------|----------|
| 0.1及更高版本 | 特征之间的高相似性 |
| 0.03 - 0.1 | 特征之间的中等相似性 |
| 0.01 - 0.03 | 特征之间的相似性低 |
| 0 - 0.01 | 特征之间的相似性很低 |

## 基于角色的访问控制(CLUAC)

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), you need to have permission to create and edit segments in order to see recommended traits. And, the recommended traits you see are only the ones from data sources that you have access to via [!UICONTROL RBAC]. Read more about [!UICONTROL RBAC] controls [here](../administration/administration-overview.md).

## 限制

* 当前，Audience Manager不会显示文件夹特征作为建议的特征。Read more about folder traits [here](../traits/manage-folder-traits.md).
* When displaying Trait Recommendations, Audience Manager does not take into account [!DNL Boolean] operators ([!DNL AND], [!DNL OR], [!DNL NOT]) in segment rules.