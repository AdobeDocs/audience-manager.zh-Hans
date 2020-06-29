---
description: 使用“特征推荐”，在区段生成器中构建或编辑区段时，您能够获得可包含的其他推荐特征（与区段规则中的特征类似）。将推荐的特征添加到区段中，可增加目标受众。
seo-description: 在构建区段时获取实时特征推荐。
seo-title: 特征推荐
solution: Audience Manager
title: 特征推荐
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1573'
ht-degree: 8%

---


# 特征推荐

根据您自己的第一方特征和数据源构建细分时，获取实时特征 [!UICONTROL Audience Marketplace] 推荐。

## 视频演示

开始，只需观 [!UICONTROL Trait Recommendations] 看下面的视频，然后阅读以了解更多信息。 视频演示向您展示如何处理来自您自己的第一方特征的建议以及来自您已订阅的 [!UICONTROL Audience Marketplace] 数据 *源的特征建议*。

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

下一个视频概述了工作流 [!UICONTROL Marketplace Recommendations]程，向您展示如何根据中数据馈送的推荐将特征添加到区段 [!UICONTROL Audience Marketplace]。 这些建议基于您未订 *阅的数据源*。

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## 概述

[!UICONTROL Trait Recommendations]在您的支 [!DNL Adobe Sensei]持下，将数据科学引入Audience Manager的日常工作流。
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule.

Audience Manager显示您的特征推荐，包括第一方特征、部 **[!UICONTROL Recommendations]** 分特征和部 **[!UICONTROL Audience Marketplace]**&#x200B;分特征 **[!UICONTROL Recommendations from Marketplace]** 推荐。

将推荐的特征添加到区段中，可增加目标受众。

![特征推荐概述](assets/trait-recommendations-overview-full.png)

**简而言之：**

* Audience Manager在节中显示第一方 [!UICONTROL Recommendations] 特征。 您未订阅的公共和私有源的市场推荐在部分中可 [!UICONTROL Recommendations from Marketplace] 见。 单击源名称以转 [!UICONTROL Audience Marketplace] 到并订阅。
* Audience Manager显示最多50个与段规则中的特征相似的特征。
* 您可以过滤掉不想从中看到任何推荐的数据源。
* 在计算相似性时，Audience Manager [会考虑](../../reference/ids-in-aam.md) 过去30天内限定为特征的UUID。
* 如果看到错误消息“未找到类似特征。 特征可能太新。”，这意味着过去30天内没有该特征的活动，或者Audience Manager尚未更新该特征的建议。 请在24小时后重试。

## 用例

您 [!UICONTROL Trait Recommendations]可以根据您使用工作流的方式改进Audience Manager:

* 作为营销人员，您可以借助相似特征快速找到对补充产品感兴趣的受众，从而扩大触及范围。
* 如果您以Audience Manager为出版商，则可 [!UICONTROL Trait Recommendations]以了解受众行为并为广告销售或用户赢取建立更好的细分。
* 作为数 [!UICONTROL Audience Marketplace] 据购买者，我希望无需浏览大量数据源即可发现相关的第三方数据。
* 作为数 [!UICONTROL Audience Marketplace] 据提供商，我希望向购买者推荐相关数据，以便从最佳和相关订阅中受益。

## 特质推荐与算法模型的差异

### 算法模型

[!UICONTROL Algorithmic Models] 不仅可以找到最具影响力的特征，还可以根据这些特征对用户进行评分，并为每个用户分配一个个人得分。 然后，便可以通过创建算法特征来定位用户。With accuracy and reach controls in the [!UICONTROL Trait Builder], you can specify which users amongst all those who have the influential traits you want to target.

