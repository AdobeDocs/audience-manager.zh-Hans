---
description: 从所有信号(包括已经在特征中使用的信号)创建新特征，并捕获特征创建后符合条件的未来受众。
seo-description: 从所有信号(包括已经在特征中使用的信号)创建新特征，并捕获特征创建后符合条件的未来受众。
seo-title: 从信号创建特征
title: 从信号创建特征
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# 从信号创建特征

从所有信号(包括已经在特征中使用的信号)创建新特征，并捕获特征创建后符合条件的未来受众。观看视频进行快速演示或阅读，了解详细信息：

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12&captions=chi_hans)

## Create Traits from Signal Dashboard {#create-traits-from-signal-dashboard}

The [!UICONTROL Signal Dashboard] allows you to create new traits from the [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals], and your saved searches.

创建新特征时，特征类型基于信号类型进行预设置：

* **[!UICONTROL Rule-based]** 特征用于实时信号、可操作日志文件和 [!DNL Adobe Analytics] 信号；

* **[!UICONTROL Onboarded]** 随附信号的特征。

To create new traits from the **[!UICONTROL Signal Dashboard]**, identify the signal that you want to use in the trait, then click the corresponding **[!UICONTROL Create Rule-Based Trait]** or **[!UICONTROL Create Onboarded Trait]** link.

![](assets/signals-create-trait.png)

You&#39;ll be redirected to the **[Trait Builder](../../features/traits/about-trait-builder.md)** to create your new trait(s).

## Create Traits from Signal Search {#create-traits-from-signal-search}

Create traits based on used or unused signals that are not shown in the [!UICONTROL Signal Dashboard].

搜索特定信号并根据结果创建基于规则或载入的特征。下面是如何执行此操作的方法：

1. Go to **[!UICONTROL Audience Data > Signals > Search]** and run a search based on the key-value pairs that you are looking for, or click **[!UICONTROL Search]** without entering any key-value pair to display all results.
2. 在结果列表中标识要在特征中使用的信号。
   * To create a trait from one signal, click the corresponding **[!UICONTROL Create Rule-Based Trait]** or **[!UICONTROL Create Onboarded Trait]** link.
   * To create a trait from multiple signals, click the corresponding check box of each signal, then click **[!UICONTROL Create Trait from Multiple Signals]**.
   >[!NOTE]
   >只能从同一类型的信号中创建特征。您不能基于实时信号和已载入的一个信号的组合创建特征。
   >
   > ![](assets/signals-create-trait-search.png)
   >您也可以从使用的信号中创建特征。Signals that are already used in traits have the number of traits displayed in the **[!UICONTROL Included in Traits]** column. 单击箭头可查看包含该信号的特征。
   >
   >![](assets/signals-used-traits.png)

3. Use the **[Trait Builder](../../features/traits/about-trait-builder.md)** to create your new traits.
