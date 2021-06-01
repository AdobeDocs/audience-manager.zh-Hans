---
description: 描述如何设置算法特征创建过程特有的步骤和功能。
seo-description: 描述如何设置算法特征创建过程特有的步骤和功能。
seo-title: 创建算法特征
solution: Audience Manager
title: 创建算法特征
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: 特征
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 5%

---

# 创建算法特征 {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

要创建算法特征，请转到[!UICONTROL Traits]并执行以下步骤：

1. 单击&#x200B;**[!UICONTROL Create New Trait]**&#x200B;并从下拉菜单中选择&#x200B;**[!UICONTROL Algorithmic]**。
1. 在[基本信息](../../features/traits/create-onboarded-rule-based-traits.md)部分中
   * 命名特征。
   * 选择数据源。
   * 选择存储文件夹。
1. 展开[!UICONTROL Configuration]窗格并单击&#x200B;**[!UICONTROL Browse All Models]**。
此时将打开一个新窗口，用于选择要用于特征的模型。
1. 选择模型并单击&#x200B;**[!UICONTROL Add Selected Model to Trait]**。
添加模型会公开访问范围和准确度设置。
1. 选择范围或准确度作为您的目标，然后从相应的下拉菜单中选择一个值。 完成后，单击&#x200B;**[!UICONTROL Save]**。

## 算法特征{#configure-settings}的配置设置

在[!UICONTROL Trait Builder]中，通过[!UICONTROL Configuration]部分，可将算法模型与特征关联。 要完成算法特征创建过程，请选择一个模型并选择达到或准确性目标。

### 先决条件

<!-- r_algo_trait_config_section.xml -->

* [创建相似人群拓展模型](../../features/algorithmic-models/create-model.md).
* 等待通知电子邮件，以告知您模型数据运行已完成。
* 填写[基本信息](../../features/traits/create-onboarded-rule-based-traits.md)部分中的必填字段。

### 配置字段和设置

| 界面元素 | 说明 |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | 单击&#x200B;**[!UICONTROL Update]**&#x200B;按钮以打开模型窗口。 从窗口中，选择要用于创建特征的算法模型。 |
| **[!UICONTROL Select Goal Accuracy]** | 选择此选项可根据准确度创建特征。 准确度是一个打分值，指示潜在用户与基线的接近度。 精度刻度范围从0（最不精确）到1（最精确）。 |
| **[!UICONTROL Reach and Accuracy Data Columns]** | 此部分在右侧显示多达21行数字数据，这些数据显示模型的准确性和范围值。 |
| **[!UICONTROL Reach and Accuracy Slider]** | 滑块位于图表底部，允许您为访问或准确度目标设置数值。 您可以设置滑块，然后选择达到或准确度目标按钮以创建特征。 |

>[!MORELIKETHIS]
>
>* [精度和范围](../../features/traits/trait-accuracy-reach.md)

