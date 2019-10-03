---
description: 描述在Model Builder中创建算法模型的必需和可选步骤。
keywords: algo how work
seo-description: 描述在Model Builder中创建算法模型的必需和可选步骤。
seo-title: 创建算法模型
solution: Audience Manager
title: 创建算法模型
topic: DIL API
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# 创建算法模型 {#create-an-algorithmic-model}

介绍在中创建算法模型所需的和可选的步骤 [!UICONTROL Model Builder]。

## 构建模型 {#build-model}

<!-- t_model_build.xml -->

### Model Builder部分

[!UICONTROL Model Builder] 由部分和 [!UICONTROL Basic Information] 部分组 [!UICONTROL Configuration] 成。 要创建模型，请完成这两个部分中的必填字段。 保存模型以启动算法。 [!DNL Audience Manager] 在第一次数据运行完成后，向您发送自动通知。 收到电子邮件后，您可以转到 [Trait Builder](../../features/traits/about-trait-builder.md) ，创建算法特征。

>[!NOTE]
>
>* 如果您创建了模型，但不使用该模型构建任何特征，则建模过程只运行一次。
>* 从包含大量信息的数据源构建模型。 数据不足的模型将运行，但不会返回结果。
>* *不要使用* 其他算法特征或细分创建模型。
>* 自动电子邮件通知仅发送一次（在第一次数据运行后）。


### 构建模型

要构建模型，请转到该部分， [!UICONTROL Models] 单击并 **[!UICONTROL Add New]** 按照以下步骤操作：

1. 在“基 [本信息](../../features/algorithmic-models/create-model.md#basic-information) ”部分
   * Name the model.
   * *(Optional) Provide a brief description about the model.*
   * 将模型的状态设置为 **[!UICONTROL Active]** 或 **[!UICONTROL Inactive]**。 不活动的模型将不运行，也不会生成任何数据。
1. 在“配 [置](../../features/algorithmic-models/create-model.md#configuration) ”部分：
   * 单 **[!UICONTROL Browse All Traits]** 击或 **[!UICONTROL Browse All Segments]** 以选择要建模的特征或区段。 选择已载入的特征、基于规则的特征或段作为基线。 Otherwise, your models will not run.
   * Choose a 30, 60, or 90 day look-back period. 这为模型设置时间范围。
   * The [!UICONTROL TraitWeight] algorithm is selected by default.
   * Select a data source from the [!UICONTROL Available Data] list.
   * Click **[!UICONTROL Save]** when done.

## Basic Information for Algorithmic Models {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder], the [!UICONTROL Basic Information] settings let you create new or edit existing models. 要创建新模型，请提供名称并转到设 [!UICONTROL Configuration] 置。 The description field is optional.

| 字段 | 描述 |
|---|---|
| **[!UICONTROL Name]** | Give your model a short, logical name that describes its function or purpose. Avoid abbreviations, special characters, and accent marks. |
| **[!UICONTROL Description]** | A field for additional descriptive information about the model. |
| **[!UICONTROL Status]** | Activates or deactivates the model (active by default). |

## 配置 {#configuration}

在中 [!UICONTROL Model Builder]，该部 [!UICONTROL Configuration] 分允许您向模型添加特征或区段。 In this section, select a baseline trait or segment, a look-back period, and data from your first and third-party data sources.

<!-- r_model_configuration.xml -->

### 先决条件

Complete the required fields in the  section first.[!UICONTROL Basic Information]

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
   <td colname="col2"> <p>单击特征或区段按钮可查看所有特征或区段的列表。 所选段或特征将成为系统算法用于建模的基线。 </p> <p> <p><b>注意</b>: 选择已载入的特征、基于规则的特征或段作为基线。 否则，您的型号将不运行。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>选择回顾期(2)</b> </p> </td> 
   <td colname="col2"> <p>设置模型的时间范围。 根据您的选择，该算法包括并评估前30、60或90天的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>选择算法(3)</b> </p> </td> 
   <td colname="col2"> <p>此时，Model builder仅与我们专有的“特征权重” <span class="keyword"> 算法配合</span> 。 <span class="keyword"> Audience Manager可能会在后续版本中添加其他算法功能。</span> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>从数据源中选择模型数据(4)</b> </p> </td> 
   <td colname="col2"> <p>允许您选择要在模型中使用的第一方和第三方数据源。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusions (5)</b> </p> </td> 
   <td colname="col2"> <p>您可以从为建模选择的数据源中排除特征。 使用“ <span class="wintitle"> 排除</span> ”列表并阅读“算法 <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> 模型：特征排除</a> ，了解更多信息。 </p> </td>
  </tr> 
 </tbody>
</table>

观看以下视频，了解如何创建第一方相似模型，以便您能够找到更多与您的客户相似的访客。

>[!VIDEO](https://video.tv.adobe.com/v/23504/?captions=chi_hans)

>[!MORE_LIKE_THIS]
>
>* [了解TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

