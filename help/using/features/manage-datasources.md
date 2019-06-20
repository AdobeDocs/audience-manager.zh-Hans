---
description: 要创建新的数据源，请转到“受众数据”>“数据源”>“添加新内容”，然后完成此处描述的每个部分的步骤。需要管理员权限才能创建数据源。
keywords: cdf；自定义数据源
seo-description: 要创建新的数据源，请转到“受众数据”>“数据源”>“添加新内容”，然后完成此处描述的每个部分的步骤。需要管理员权限才能创建数据源。
seo-title: 创建数据源
solution: Audience Manager
title: 创建数据源
uuid: 4df65bcb-9ad9-4b72b72e-8918b43d4850
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

To create a new data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. 需要管理员权限才能创建数据源。

<!-- create-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. 命名数据源。
1. *(可选)* 描述数据源。简明的描述可帮助您定义数据源的角色或目的。
1. 提供集成代码。通常，集成代码是可选的。当您希望：

   * [创建跨设备数据源](../features/profile-merge-rules/merge-rules-start.md#create-data-source)。
   * Use the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
   * Work with [Profile Merge Rules](../features/profile-merge-rules/merge-rules-start.md).

1. Choose an **[!UICONTROL ID Type]**. ID类型选项包括：

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (创建) [!UICONTROL Profile Merge Rule]。Note, for some customers, this selection exposes the **[!UICONTROL ID Definition]** options.

1. Choose an **[!UICONTROL ID Definition]** option. 选项包括：

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## 数据导出控制 {#export-controls}

[数据导出控件](../features/data-export-controls.md) 是可选的分类规则，您可以应用于数据源和目标。当该操作违反了数据隐私或使用协议时，它们会阻止您向目标发送数据。Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

这些设置决定了如何识别、使用和共享数据源。还可以为入站数据文件启用错误报告。To complete the [!UICONTROL Data Source Settings] section:

1. Select a [!UICONTROL Data Source Setting] check box to apply an option to your data source.
2. 单击 **[!UICONTROL Save]**.

>[!MORE_ LIKE_ This]
>
>* [数据源设置和菜单选项](../features/datasources-list-and-settings.md#settings-menu-options)


## Delete a Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

删除不再需要的数据源。

>[!NOTE]
>
>请注意以下限制：
>
>* You cannot delete an [Active Audience or Data Source Synced Trait](../features/traits/client-activity-synced-audience-traits.md).
>* For customers using Adobe Analytics: Audience Manager does not allow you to delete data sources created automatically from your [!DNL Analytics] report suites. Use the [Core Service](https://marketing.adobe.com/resources/help/en_US/mcloud/) to unmap these data sources.


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. 选中一个或多个数据源旁边的复选框。
You can use the [!UICONTROL Search] box to locate the desired data sources if you have a long list.
1. Click  ![](assets/icon_trash.png), then confirm the deletion.