---
description: 介绍允许您在Model Builder中创建算法模型的必需和可选步骤。
keywords: algo如何工作
seo-description: 介绍允许您在Model Builder中创建算法模型的必需和可选步骤。
seo-title: 创建算法模型
solution: Audience Manager
title: 创建算法模型
topic: DIL API
uuid: cff4fc4e-cf92-445f-b2 d9-71c3 ca624 e26
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create an Algorithmic Model {#create-an-algorithmic-model}

Describes the required and optional steps that let you create an algorithmic model in [!UICONTROL Model Builder].

## Build a Model {#build-model}

<!-- t_model_build.xml -->

### Model Builder部分

[!UICONTROL Model Builder] 由 [!UICONTROL Basic Information] 和 [!UICONTROL Configuration] 部分组成。要创建模型，请完成这两个部分中的必填字段。保存模型以启动算法。[!DNL Audience Manager] 在第一个数据运行完成后向您发送一个自动通知。After you receive the email, you can go to [Trait Builder](../../features/traits/about-trait-builder.md) and create algorithmic traits.

>[!NOTE]
>
>* 在创建模型时，建模过程只运行一次，但不会创建任何特征。
>* 从包含有意义信息的数据源构建模型。数据不足的模型将运行，但不会返回结果。
>* *请勿* 使用其他算法特征或区段创建模型。
>* 自动电子邮件通知仅发送一次(在第一个数据运行之后)。


### 构建模型

To build a model, go to the [!UICONTROL Models] section and click **[!UICONTROL Add New]** and follow the steps below:

1. In the [Basic Information](../../features/algorithmic-models/create-model.md#basic-information) section
   * 命名模型。
   * *(可选)* 提供有关模型的简短说明。
   * Set the status for the model to **[!UICONTROL Active]** or **[!UICONTROL Inactive]**. 不活动的模型将不会运行，并且不会生成任何数据。
1. In the [Configuration](../../features/algorithmic-models/create-model.md#configuration) section:
   * Click **[!UICONTROL Browse All Traits]** or **[!UICONTROL Browse All Segments]** to select a trait or segment you want to model against. 选择一个载入的特征、一个基于规则的特征或一个区段作为基准。否则，您的模型将不会运行。
   * 选择30、60或90天回顾期。这将设置模型的时间范围。
   * [!UICONTROL TraitWeight] 默认情况下，此算法处于选中状态。
   * Select a data source from the [!UICONTROL Available Data] list.
   * Click **[!UICONTROL Save]** when done.

## Basic Information for Algorithmic Models {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder], the [!UICONTROL Basic Information] settings let you create new or edit existing models. To create a new model, provide a name and move on to the [!UICONTROL Configuration] settings. 描述字段为可选字段。

| 字段 | 描述 |
|---|---|
| **[!UICONTROL Name]** | 为您的模型提供一个简短的逻辑名称，用于描述其函数或目的。避免缩写、特殊字符和重音符号。 |
| **[!UICONTROL Description]** | 有关该模型的其他描述性信息的字段。 |
| **[!UICONTROL Status]** | 激活或取消激活模型(默认情况下处于活动状态)。 |

## 配置 {#configuration}

In [!UICONTROL Model Builder], the [!UICONTROL Configuration] section lets you add traits or segments to the model. 在此部分中，从您的第一方和第三方数据源中选择基准特征或区段、回顾期和数据。

<!-- r_model_configuration.xml -->

### 先决条件

Complete the required fields in the [!UICONTROL Basic Information] section first.

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
   <td colname="col2"> <p>单击特征或区段按钮可查看所有特征或区段的列表。选定的区段或特征将成为系统算法用于建模的基线。 </p> <p> <p><b>注意</b>：选择一个载入的特征、一个基于规则的特征或一个区段作为基准。否则，您的模型将不会运行。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>选择回顾期间(2)</b> </p> </td> 
   <td colname="col2"> <p>设置模型的时间范围。根据您的选择，算法包括并评估前30、60或90天的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>选择算法(3)</b> </p> </td> 
   <td colname="col2"> <p>At this time, Model Builder works with our proprietary <span class="keyword"> Trait Weight</span> algorithm only. <span class="keyword"> Audience Manager</span> 可能在后续发行版中添加其他算法函数。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>从数据源中选择模型数据(4)</b> </p> </td> 
   <td colname="col2"> <p>允许您选择要在模型中使用的第一方和第三方数据源。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusions(5)</b> </p> </td> 
   <td colname="col2"> <p>您可以排除您选择用于建模的数据源的特征。Use the <span class="wintitle"> Exclusions</span> list and read <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algorithmic Models: Trait Exclusion</a> to learn more. </p> </td>
  </tr> 
 </tbody>
</table>

>[!MORE_ LIKE_ This]
>
>* [了解Tritweight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

