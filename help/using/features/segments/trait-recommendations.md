---
description: 使用“特征推荐”，在区段生成器中构建或编辑区段时，您能够获得可包含的其他推荐特征（与区段规则中的特征类似）。将推荐的特征添加到区段中，可增加目标受众。
seo-description: 在构建细分时获得实时特征推荐。
seo-title: 特征推荐
solution: Audience Manager
title: 特征推荐
uuid: null
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# 特征推荐

在构建细分时获得实时特征推荐。

## 视频演示

首先观看特征推荐视频，然后阅读更多信息。

>[!VIDEO](https://video.tv.adobe.com/v/26228/?captions=chi_hans)

## 概述

[!UICONTROL Trait Recommendations]以数据科学为后盾，将数据科学引入Audience [!DNL Adobe Sensei]Manager日常工作流程中。
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. 将推荐的特征添加到区段中，可增加目标受众。

![特征推荐概述](assets/trait-recommendations-overview.png)

**在nutshell中：**

* Audience Manager将当前订阅数据源中的第一方特征和第三方特征显示为建议的特征。
* Audience Manager最多可显示与区段规则类似的50个特征。
* 您可以过滤出不希望查看任何推荐的数据源。
* 在计算相似性时，Audience Manager将在 [过去30天内符合特征的UI](../../reference/ids-in-aam.md) 视为合格。
* 如果看到错误消息“找不到类似的特征。特征可能过于新。“这意味着，过去30天内该特征没有活动，或者Audience Manager尚未更新该特征的建议。请在24小时后重试。

## 用例

通过 [!UICONTROL Trait Recommendations]使用Audience Manager，您可以改进工作流程：

* 作为营销人员，您可以通过类似特征快速找到对互补产品感兴趣的受众，从而提高受众范围。
* 如果您使用Audience [!UICONTROL Trait Recommendations]Manager作为publisher，您可以了解受众行为并为广告销售或用户赢取建立更好的细分。

## 特征推荐与算法模型之间的差异

### 算法模型

[!UICONTROL Algorithmic Models] 不仅找到最有影响力的特征，而且还根据这些特征给用户评分，为每个用户分配一个单独的分数。然后创建算法特征以定位用户。通过准确性和触及 [!UICONTROL Trait Builder]力控制，您可以指定所有具有影响力特征的用户。

[!UICONTROL Algorithmic Models] 使您能够选择不同准确性级别的用户，并测试 [!UICONTROL Audience Lab] 用户组的转换效果。请参阅Audience Lab [中比较模型中的详细用例](../../features/audience-lab/audience-lab-use-cases.md#compare-models)。

在中 [!UICONTROL Algorithmic Models]，该模型每天运行一次，并refre符合算法特征的用户。

### 特征推荐

[!UICONTROL Trait Recommendations] 是一种快速获取其他特征的方法，它类似于您在区段中使用的其他特征。

您应在以下情况下使用 [!UICONTROL Trait Recommendations] ：

* 您需要在构建区段时快速洞察；
* 您正在将细分用于简短营销活动，或者在您希望快速抑制转化受众时使用细分；
* 您正在尝试最大化覆盖面。

## 工作流

在 [区段生成器](segment-builder.md)中构建或编辑区段时，您可以探索类似区段规则中特征的特征。区段生成器工作流对于新的和现有的区段非常相似：

### 新区段

1. 在 **“受众数据”&gt;“区段**”中，选择 **“添加新**&#x200B;内容”。
2. 在 **“特征”** 下拉框中，至少向区段规则中添加一个特征。
3. 您现在可以看到类似于您添加到区段规则的特征的推荐特征。向下滚动以查看所有推荐的特征。
4. (可选)要排除特定数据源中的推荐特征，请单击要排除的数据源 **的X** 符号。
   > [!NOTE]
   > 
   >被排除的数据源显示在建议特征列表上方。按灰色框中的 **X** 可删除排除，并可再次查看各个数据源中的结果。
5. 要向区段规则添加建议的特征，请单击 **+** 符号。

### 现有区段

1. 转至 **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**，选择要编辑的区段，然后按 ![编辑](assets/edit-button.png)。
1. 向下滚动到 [!UICONTROL Traits] 下拉框。
1. 您可以看到推荐的特征，这类似于区段规则中已有的特征。向下滚动以查看所有推荐的特征。
1. (可选)要排除特定数据源中的推荐特征，请单击要排除的数据源 **的X** 符号。
   > [!NOTE]
   > 
   >被排除的数据源显示在建议特征列表上方。按灰色框中的 **X** 可删除排除，并可再次查看各个数据源中的结果。
1. 要向区段规则添加建议的特征，请单击 **+** 符号。

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

单击特征将打开一个弹出窗口，如下图所示。如果推荐的特征不是区段的一部分，则可以按 **+**&#x200B;将其添加到区段。

![](assets/add_to_segments.png)

> [!TIP]
>
>在特征信息弹出窗口中生成推荐时，将考虑主页中被排除的数据源。如果您在此视图中排除数据源，排除将应用于主页。

> [!NOTE]
>
> 建议的特征可能是您订阅的源的第一方特征或第三方特征。

## 工作原理

为了生成特征建议，Audience Manager计算目标特征和您的帐户访问的每个其他特征之间的 [](https://en.wikipedia.org/wiki/Jaccard_index) Jacard相似性(包括第三方数据)。Audience Manager随后最多可显示最相似的50个特征。

## 特征相似性得分

Audience Manager通过计算相交和联合的数量计算两个特征 [!UICONTROL Trait Similarity Score] 之间的差异， [!UICONTROL UUID]然后除以两者。对于两个特征A和B，计算如下：

![](assets/jaccard_similarity.png)

另请参见下面的两个示例。

### 示例-低特征相似性得分

假设有两个特征A和B，假设每个特征有1,000， [!UICONTROL UUID]000s，25,000 [!UICONTROL UUID]s符合两个特征。
使用上面的公式，这将导致：25,000/1,975,000=0.012。这很低 [!UICONTROL Trait Similarity Score]，两个特征截然不同。

![](assets/Trait-Recommendations-Low-overlap.png)

### 示例-特征相似性得分

如果同一特征A和B具有400，000 [!UICONTRL UUID]，可符合两种特征，则要 [!UICONTROL Trait Similarity Score] 高得多：
400,000/1,600，000=0.25

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

对于使用 [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC])的公司，您需要具有创建和编辑区段的权限，以便查看推荐的特征。此外，您所看到的推荐特征只是从您有权访问的数据源中看到的特征 [!UICONTROL RBAC]。请阅读此处 [!UICONTROL RBAC] 的有关控件 [的更多](../administration/administration-overview.md)信息。

## 限制

* 当前，Audience Manager不会显示文件夹特征作为建议的特征。在此处阅读有关文件夹特征 [的更多信息](../traits/manage-folder-traits.md)。
* 显示Travical Recommendations时，Audience Manager不会在区段规则中考虑 [!DNL Boolean] 操作符([!DNL AND]， [!DNL OR]， [!DNL NOT])。