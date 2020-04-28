---
description: 描述在Model Builder中创建算法模型的必需和可选步骤。
keywords: algo how works
seo-description: 描述在Model Builder中创建算法模型的必需和可选步骤。
seo-title: 创建算法模型
solution: Audience Manager
title: 创建算法模型
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
translation-type: tm+mt
source-git-commit: af43becaf841909174fad097f4d4d5040c279b47

---


# 创建相似模型 {#create-an-algorithmic-model}

介绍创建应用程序所需的步骤和可选步骤 [!UICONTROL Look-Alike Model]。

## Model Builder部分

[!UICONTROL Model Builder] 由部分和 [!UICONTROL Basic Information] 部分组 [!UICONTROL Configuration] 成。 要创建模型，请完成这两个部分中的必填字段。 保存模型以开始算法。 [!DNL Audience Manager] 在第一次数据运行完成后，向您发送自动通知。 收到电子邮件后，您可以转到 [Trait Builder](../../features/traits/about-trait-builder.md) ，创建算法特征。

>[!NOTE]
>
>* 如果您创建了模型，但不使用该模型构建任何特征，则建模过程只运行一次。
>* 从包含大量信息的数据源构建模型。 数据不足的模型将运行，但不会返回结果。
>* *请勿使用* 其他算法特征或细分创建模型。
>* 自动电子邮件通知仅发送一次（在第一次数据运行后）。


## 构建模型

请按照以下步骤构建 [!UICONTROL Look-Alike Model]:

1. 转到 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** 并单 **[!UICONTROL Add New]** 击部 [!UICONTROL Look-Alike Modeling] 分。
   ![look-alike-add](assets/look-alike-add.png)
2. 在“基 [本信息](../../features/algorithmic-models/create-model.md#basic-information) ”部分
   * 命名模型。
   * *（可选）* ，提供有关模型的简要说明。
   * 将模型的状态设置为 **[!UICONTROL Active]** 或 **[!UICONTROL Inactive]**。 不活动的模型将不运行，也不会生成任何数据。
      ![look-alike-basic](assets/look-alike-basic.png)
3. 在“配 [置](../../features/algorithmic-models/create-model.md#configuration) ”部分：
   * 单 **[!UICONTROL Browse All Traits]** 击或 **[!UICONTROL Browse All Segments]** 以选择要建模的特征或区段。 选择已载入的特征、基于规则的特征或段作为基线。 否则，您的型号将不运行。
   * 选择30天、60天或90天回顾期。 这为模型设置时间范围。
   * 默认 [!UICONTROL TraitWeight] 情况下选择算法。
   * 从列表中选择数据源。 [!UICONTROL Available Data]
   * 完成 **[!UICONTROL Save]** 后单击。
      ![look-alike-configuration](assets/look-alike-configuration.png)

## 算法模型的基本信息 {#basic-information}

<!-- r_model_basic.xml -->

在中， [!UICONTROL Model Builder]通过 [!UICONTROL Basic Information] 这些设置可以创建新模型或编辑现有模型。 要创建新模型，请提供名称并转到设 [!UICONTROL Configuration] 置。 描述字段为可选字段。

| 字段 | 描述 |
|---|---|
| **[!UICONTROL Name]** | 为模型提供一个描述其功能或用途的简短逻辑名称。 避免缩写、特殊字符和重音标记。 |
| **[!UICONTROL Description]** | 有关模型的其他描述性信息的字段。 |
| **[!UICONTROL Status]** | 激活或取消激活模型（默认情况下处于活动状态）。 |

## 配置 {#configuration}

在中 [!UICONTROL Model Builder]，该部 [!UICONTROL Configuration] 分允许您向模型添加特征或区段。 在本节中，选择基线特征或区段、回顾期以及来自第一方和第三方数据源的数据。

<!-- r_model_configuration.xml -->

### 先决条件

首先填写部分中的 [!UICONTROL Basic Information] 必填字段。

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
   <td colname="col2"> <p>此时，Model Builder仅与我们专有的特征权重算 <span class="keyword"> 法配合使用</span> 。 <span class="keyword"> 受众管理器</span> ，可在后续发行版中添加其他算法函数。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>从数据源中选择模型数据(4)</b> </p> </td> 
   <td colname="col2"> <p>允许您选择要在模型中使用的第一方和第三方数据源。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>排除(5)</b> </p> </td> 
   <td colname="col2"> <p>您可以从为建模选择的数据源中排除特征。 使用“排 <span class="wintitle"> 除”列表</span> ，并阅读“算 <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> 法模型：特征排除</a> ，了解更多信息。 </p> </td>
  </tr> 
 </tbody>
</table>

观看以下视频，了解如何创建第一方相似模型，以便您能够找到更多与转换器相似的访客。

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [了解TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

