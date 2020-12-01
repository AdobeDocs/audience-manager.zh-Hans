---
description: 要创建新数据源，请转到受众数据>数据源>添加新，然后完成此处描述的每个部分的步骤。 创建数据源需要管理员权限。
keywords: data sources;manage data source;audience manager data source
seo-description: 要创建新数据源，请转到受众数据>数据源>添加新，然后完成此处描述的每个部分的步骤。 创建数据源需要管理员权限。
seo-title: 创建数据源
solution: Audience Manager
title: 管理数据源
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 5%

---


# 跨渠道和解决方案一致地管理 [!UICONTROL Data Sources] {#manage-data-sources}

## 创建一个 [!UICONTROL Data Source] {#create-data-source}

要创建新的[!UICONTROL data source]，请转到&#x200B;**[!UICONTROL Audience Data > Data Sources > Add New]**&#x200B;并完成此处描述的每个部分的步骤。 创建[!UICONTROL data source]需要管理员权限。

<!-- create-datasource.xml -->

>[!TIP]
>
>有关这些不同控件的说明，请参见[数据源设置和菜单选项](../features/datasources-list-and-settings.md#settings-menu-options)。

## [!UICONTROL Data Source] 详细信息 {#details}

完成[!UICONTROL Data Source Details]部分：

1. 命名[!UICONTROL data source]。
1. *（可选）* 描述 [!UICONTROL data source]。简洁的描述可帮助您定义[!UICONTROL data source]的角色或用途。
1. 提供[!UICONTROL integration code]。 通常，[!UICONTROL integration codes]是可选的。 您需要满足以下条件时，才需满足这些条件：

   * [创建跨设备数据源](../features/profile-merge-rules/merge-rules-start.md#create-data-source)。
   * 使用[Adobe Experience Platform身份服务](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)。
   * 使用[用户档案合并规则](../features/profile-merge-rules/merge-rules-start.md)。

1. 选择&#x200B;**[!UICONTROL ID Type]**。 [!UICONTROL ID Type] 选项包括：

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (创建时需要 [!UICONTROL Profile Merge Rule])。注意，对于某些客户，此选项会显示&#x200B;**[!UICONTROL ID Definition]**&#x200B;选项。

1. 选择&#x200B;**[!UICONTROL ID Definition]**&#x200B;选项。 选项包括：

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[数据导](../features/data-export-controls.md) 出控件是可应用于和的可选分 [!UICONTROL data source] 类规则 [!UICONTROL destination]。它们可防止您在[!UICONTROL destination]操作违反数据隐私或使用协议时向其发送数据。 如果不使用[!UICONTROL Data Export Controls]，请跳过此部分。

## [!UICONTROL Data Source] 设置 {#settings}

这些设置决定如何识别、使用和共享[!UICONTROL data source]。 您还可以为入站数据文件启用错误报告。 完成[!UICONTROL Data Source Settings]部分：

1. 选中[!UICONTROL Data Source Setting]复选框，将选项应用于[!UICONTROL data source]。
2. 单击 **[!UICONTROL Save]**.

## 删除数据源{#delete-data-source}

<!-- t_datasource_delete.xml -->

删除不再需要的[!UICONTROL data source]。

>[!NOTE]
>
>请注意以下限制：
>
>* 无法删除[活动受众或数据源同步特征](../features/traits/client-activity-synced-audience-traits.md)。
>* 对于使用Adobe Analytics的客户：Audience Manager不允许您删除从[!DNL Analytics]报表包自动创建的数据源。 使用[核心服务](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html)取消映射这些数据源。


1. 单击 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. 选中一个或多个数据源旁边的复选框。
如果列表较长，可使用[!UICONTROL Search]框查找所需的数据源。
1. 单击![](assets/icon_trash.png)，然后确认删除。


>[!MORELIKETHIS]
>
>* [数据源设置和菜单选项](../features/datasources-list-and-settings.md#settings-menu-options)