---
description: 要创建新数据源，请转到“受众数据”>“数据源”>“添加新”，然后完成此处描述的每个部分的步骤。 创建数据源需要管理员权限。
keywords: data sources;manage data source;audience manager data source
seo-description: 要创建新数据源，请转到“受众数据”>“数据源”>“添加新”，然后完成此处描述的每个部分的步骤。 创建数据源需要管理员权限。
seo-title: 创建数据源
solution: Audience Manager
title: 管理数据源
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

要创建新数据源，请转到并完 **[!UICONTROL Audience Data > Data Sources > Add New]** 成此处介绍的每个部分的步骤。 创建数据源需要管理员权限。

<!-- create-datasource.xml -->

>[!TIP]
>
>有关 [这些不同控件的说明，请参阅数据源设置和菜单选项](../features/datasources-list-and-settings.md#settings-menu-options) 。

## 数据源详细信息 {#details}

要完成此部 [!UICONTROL Data Source Details] 分，请执行以下操作：

1. 命名数据源。
1. *（可选）* ，描述数据源。 简明的描述可帮助您定义数据源的角色或用途。
1. 提供集成代码。 通常，集成代码是可选的。 您需要满足以下条件时，才需要这些条件：

   * [创建跨设备数据源](../features/profile-merge-rules/merge-rules-start.md#create-data-source)。
   * 使用 [Adobe Experience Platform Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/)。
   * 使用配置 [文件合并规则](../features/profile-merge-rules/merge-rules-start.md)。

1. 选择 **[!UICONTROL ID Type]**。 ID类型选项包括：

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (创建时需要 [!UICONTROL Profile Merge Rule])。 请注意，对于某些客户，此选项会显示 **[!UICONTROL ID Definition]** 选项。

1. Choose an **[!UICONTROL ID Definition]** option. 选项包括：

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## 数据导出控制 {#export-controls}

[数据导出控件](../features/data-export-controls.md) (Data Export Controls)是可应用于数据源和目标的可选分类规则。 当该操作违反数据隐私或使用协议时，它们会阻止您将数据发送到目标。 如果不使用，请跳过此部分 [!UICONTROL Data Export Controls]。

## Data Source Settings {#settings}

这些设置决定了如何识别、使用和共享数据源。 您还可以为入站数据文件启用错误报告。 要完成此部 [!UICONTROL Data Source Settings] 分，请执行以下操作：

1. 选中一 [!UICONTROL Data Source Setting] 个复选框，将选项应用于数据源。
2. 单击 **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [数据源设置和菜单选项](../features/datasources-list-and-settings.md#settings-menu-options)


## 删除数据源 {#delete-data-source}

<!-- t_datasource_delete.xml -->

删除不再需要的数据源。

>[!NOTE]
>
>请注意以下限制：
>
>* 无法删除活动 [受众或数据源已同步的特征](../features/traits/client-activity-synced-audience-traits.md)。
>* 对于使用Adobe Analytics的客户：Audience Manager不允许您删除从报表包自动创建的数 [!DNL Analytics] 据源。 使用核 [心服务](https://marketing.adobe.com/resources/help/en_US/mcloud/) ，取消映射这些数据源。


1. 单击 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. 选中一个或多个数据源旁边的复选框。
如果您有 [!UICONTROL Search] 长列表，则可以使用该框来查找所需的数据源。
1. 单击 ![](assets/icon_trash.png)，然后确认删除。