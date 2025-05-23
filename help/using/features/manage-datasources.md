---
description: 要创建新数据源，请转到受众数据>数据源>新增，并完成此处所述每个部分的步骤。 创建数据源需要管理员权限。
keywords: 数据源；管理数据源；Audience Manager数据源
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: 管理数据源
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: bda66cb9aaee3a40ae64dda100f42b88696a027e
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---

# 管理[!UICONTROL Data Sources] {#manage-data-sources}

## 创建[!UICONTROL Data Source] {#create-data-source}

要创建新[!UICONTROL data source]，请转到&#x200B;**[!UICONTROL Audience Data > Data Sources > Add New]**&#x200B;并完成此处描述的每个部分的步骤。 创建[!UICONTROL data source]需要管理员权限。

<!-- create-datasource.xml -->

>[!TIP]
>
>有关这些不同控件的说明，请参阅[数据Source设置和菜单选项](../features/datasources-list-and-settings.md#settings-menu-options)。

## [!UICONTROL Data Source]详细信息 {#details}

要完成[!UICONTROL Data Source Details]部分，请填写以下字段：

1. **[!UICONTROL Name]**：提供数据源的名称。
1. **[!UICONTROL Description]** （可选）：输入数据源的描述，以帮助您定义数据源的角色或用途。
1. **[!UICONTROL Integration Code]** （可选）：输入集成代码。 当您想要：
   * [创建跨设备数据源](../features/profile-merge-rules/merge-rules-start.md#create-data-source)。
   * 使用[Adobe Experience Platform Identity服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)。
   * 使用[配置文件合并规则](../features/profile-merge-rules/merge-rules-start.md)。
1. **[!UICONTROL Namespace]** （只读）：此字段是只读的，在保存数据源时会自动生成。 如果要将区段从Audience Manager导出到Experience Platform，则必须在Experience Platform中创建相应的[身份命名空间](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=zh-Hans#manage-namespaces)，并将自动生成的值用作Experience Platform中的命名空间[身份符号](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/features/namespaces#components-of-a-namespace)。
1. **[!UICONTROL ID Type]**：选择此数据源将包含的ID类型：
   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** （创建[!UICONTROL Profile Merge Rule]所需）。 请注意，对于某些客户，此选择会公开&#x200B;**[!UICONTROL ID Definition]**&#x200B;选项。
1. 选择一个&#x200B;**[!UICONTROL ID Definition]**&#x200B;选项。 选项包括：

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[数据导出控件](../features/data-export-controls.md)是可选的分类规则，可应用于[!UICONTROL data source]和[!UICONTROL destination]。 当操作违反数据隐私或使用协议时，它们会阻止您向[!UICONTROL destination]发送数据。 如果您不使用[!UICONTROL Data Export Controls]，请跳过此部分。

## [!UICONTROL Data Source]设置 {#settings}

这些设置决定如何识别、使用和共享[!UICONTROL data source]。 您还可以为入站数据文件启用错误报告。 要完成[!UICONTROL Data Source Settings]部分，请执行以下操作：

1. 选中一个[!UICONTROL Data Source Setting]复选框以将选项应用于您的[!UICONTROL data source]。
2. 单击 **[!UICONTROL Save]**。

## 删除数据Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

删除您不再需要的[!UICONTROL data source]。

>[!NOTE]
>
>请注意以下限制：
>
>* 您无法删除[活动受众或Source同步的数据](../features/traits/client-activity-synced-audience-traits.md)特征。
>* 对于使用Adobe Analytics的客户：Audience Manager不允许您删除从[!DNL Analytics]报表包中自动创建的数据源。 使用[核心服务](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/services/customer-attributes/attributes)取消这些数据源的映射。

1. 单击&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**。
1. 选中一个或多个数据源旁边的复选框。
如果您有长列表，可以使用[!UICONTROL Search]框找到所需的数据源。
1. 单击![](assets/icon_trash.png)，然后确认删除。


>[!MORELIKETHIS]
>
>* [数据Source设置和菜单选项](../features/datasources-list-and-settings.md#settings-menu-options)
