---
description: 从所有信号（包括已在特征中使用的信号）创建新特征，并捕获在特征创建后符合条件的未来受众。
seo-description: 从所有信号（包括已在特征中使用的信号）创建新特征，并捕获在特征创建后符合条件的未来受众。
seo-title: 从信号创建特征
title: 从信号创建特征
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# 从信号创建特征

从所有信号（包括已在特征中使用的信号）创建新特征，并捕获在特征创建后符合条件的未来受众。 观看视频以快速进行演示或阅读以了解详细信息：

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12&captions=chi_hans)

## 从Signal Dashboard创建特征 {#create-traits-from-signal-dashboard}

使用 [!UICONTROL Signal Dashboard] 该选项，您可以从保存的搜索 [!UICONTROL Top Unused Signals]、 [!UICONTROL New Unused Signals]和搜索创建新特征。

创建新特征时，根据信号类型预先设置特征类型：

* **[!UICONTROL Rule-based]** 实时信号、可操作日志文件和信号的特 [!DNL Adobe Analytics] 征；

* **[!UICONTROL Onboarded]** 已载入信号的特征。

要从中创建新特征 **[!UICONTROL Signal Dashboard]**，请标识要在特征中使用的信号，然后单击相应的 **[!UICONTROL Create Rule-Based Trait]** 或链 **[!UICONTROL Create Onboarded Trait]** 接。

![](assets/signals-create-trait.png)

您将被重定向到 **[Trait Builder](../../features/traits/about-trait-builder.md)** ，以创建新特征。

## 通过信号搜索创建特征 {#create-traits-from-signal-search}

根据未使用或未使用的信号创建特征（未在中显示） [!UICONTROL Signal Dashboard]。

搜索特定信号并基于结果创建基于规则或载入的特征。 下面介绍如何实现此操作：

1. 转到并 **[!UICONTROL Audience Data > Signals > Search]** 根据您要查找的键值对运行搜索，或者单击而不输入键值对以显示 **[!UICONTROL Search]** 所有结果。
2. 在结果列表中标识要在特征中使用的信号。
   * 要从一个信号创建特征，请单击相应的 **[!UICONTROL Create Rule-Based Trait]** 或链 **[!UICONTROL Create Onboarded Trait]** 接。
   * 要从多个信号创建特征，请单击每个信号的相应复选框，然后单击 **[!UICONTROL Create Trait from Multiple Signals]**。
   >[!NOTE]
   >您只能从相同类型的信号创建特征。 不能根据实时信号和载入的信号的组合创建特征。
   >
   > ![](assets/signals-create-trait-search.png)
   >您也可以根据使用的信号创建特征。 已在特征中使用的信号具有列中显示的特征数 **[!UICONTROL Included in Traits]** 量。 单击箭头可查看包含信号的特征。
   >
   >![](assets/signals-used-traits.png)

3. 使用 **[Trait Builder](../../features/traits/about-trait-builder.md)** 创建新特征。
