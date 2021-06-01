---
description: 介绍在模型生成器中创建算法模型的必需和可选步骤。
keywords: algo how工作
seo-description: 介绍在模型生成器中创建算法模型的必需和可选步骤。
seo-title: 创建算法模型
solution: Audience Manager
title: 创建算法模型
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: 算法模型
exl-id: 8b7c4f57-f2c8-46f1-8924-5513fd6ede04
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---

# 创建相似人群拓展模型 {#create-an-algorithmic-model}

描述用于创建[!UICONTROL Look-Alike Model]的必需和可选步骤。

## 模型生成器部分

[!UICONTROL Model Builder] 包含和 [!UICONTROL Basic Information] 部 [!UICONTROL Configuration] 分。要创建模型，请填写这两个部分中的必填字段。 保存模型以启动算法。 [!DNL Audience Manager] 首次数据运行完成后，会向您发送自动通知。收到电子邮件后，您可以转到[特征生成器](../../features/traits/about-trait-builder.md)并创建算法特征。

>[!NOTE]
>
>* 如果您创建了模型，但没有使用该模型构建任何特征，则建模过程只运行一次。
>* 从包含大量有意义信息的数据源构建模型。 将运行数据不足的模型，但它们不会返回结果。
>* *请勿使* 用其他算法特征或区段创建模型。
>* 自动电子邮件通知仅发送一次（在首次运行数据后）。


## 构建模型

按照以下步骤构建[!UICONTROL Look-Alike Model]:

1. 转到&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，然后单击[!UICONTROL Look-Alike Modeling]部分中的&#x200B;**[!UICONTROL Add New]**。
   ![look-alkie-add](assets/look-alike-add.png)
1. 在[基本信息](../../features/algorithmic-models/create-model.md#basic-information)部分中
   * 命名模型。
   * *（可选）* 提供有关模型的简要描述。
   * 将模型的状态设置为&#x200B;**[!UICONTROL Active]**&#x200B;或&#x200B;**[!UICONTROL Inactive]**。 不活动的模型将不会运行，也不会生成任何数据。
      ![相似人群拓展 — 基本](assets/look-alike-basic.png)
1. 在[Configuration](../../features/algorithmic-models/create-model.md#configuration)部分中：
   * 单击&#x200B;**[!UICONTROL Browse All Traits]**&#x200B;或&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;以选择要针对其建模的特征或区段。 按名称、ID、描述或数据源搜索特征。 搜索时单击文件夹可将结果限制为该文件夹及其子文件夹。 您还可以按特征类型（[!UICONTROL Folder Trait]、[!UICONTROL Rule-based]、[!UICONTROL Onboarded]和[!UICONTROL Algorithmic]）或群体类型（[设备ID](../../reference/ids-in-aam.md)和[跨设备ID](../../reference/ids-in-aam.md)）筛选特征。
      ![浏览特征](assets/browse-traits.png)
   * 选择30、60或90天的回顾期。 这为模型设置一个时间范围。
   * 默认情况下，会选择[!UICONTROL TraitWeight]算法。
   * 从[!UICONTROL Available Data]列表中选择数据源。
   * 完成后，单击&#x200B;**[!UICONTROL Save]**。
      ![相似人群拓展配置](assets/look-alike-configuration.png)

请观看以下视频，详细了解跨设备量度的工作方式。

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## 算法模型{#basic-information}的基本信息

<!-- r_model_basic.xml -->

在[!UICONTROL Model Builder]中，通过[!UICONTROL Basic Information]设置，您可以创建新模型或编辑现有模型。 要创建新模型，请提供名称并转到[!UICONTROL Configuration]设置。 描述字段为可选字段。

| 字段 | 描述 |
|---|---|
| **[!UICONTROL Name]** | 为模型提供一个描述其功能或用途的简短逻辑名称。 避免缩写、特殊字符和重音符号。 |
| **[!UICONTROL Description]** | 有关模型的其他描述性信息的字段。 |
| **[!UICONTROL Status]** | 激活或停用模型（默认情况下处于活动状态）。 |

## 配置 {#configuration}

在[!UICONTROL Model Builder]中，通过[!UICONTROL Configuration]部分可向模型添加特征或区段。 在此部分中，选择基线特征或区段、回顾期以及来自第一方和第三方数据源的数据。

<!-- r_model_configuration.xml -->

### 先决条件

首先填写[!UICONTROL Basic Information]部分中的必填字段。

![](assets/lam_exclude_traits_numbered.png)

<table id="table_7A6BE5E5498D4776A30323B743954150"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>选择基线特征或区段(1)</b> </p> </td> 
   <td colname="col2"> <p>单击特征或区段按钮可查看所有特征或区段的列表。 所选区段或特征将成为系统算法用于建模的基线。 </p> <p> <p><b>注意</b>:选择已载入的特征、基于规则的特征或区段作为基线。否则，您的模型将不运行。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>选择回顾时段(2)</b> </p> </td> 
   <td colname="col2"> <p>设置模型的时间范围。 算法会根据您的选择，包含并评估前30、60或90天的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>选择算法(3)</b> </p> </td> 
   <td colname="col2"> <p>目前，模型生成器仅适用于我们专有的<span class="keyword">特征权重</span>算法。 <span class="keyword"> Audience Manager可</span> 以在后续版本中添加其他算法函数。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>从数据源中选择模型数据(4)</b> </p> </td> 
   <td colname="col2"> <p>允许您选择要在模型中使用的第一方和第三方数据源。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>排除项(5)</b> </p> </td> 
   <td colname="col2"> <p>您可以从为建模选择的数据源中排除特征。 使用<span class="wintitle">排除项</span>列表并阅读<a href="../../features/algorithmic-models/trait-exclusion-algo-models.md">算法模型：特征排除</a>以了解更多信息。 </p> </td>
  </tr> 
 </tbody>
</table>

请观看以下视频，了解如何创建第一方相似人群拓展模型，以便您能够找到更多自己的类似于转换器的访客。

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [了解TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