[!UICONTROL Algorithmic Models] 使您能够选择不同准确度级别的用户，并测试哪 [!UICONTROL Audience Lab] 组用户转换效果更好。 有关详细用例，请参阅[在 Audience Lab 中比较模型](../../features/audience-lab/audience-lab-use-cases.md#compare-models)。

In [!UICONTROL Algorithmic Models], the model runs every 8 days and refreshes the users qualified for algorithmic traits.

### 特征推荐

[!UICONTROL Trait Recommendations] 是一种快速的方法，可让您深入了解与您在区段中使用的特征相似的其他特征。

您应当在以下时 [!UICONTROL Trait Recommendations] 间使用：

* 构建区段时需要快速获取信息；
* 要将区段用于短期促销活动，或者希望快速抑制转化的受众；
* 想要最大化范围。

## 工作流

在区段生成器中构建或编 [辑区段](segment-builder.md)，您可以探索与区段规则中的特征相似的特征。 区段 [生成器](segment-builder.md) (Segment Builder)工作流程对于新区段和现有区段非常相似：

### 新细分

1. 转至 **受众数据>区段**，然后单击 **添加新**。
1. 在“特 **征** ”下拉框中，至少向段规则添加一个特征。
1. 您可以在部分查看订阅的源 [!UICONTROL Audience Marketplace] 中的第一方推荐特征和特征推荐 **[!UICONTROL Recommendations]** 。 该 **[!UICONTROL Recommendations from Marketplace]** 部分显示您未订阅源的特征推荐。 所有这些建议都与您添加到区段规则的特征相似。 向下滚动以查看所有推荐特征。
1. （可选）要从某些数据源中排除推荐的第一方特征，请 **单击** “要排除的数据源的X”符号。

   >[!NOTE]
   >
   >被排除的数据源显示在建议特征列表的正上方。 单 **击灰** 色框中的X可删除排除项，并再次查看各个数据源的结果。
1. 要向区段规则添加推荐特征，请单 **击+** 符号。

>[!IMPORTANT]
>
>在向区 [!UICONTROL Marketplace] 段添加特征时，这些特征仅用于区段估计，直到您订阅相应的数据源。 来自您未订阅的数据源的特征在特征列表中标有购物车图标。 单击特征名称可转到数据源页面并订阅它。
>
>![marketplace-not-subscriped](assets/trait-recommendations-marketplace.png)
>
>仅在订阅相应数据服务后，才能保存具有第三方特征的区段。

### 现有细分

1. 转到> **[!UICONTROL Audience Data],[!UICONTROL Segments]**选择要编辑的区段，然后单击![编辑](assets/edit-button.png)。
1. 向下滚动 [!UICONTROL Traits] 到下拉框。
1. 您可以看到推荐的特征，这些特征与段规则中已有的特征相似。 向下滚动以查看所有推荐特征。
1. （可选）要从某些数据源中排除推荐的特 **征** ，请单击要排除的数据源的X符号。

   >[!NOTE]
   >
   >被排除的数据源显示在建议特征列表的正上方。 单 **击灰** 色框中的X可删除排除项，并再次查看各个数据源的结果。
1. 要向区段规则添加推荐特征，请单 **击+** 符号。

在创建或编辑区段并向区段规则添加特征时，最多可看到50个推荐特征，与您添加的特征相似。 如果区段规则包含多个特征，则Audience Manager使用循环法来显示每个特征的最佳匹配，然后在每个特征中显示每个特征的次佳匹配，依此类推，在区段规则中按人口划分的最大50个特征。

![三种基本特征](assets/three-base-traits.png)

例如，当区段规则中有三个特征时，建议的特征为：

1. 最适合特征3（人口最多的特征）;
1. 特征1的最佳匹配；
1. 特征2的最佳匹配；
1. 特征3次优匹配；
1. 特征1的次优匹配，等等，直到你达到50个特征。

要获取特定特征的推荐，您可以单击段规则(1)或推荐特征视图(2)中的特征。

![base-traits-example](assets/three-base-traits-numbered.png)

单击第一方特征可打开一个弹出窗口，如下图所示。 如果建议的特征不是区段的一部分，则可以按+将其添加到区段 **中**。

![添加到区段](assets/add_to_segments.png)

>[!TIP]
>
>在特征信息弹出窗口中生成推荐时，会考虑主页中被排除的数据源。 此外，如果在此视图中排除数据源，则排除将应用于主页。

>[!NOTE]
>
>建议的特征可以是您订阅的数据源中的第一方特征或第三方特征 [!UICONTROL Audience Marketplace]。

## 工作原理

要生成特征推荐，Audience Manager会计 [算目标特征与您帐户有权访问的所有其他特征](https://en.wikipedia.org/wiki/Jaccard_index) （包括第三方数据）之间的Jaccard相似性。 Audience Manager显示最多50个相似性最高的特征。

## 特征相似性得分 {#trait-similarity-score}

Audience Manager通 [!UICONTROL Trait Similarity Score] 过计算交集和合并数来计算两个特征 [!UICONTROL UUID]之间的数，然后将两个特征分。 对于两个特征A和B，计算如下所示：

![积分相似性](assets/jaccard_similarity.png)

另请参见下面的两个示例。

### 示例1 —— 低特征相似性得分

假设A和B两个特征，假设每个特征的人口数为1,000,000 [!UICONTROL UUID]s，其中25,000 [!UICONTROL UUID]s符合这两个特征。
使用上述公式，这将导致： 25,000 / 1,975,000 = 0.012。这是一个低值，这两 [!UICONTROL Trait Similarity Score]个特征是非常不同的。

![trait-recommendations-low-overlap](assets/Trait-Recommendations-Low-overlap.png)

### 示例2 —— 特征相似性得分

如果相同的特征A和B具有400,000 [!UICONTROL UUID]个符合这两个特征，则 [!UICONTROL Trait Similarity Score] 要高得多：
400,000 / 1,600,000 = 0.25

![特质——推荐——高重叠](assets/Trait-Recommendations-High-overlap.png)

### 如何解读特质相似性评分

使用下表作为特征相似性的粗略指南。 本指南基于在大多数特征上观察到的相似性得分。

| [!UICONTROL Trait Similarity Score] | 意义 |
---------|----------|
| 0.1及更高版本 | 特征之间的高相似性 |
| 0.03 - 0.1 | 特征之间的中等相似性 |
| 0.01 - 0.03 | 特征之间的低相似性 |
| 0 - 0.01 | 特征之间的相似性很低 |

## 基于角色的访问控制(RBAC)

对于使用( [!UICONTROL Role-Based Access Controls] )[!UICONTROL RBAC]的公司，您需要具有创建和编辑区段的权限，才能查看推荐的特征。 您看到的特征建议仅是您有权通过访问的数据源 [!UICONTROL RBAC]。

>[!IMPORTANT]
>
>要添加 [!UICONTROL Marketplace Recommendations] 到区段，用户必须先订阅相应的数据服务。 只有具有管理员权限的用户才能订 [!UICONTROL Audience Marketplace] 阅数据服务。

请在此处阅读有 [!UICONTROL RBAC] 关控 [件的更多信息](../administration/administration-overview.md)。

## 限制

* 目前，Audience Manager不将文件夹特征显示为推荐特征。 请在此处阅读有关文件夹特征的 [更多信息](../traits/manage-folder-traits.md)。
* 显示特征推荐时，Audience Manager不考虑段 [!DNL Boolean] 规则中[!DNL AND]的 [!DNL OR]运算符( [!DNL NOT]、、)。
