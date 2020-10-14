---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-title: 管理预测受众
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 48bf17a2899fd06c525ba6b4fddb9ec805efb5c3
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 7%

---


# 开始使用 Predictive Audiences {#predictive-audiences-getting-started}

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

## 创建预测受众模型 {#create-predictive-audiences}

在创建模 [!UICONTROL Predictive Audiences] 型之前，您需要确定要将特征和区段分配给哪个第 [!UICONTROL Predictive Audiences] 一方数据源。 您可以使用现有的第一方数据源，也可以创建新数据源。 有关 [如何创建新](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) 的第一方数据源的详细信息，请参阅管理数据源。

一旦知道要使用哪个数据源，请按照以下步骤操作。

1. 转到 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**。
1. 在部分 [!UICONTROL Predictive Audiences] 中，单击 **[!UICONTROL Add New]**。

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. 接下来，定义要按受众分类的角色。 您可以通过选择特征或细分来构建角色， 使用屏 [!UICONTROL Traits] 幕左 [!UICONTROL Segments] 上角的和选项卡在您的特征和区段目录之间切换。 确定要用作角色的特征或区段后，单击列中的 **[!UICONTROL Add]** 相应图 [!UICONTROL Action] 标。
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >您必须为基准角色选择至少两个特征或两个区段。 不能同时使用特征和区段。
1. 定 **[!UICONTROL Next]** 义角色后单击。
1. 接下来，通过为此受众选择第一方特征或段，选择要分类的第一方受众。 使用屏 [!UICONTROL Traits] 幕左 [!UICONTROL Segments] 上角的和选项卡在特征和区段目录之间切换。 选择要用作受众的第一方特征或段，以将其添加到模型。
   ![smart-persona-select-受众](assets/predictive-audiences-audience.png)
1. 选 **[!UICONTROL Next]** 择受众后单击。
1. 填写模型详细信息：
   * **[!UICONTROL Model Name]**:为模型输入描述性名称，以帮助您稍后识别它。 由模型生成的段名称将与模型名称开始。
   * **[!UICONTROL Description]**:输入有助于识别其用例的模型描述。
   * **[!UICONTROL Data Source]**:选择您希望将此模型中的区段分 [!UICONTROL Predictive Audiences] 配给的第一方数据源。
   * **[!UICONTROL Profile Merge Rule]**:为此模 [!UICONTROL Profile Merge Rule] 型创建的所有预测 [!UICONTROL segments] 值选择要分配的值。 如果您选择的目标 [!UICONTROL segment]受众为，我们建议选择与 [!UICONTROL Profile Merge Rule] 目标受众相同的。
      ![预测受众保存](assets/predictive-audiences-save.png)
1. 单击 **[!UICONTROL Save]**.

## 克隆和编辑预测受众模型 {#clone-predictive-audiences}

Audience Manager不支持编辑现有 [!UICONTROL Predictive Audiences] 模型。 要更改模型的配置，可创建现有模型的克隆并对其进行编辑。 您可以通过以下方式实现：

1. 转到 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**。
2. 单击要克隆 [!UICONTROL Predictive Audiences] 的模型的名称。
3. 单击 **[!UICONTROL Clone]** 屏幕左上角的按钮。
   ![预测受众克隆](assets/predictive-audiences-clone.png)
4. 克隆模型后，您将转到克隆 [!DNL Save & Configure] 模型的页面。 在此页中，可以更改模 [!UICONTROL data source] 型的分配[!UICONTROL Profile Merge Rule] 和分配值。 要编辑克隆模型的角色和目标受众，请使 [!UICONTROL Back] 用和 [!UICONTROL Next] 按钮在三个选项卡之间导航，或单击三个选项卡名称

   ![预测受众-克隆导航](assets/predictive-audiences-clone-navigate.png)

5. 编辑完模型后，单击 **[!UICONTROL Save]**。

## 删除预测受众 {#delete-predictive-audiences}

要删除模 [!UICONTROL Predictive Audiences] 型，请转 **[!UICONTROL Audience Data]** 到> **[!UICONTROL Models]**，找到要删除的模型，然后单击该 **[!UICONTROL Delete]** 图标。
