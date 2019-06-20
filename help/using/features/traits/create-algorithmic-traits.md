---
description: 介绍了算法特征创建过程独有的步骤和功能。
seo-description: 介绍了算法特征创建过程独有的步骤和功能。
seo-title: 创建算法特征
solution: Audience Manager
title: 创建算法特征
uuid: 50c2d2d1-f412-479b-bb70-4f139429 c388
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create Algorithmic Traits {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

To create an algorithmic trait, go to [!UICONTROL Traits] and follow the steps below:

1. Click **[!UICONTROL Create New Trait]** and select **[!UICONTROL Algorithmic]** from the drop down menu.
1. In the [Basic Information](../../features/traits/create-onboarded-rule-based-traits.md) section
   * 命名特征。
   * 选择数据源。
   * 选择存储文件夹。
1. Expand the [!UICONTROL Configuration] pane and click **[!UICONTROL Browse All Models]**.
这将打开一个新窗口，可让您选择要用于特征的模型。
1. Select a model and click **[!UICONTROL Add Selected Model to Trait]**.
添加模型会显示范围和准确度设置。
1. 选择范围或准确性作为目标，然后从相应的下拉菜单中选择一个值。Click **[!UICONTROL Save]** when done.

>[!MORE_ LIKE_ This]
>
>* [准确性和触及力](../../features/traits/trait-accuracy-reach.md)


## Configuration Settings for Algorithmic Traits {#configure-settings}

In [!UICONTROL Trait Builder], the [!UICONTROL Configuration] section lets you associate an algorithmic model to a trait. 要完成算法特征创建过程，请选择一个模型，然后选择范围或准确性目标。

### 先决条件

<!-- r_algo_trait_config_section.xml -->

* [创建算法模型](../../features/algorithmic-models/create-model.md#build-model)。
* 等待通知电子邮件，通知您模型数据运行已完成。
* Complete the required fields in the [Basic Information](../../features/traits/create-onboarded-rule-based-traits.md) section.

### 配置字段和设置

| 界面元素 | 说明 |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Click the **[!UICONTROL Update]** button to open the models window. 从窗口中选择要用于创建特征的算法模型。 |
| **[!UICONTROL Select Goal Accuracy]** | 选择此选项可根据准确度创建特征。准确性是一个计分值，用于指示潜在用户对基准的距离。准确度范围范围从0(至少精确到精确)到1(最精确)。 |
| **[!UICONTROL Reach and Accuracy Data Columns]** | 此部分在右侧显示多达21行数字数据，它们显示您的模型的准确性和触及值。 |
| **[!UICONTROL Reach and Accuracy Slider]** | 滑块位于图形底部，可让您为您的范围或准确性目标设置数值。您可以设置滑块，然后选择范围或准确度目标按钮以创建特征。 |

>[!MORE_ LIKE_ This]
>
>* [准确性和触及力](../../features/traits/trait-accuracy-reach.md)