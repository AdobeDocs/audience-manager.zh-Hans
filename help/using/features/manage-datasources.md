---
description: 要创建新数据源，请转到受众数据>数据源>新增，并完成此处介绍的每个部分的步骤。 创建数据源需要管理员权限。
keywords: 数据源；管理数据源；audience manager数据源
seo-description: 要创建新数据源，请转到受众数据>数据源>新增，并完成此处介绍的每个部分的步骤。 创建数据源需要管理员权限。
seo-title: 创建数据源
solution: Audience Manager
title: 管理数据源
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: 数据源
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 3%

---

# 跨渠道和解决方案一致地管理 [!UICONTROL Data Sources] {#manage-data-sources}

## 创建一个 [!UICONTROL Data Source] {#create-data-source}

要创建新的[!UICONTROL data source]，请转到&#x200B;**[!UICONTROL Audience Data > Data Sources > Add New]**&#x200B;并完成此处介绍的每个部分的步骤。 创建[!UICONTROL data source]需要管理员权限。

<!-- create-datasource.xml -->

>[!TIP]
>
>有关这些不同控件的说明，请参阅[数据源设置和菜单选项](../features/datasources-list-and-settings.md#settings-menu-options)。

## [!UICONTROL Data Source] 详细信息 {#details}

要完成[!UICONTROL Data Source Details]部分，请执行以下操作：

1. 命名[!UICONTROL data source]。
1. *（可选）* 描述 [!UICONTROL data source]。简要描述可帮助您定义[!UICONTROL data source]的角色或用途。
1. 提供[!UICONTROL integration code]。 通常，[!UICONTROL integration codes]是可选的。 当您想要执行以下操作时，需要使用这些参数：

   * [创建跨设备数据源](../features/profile-merge-rules/merge-rules-start.md#create-data-source)。
   * 使用[Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)。
   * 使用[配置文件合并规则](../features/profile-merge-rules/merge-rules-start.md)。

1. 选择&#x200B;**[!UICONTROL ID Type]**。 [!UICONTROL ID Type] 选项包括：

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (创建时需要使 [!UICONTROL Profile Merge Rule]用)。请注意，对于某些客户，此选项会公开&#x200B;**[!UICONTROL ID Definition]**&#x200B;选项。

1. 选择&#x200B;**[!UICONTROL ID Definition]**&#x200B;选项。 选项包括：

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[数据导出](../features/data-export-controls.md) 控制器是可选的分类规则，您可以将其应用 [!UICONTROL data source] 到和 [!UICONTROL destination]。当[!UICONTROL destination]操作违反数据隐私或使用协议时，它们会阻止您向该操作发送数据。 如果不使用[!UICONTROL Data Export Controls]，请跳过此部分。

## [!UICONTROL Data Source] 设置 {#settings}

这些设置决定了识别、使用和共享[!UICONTROL data source]的方式。 您还可以为入站数据文件启用错误报告。 要完成[!UICONTROL Data Source Settings]部分，请执行以下操作：

1. 选中[!UICONTROL Data Source Setting]复选框，以将选项应用于[!UICONTROL data source]。
2. 单击 **[!UICONTROL Save]**.

## 删除数据源 {#delete-data-source}

<!-- t_datasource_delete.xml -->

删除不再需要的[!UICONTROL data source]。

>[!NOTE]
>
>请注意以下限制：
>
>* 无法删除[活动受众或数据源同步特征](../features/traits/client-activity-synced-audience-traits.md)。
>* 对于使用Adobe Analytics的客户：Audience Manager不允许您删除从[!DNL Analytics]报表包中自动创建的数据源。 使用[核心服务](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html)取消映射这些数据源。


1. 单击 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. 选中一个或多个数据源旁边的复选框。
如果列表较长，可使用[!UICONTROL Search]框找到所需的数据源。
1. 单击![](assets/icon_trash.png)，然后确认删除。


>[!MORELIKETHIS]
>
>* [数据源设置和菜单选项](../features/datasources-list-and-settings.md#settings-menu-options)

