---
description: 要创建新数据源，请转到受众数据>数据源>新增，并完成此处介绍的每个部分的步骤。 创建数据源需要管理员权限。
keywords: 数据源；管理数据源；audience manager数据源
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: 管理数据源
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 6ec76227dd8c7581550c3d95e24fc5b6a4b01093
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 2%

---

# 跨渠道和解决方案一致地管理 [!UICONTROL Data Sources] {#manage-data-sources}

## 创建一个 [!UICONTROL Data Source] {#create-data-source}

创建新 [!UICONTROL data source]，转到 **[!UICONTROL Audience Data > Data Sources > Add New]** 并完成此处介绍的每个部分的步骤。 需要管理员权限才能创建 [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>请参阅 [数据源设置和菜单选项](../features/datasources-list-and-settings.md#settings-menu-options) 以了解这些不同控件的描述。

## [!UICONTROL Data Source] 详细信息 {#details}

完成 [!UICONTROL Data Source Details] 部分：

1. 将 [!UICONTROL data source].
1. *（可选）* 描述 [!UICONTROL data source]. 简要描述可帮助您定义 [!UICONTROL data source].
1. 提供 [!UICONTROL integration code]. 通常， [!UICONTROL integration codes] 为可选项。 当您想要执行以下操作时，需要使用这些参数：

   * [创建跨设备数据源](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * 使用 [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * 使用 [配置文件合并规则](../features/profile-merge-rules/merge-rules-start.md).

1. 选择 **[!UICONTROL ID Type]**. [!UICONTROL ID Type] 选项包括：

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (创建 [!UICONTROL Profile Merge Rule])。 请注意，对于某些客户，此选择会公开 **[!UICONTROL ID Definition]** 选项。

   >[!NOTE]
   >
   >对于已配置为Audience Manager和Experience Platform的每个组织，即使您没有在两个应用程序之间设置区段共享，在创建跨设备数据源时，也会对应 [标识命名空间](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) 在Experience Platform中创建。

1. 选择 **[!UICONTROL ID Definition]** 选项。 选项包括：

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[数据导出控制](../features/data-export-controls.md) 是可选的分类规则，您可以将其应用到 [!UICONTROL data source] 和 [!UICONTROL destination]. 它们会阻止您将数据发送到 [!UICONTROL destination] 操作违反数据隐私或使用协议时。 如果您不使用 [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] 设置 {#settings}

这些设置决定了 [!UICONTROL data source] 被标识、使用和共享。 您还可以为入站数据文件启用错误报告。 完成 [!UICONTROL Data Source Settings] 部分：

1. 选择 [!UICONTROL Data Source Setting] 复选框，以将选项应用于 [!UICONTROL data source].
2. 单击 **[!UICONTROL Save]**.

## 删除数据源 {#delete-data-source}

<!-- t_datasource_delete.xml -->

删除 [!UICONTROL data source] 你不再需要的。

>[!NOTE]
>
>请注意以下限制：
>
>* 您无法删除 [活动受众或数据源同步特征](../features/traits/client-activity-synced-audience-traits.md).
>* 对于使用Adobe Analytics的客户：Audience Manager不允许您删除从 [!DNL Analytics] 报表包。 使用 [核心服务](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) 来取消映射这些数据源。


1. 单击 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. 选中一个或多个数据源旁边的复选框。
您可以使用 [!UICONTROL Search] 框中，可找到所需的数据源。
1. 单击  ![](assets/icon_trash.png)，然后确认删除。


>[!MORELIKETHIS]
>
>* [数据源设置和菜单选项](../features/datasources-list-and-settings.md#settings-menu-options)

