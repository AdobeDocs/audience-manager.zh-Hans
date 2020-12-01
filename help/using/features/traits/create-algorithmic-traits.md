---
description: 描述算法特征创建过程特有的设置步骤和功能。
seo-description: 描述算法特征创建过程特有的设置步骤和功能。
seo-title: 创建算法特征
solution: Audience Manager
title: 创建算法特征
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 5%

---


# 创建算法特征 {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

要创建算法特征，请转至[!UICONTROL Traits]并按照以下步骤操作：

1. 单击&#x200B;**[!UICONTROL Create New Trait]**&#x200B;并从下拉菜单中选择&#x200B;**[!UICONTROL Algorithmic]**。
1. 在[基本信息](../../features/traits/create-onboarded-rule-based-traits.md)部分
   * 命名特征。
   * 选择数据源。
   * 选择存储文件夹。
1. 展开[!UICONTROL Configuration]窗格，然后单击&#x200B;**[!UICONTROL Browse All Models]**。
这将打开一个新窗口，通过该窗口可以选择要用于特征的模型。
1. 选择一个模型，然后单击&#x200B;**[!UICONTROL Add Selected Model to Trait]**。
添加模型会显示范围和准确性设置。
1. 选择范围或准确度作为目标，并从相应的下拉菜单中选择一个值。 完成后，单击&#x200B;**[!UICONTROL Save]**。

## 算法特征{#configure-settings}的配置设置

在[!UICONTROL Trait Builder]中，[!UICONTROL Configuration]部分允许您将算法模型与特征关联。 要完成算法特征创建过程，请选择一个模型并选择达到或准确的目标。

### 先决条件

<!-- r_algo_trait_config_section.xml -->

* [创建相似人群拓展模型](../../features/algorithmic-models/create-model.md).
* 等待通知电子邮件，它让您知道模型数据运行已完成。
* 填写[基本信息](../../features/traits/create-onboarded-rule-based-traits.md)部分中的必填字段。

### 配置字段和设置

| 接口元素 | 说明 |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | 单击&#x200B;**[!UICONTROL Update]**&#x200B;按钮以打开模型窗口。 在窗口中，选择要用于创建特征的算法模型。 |
| **[!UICONTROL Select Goal Accuracy]** | 选择此选项可创建基于准确度的特征。 准确性是一个已计分的值，它指示潜在用户与您的基线的距离。 精度刻度范围从0（最不精确）到1（最精确）。 |
| **[!UICONTROL Reach and Accuracy Data Columns]** | 此部分位于右侧，最多显示21行数字数据，这些数据显示模型的准确度和范围值。 |
| **[!UICONTROL Reach and Accuracy Slider]** | 位于图形底部的滑块允许您为达到或准确目标设置数值。 您可以设置滑块，然后选择达到或准确目标按钮以创建特征。 |

>[!MORELIKETHIS]
>
>* [精度和范围](../../features/traits/trait-accuracy-reach.md)

