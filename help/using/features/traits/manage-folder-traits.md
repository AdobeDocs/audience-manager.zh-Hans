---
description: 创建、编辑和删除文件夹特征。
keywords: 文件夹特征；文件夹特征；文件夹特征；文件夹特征
seo-description: Create, edit, and delete folder traits.
seo-title: Manage Folder Traits
solution: Audience Manager
title: 管理文件夹特征
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
exl-id: fa7a8d2a-dacc-413e-89d6-d3b7ce7bbbe3
source-git-commit: f7a4478589f4af1d467f1045a97dbb7f5cd6f9e5
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 5%

---

# 管理文件夹特征 {#manage-folder-traits}

创建、编辑和删除文件夹特征。

## 创建文件夹特征 {#create-folder-trait}

A [!UICONTROL folder trait] 在分类中创建新文件夹时，将自动创建。

<!-- create-folder-trait.xml -->

1. 转到 **[!UICONTROL Audience Data > Traits]** 导航到 **特征** 功能板。
1. 在 [!UICONTROL Trait Storage] 窗口，悬停：

   * 添加新根级别文件夹的“所有特征”文本。
   * 用于添加新的下属文件夹的现有父文件夹。

   ![](assets/folder_traits_create.PNG)

1. 单击“+”图标可创建此文件夹。请注意，在分类中最多可创建2000个文件夹。 请参阅[使用限制](../../features/administration/usage-limits.md)文档，以了解更多信息。
1. 命名文件夹并单击 **保存**. 例如，名为Electronics的文件夹将具有名为“Electronics文件夹特征”的文件夹特征。 您可以在特征仪表板中查看和选择新的文件夹特征。
1. 新文件夹特征会自动分配给 [!DNL Audience Manager] 生成的数据源。 您的用户具有适当的 [!UICONTROL Role-Based Access Control] ([!DNL RBAC])权限可以在编辑文件夹特征工作流中更改数据源。 请参阅 [编辑文件夹特征](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## 编辑文件夹特征 {#edit-folder-trait}

介绍如何编辑 [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. 在 [!UICONTROL Traits] 功能板，将鼠标悬停在 **[!UICONTROL Actions]** 列。
1. 单击铅笔以编辑特征。

   ![](assets/folder_traits_edit_border.png)

1. 的 **[!UICONTROL Edit]** 工作流允许您更改文件夹特征的数据源。 选择所需的数据源并单击 **[!UICONTROL Save]**. 数据源按数字排序 [!DNL DPID]，在下拉框中。

   如果贵公司使用 [!UICONTROL Role-Based Access Rights (RBAC)]，您或您的用户需要 [访问权限](../../features/traits/about-folder-traits.md#role-based-access-controls) 来特征数据源。

>[!NOTE]
>
>无法直接重命名文件夹特征。 [重命名其关联的存储文件夹](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) 以更改文件夹特征的名称。

## 删除文件夹特征 {#delete-folder-trait}

通过删除特征所属的存储文件夹来删除文件夹特征。

<!-- delete-folder-trait.xml -->

1. **受众数据>特征** 导航到 **特征** 功能板。
1. 在 [!UICONTROL Trait Storage] ，请将鼠标悬停在文件夹上并单击X图标以将其删除。

   ![步骤结果](assets/folder_traits_create.PNG)

>[!NOTE]
>
>如果在区段表达式中使用文件夹特征，则无法删除该特征。 导航到 [特征视图](../../features/traits/trait-details-page.md) 部分以了解哪些区段使用文件夹特征。 然后，单击区段名称以打开 [区段摘要视图](../../features/segments/segment-summary-view.md)，用于从区段表达式中删除特征。
