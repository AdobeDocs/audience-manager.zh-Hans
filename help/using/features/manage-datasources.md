---
description: 要创建新数据源，请转到受众数据>数据源>添加新，然后完成此处描述的每个部分的步骤。 创建数据源需要管理员权限。
keywords: data sources;manage data source;audience manager data source
seo-description: 要创建新数据源，请转到受众数据>数据源>添加新，然后完成此处描述的每个部分的步骤。 创建数据源需要管理员权限。
seo-title: 创建数据源
solution: Audience Manager
title: 管理数据源
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: 0869e016d7f80710cb194449c48675b82fdfa865
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 5%

---


# 跨渠道和解决方案一致地管理 [!UICONTROL Data Sources] {#manage-data-sources}

## 创建一个 [!UICONTROL Data Source] {#create-data-source}

要创建新节， [!UICONTROL data source]请转到并 **[!UICONTROL Audience Data > Data Sources > Add New]** 完成此处介绍的每个节的步骤。 需要管理员权限才能创建 [!UICONTROL data source]。

<!-- create-datasource.xml -->

>[!TIP]
>
>有关 [这些不同控件的说明](../features/datasources-list-and-settings.md#settings-menu-options) ，请参阅数据源设置和菜单选项。

## [!UICONTROL Data Source] 详细信息 {#details}

要完成该部 [!UICONTROL Data Source Details] 分：

1. 命名 [!UICONTROL data source]。
1. *(可选* )描述 [!UICONTROL data source]。 简洁的描述可帮助您定义角色或目的 [!UICONTROL data source]。
1. 提供 [!UICONTROL integration code]。 通常为 [!UICONTROL integration codes] 可选。 您需要满足以下条件时，才需满足这些条件：

   * [创建跨设备数据源](../features/profile-merge-rules/merge-rules-start.md#create-data-source)。
   * Use the [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html).
   * 使用 [用户档案合并规则](../features/profile-merge-rules/merge-rules-start.md)。

1. 选择 **[!UICONTROL ID Type]**。 [!UICONTROL ID Type] 选项包括：

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (创建时需要 [!UICONTROL Profile Merge Rule])。 请注意，对于某些客户，此选项会显示 **[!UICONTROL ID Definition]** 选项。

1. Choose an **[!UICONTROL ID Definition]** option. 选项包括：

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[数据导出控件](../features/data-export-controls.md) 是可应用于和的可选分类 [!UICONTROL data source] 规则 [!UICONTROL destination]。 它们可防止您在数据隐私或使 [!UICONTROL destination] 用协议违反时向其发送数据。 如果不使用，请跳过此部 [!UICONTROL Data Export Controls]分。

## [!UICONTROL Data Source] 设置 {#settings}

这些设置决定了 [!UICONTROL data source] 如何识别、使用和共享。 您还可以为入站数据文件启用错误报告。 要完成该部 [!UICONTROL Data Source Settings] 分：

1. 选中一 [!UICONTROL Data Source Setting] 个复选框，将选项应用到 [!UICONTROL data source]您。
2. 单击 **[!UICONTROL Save]**.

## 删除数据源 {#delete-data-source}

<!-- t_datasource_delete.xml -->

删除 [!UICONTROL data source] 您不再需要的。

>[!NOTE]
>
>请注意以下限制：
>
>* 无法删除活 [动受众或数据源已同步特征](../features/traits/client-activity-synced-audience-traits.md)。
>* 对于使用AdobeAnalytics的客户： Audience Manager不允许您删除从报表包自动创建的 [!DNL Analytics] 数据源。 使用核 [心服务](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) ，取消映射这些数据源。


1. 单击 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. 选中一个或多个数据源旁边的复选框。
如果列表 [!UICONTROL Search] 较长，可使用该框定位所需的数据源。
1. 单击 ![](assets/icon_trash.png)，然后确认删除。


>[!MORELIKETHIS]
>
>* [数据源设置和菜单选项](../features/datasources-list-and-settings.md#settings-menu-options)