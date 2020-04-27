---
description: 预测受众可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: 预测受众可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-title: 管理预测受众
solution: Audience Manager
title: 受众经理预测受众
translation-type: tm+mt
source-git-commit: 8259f07c91efa0efd88e8f7c87cb1829ffadd77d

---


# 预测受众入门 {#predictive-audiences-getting-started}

>[!IMPORTANT]
>本文包含用于指导您完成此功能的设置和使用的产品文档。 此处包含的任何内容都不是法律建议。 请咨询您自己的法律顾问以获得法律指导。

## 创建预测受众模型 {#create-predictive-audiences}

在创建模 [!UICONTROL Predictive Audiences] 型之前，您需要确定要将特征和区段分配给哪个第 [!UICONTROL Predictive Audiences] 一方数据源。 您可以使用现有的第一方数据源，或创建新数据源。 有关 [如何创建新的第一方数据源的详细信息](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) ，请参阅管理数据源。

一旦知道要使用哪个数据源，请按照以下步骤操作。

1. 转到 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**。
1. 在部分 [!UICONTROL Predictive Audiences] 中，单击 **[!UICONTROL Add New]**。

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. 接下来，定义要按受众分类的角色。 您可以通过选择特征或区段来构建角色来实现此目的。 使用屏 [!UICONTROL Traits] 幕左上 [!UICONTROL Segments] 角的和选项卡在您的特征和区段目录之间切换。 确定要用作角色的特征或区段后，单击列中的相 **[!UICONTROL Add]** 应图 [!UICONTROL Action] 标。
   ![smart-persona-select-persona](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >您必须为基准角色选择至少两个特征或两个区段。 不能同时使用特征和区段。
1. 定 **[!UICONTROL Next]** 义角色后单击。
1. 接下来，通过为此受众选择第一方特征或段，选择要分类的第一方受众。 使用屏 [!UICONTROL Traits] 幕左上 [!UICONTROL Segments] 角的和选项卡在特征和区段目录之间切换。 选择要用作受众的第一方特征或段，以将其添加到模型。
   ![smart-persona-select-受众](assets/predictive-audiences-audience.png)
1. 选 **[!UICONTROL Next]** 择受众后单击。
1. 填写模型详细信息：
   1. **[!UICONTROL Model Name]**:为模型输入描述性名称，这将帮助您稍后识别它。 由模型生成的区段名称将与模型名称开始。
   2. **[!UICONTROL Description]**:输入模型说明，以帮助您识别其用例。
   3. **[!UICONTROL Data Source]**:选择您希望将此模型中的区段分 [!UICONTROL Predictive Audiences] 配给的第一方数据源。
      ![预测受众-保存](assets/predictive-audiences-save.png)
1. 单击 **[!UICONTROL Save]**.

## 编辑预测受众 {#edit-predictive-audiences}

受众管理器不支持编辑现有模 [!UICONTROL Predictive Audiences] 型。 要更改模型的配置，必须创建新模型。 如果已达到10个模型的限 [!UICONTROL Predictive Audiences] 制，并且需要编辑其中一个模型，则必须删除一个模型并创建新模型。

## 删除预测受众 {#delete-predictive-audiences}

要删除模 [!UICONTROL Predictive Audiences] 型，请转到 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，找到要删除的模型，然后单击该图 **[!UICONTROL Delete]** 标。