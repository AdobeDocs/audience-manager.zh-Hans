---
description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-description: Predictive Audiences 可以帮助您使用数据科学将未知受众实时分类为不同的角色。
seo-title: 管理预测受众
solution: Audience Manager
title: 开始使用 Predictive Audiences
feature: 算法模型
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 7%

---

# 开始使用 Predictive Audiences {#predictive-audiences-getting-started}

>[!IMPORTANT]
>本文包含旨在指导您完成此功能的设置和使用的产品文档。 这里没有任何法律建议。 请咨询您自己的法律顾问以获得法律指导。

## 创建预测受众模型 {#create-predictive-audiences}

在创建[!UICONTROL Predictive Audiences]模型之前，您需要确定要将[!UICONTROL Predictive Audiences]特征和区段分配给哪个第一方数据源。 您可以使用现有的第一方数据源，也可以创建一个新数据源。 有关如何创建新的第一方数据源的详细信息，请参阅[管理数据源](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html)。

知道要使用哪个数据源后，请执行以下步骤。

1. 转到&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**。
1. 在[!UICONTROL Predictive Audiences]部分中，单击&#x200B;**[!UICONTROL Add New]**。

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. 接下来，定义要按受众分类的角色。 为此，您可以选择特征或区段，以从中构建角色。 使用屏幕左上角的[!UICONTROL Traits]和[!UICONTROL Segments]选项卡，在特征和区段目录之间进行切换。 确定要用作角色的特征或区段后，单击[!UICONTROL Action]列中相应的&#x200B;**[!UICONTROL Add]**图标。
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >必须为基线角色至少选择两个特征或两个区段。 不能同时使用特征和区段的组合。
1. 定义角色后，单击&#x200B;**[!UICONTROL Next]**。
1. 接下来，通过为此受众选择第一方特征或区段，选择要进行分类的第一方受众。 使用屏幕左上角的[!UICONTROL Traits]和[!UICONTROL Segments]选项卡，在特征和区段目录之间进行切换。 选择要用作受众的第一方特征或区段，以将其添加到模型中。
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. 选择受众后，单击&#x200B;**[!UICONTROL Next]**。
1. 填写模型详细信息：
   * **[!UICONTROL Model Name]**:为模型输入描述性名称，以便稍后进行识别。由模型生成的区段名称将以模型名称开头。
   * **[!UICONTROL Description]**:输入有助于识别其用例的模型描述。
   * **[!UICONTROL Data Source]**:选择您希望将此模型中的区 [!UICONTROL Predictive Audiences] 段分配到的第一方数据源。
   * **[!UICONTROL Profile Merge Rule]**:为此模 [!UICONTROL Profile Merge Rule] 型创建的所有预测 [!UICONTROL segments] 选择要分配的。如果您选择的目标受众是[!UICONTROL segment]，我们建议选择目标受众的相同[!UICONTROL Profile Merge Rule]。
      ![predictive-audiences-save](assets/predictive-audiences-save.png)
1. 单击 **[!UICONTROL Save]**.

## 克隆和编辑预测受众模型 {#clone-predictive-audiences}

Audience Manager不支持编辑现有[!UICONTROL Predictive Audiences]模型。 要更改模型的配置，可以创建现有模型的克隆并对其进行编辑。 以下是您如何执行此操作：

1. 转到&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**。
2. 单击要克隆的[!UICONTROL Predictive Audiences]型号的名称。
3. 单击屏幕左上角的&#x200B;**[!UICONTROL Clone]**按钮。
   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)
4. 克隆模型后，将转到克隆模型的[!DNL Save & Configure]页面。 在此页中，您可以更改模型的[!UICONTROL data source]和分配的[!UICONTROL Profile Merge Rule]。 要编辑克隆模型的角色和目标受众，请使用[!UICONTROL Back]和[!UICONTROL Next]按钮在三个选项卡之间导航，或单击三个选项卡名称

   ![predictive-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. 编辑完模型后，单击&#x200B;**[!UICONTROL Save]**。

## 删除预测受众 {#delete-predictive-audiences}

要删除[!UICONTROL Predictive Audiences]模型，请转到&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，找到要删除的模型，然后单击&#x200B;**[!UICONTROL Delete]**&#x200B;图标。
