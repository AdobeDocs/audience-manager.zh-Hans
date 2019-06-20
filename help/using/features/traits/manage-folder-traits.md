---
description: 创建、编辑和删除文件夹特征。
keywords: 文件夹特征；文件夹特征；文件夹特征；文件夹特征
seo-description: 创建、编辑和删除文件夹特征。
seo-title: 管理文件夹特征
solution: Audience Manager
title: 管理文件夹特征
uuid: 287ac280-bd58-4985-85bd-b6501 eb64 b7 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Folder Traits {#manage-folder-traits}

创建、编辑和删除文件夹特征。

## Create a Folder Trait {#create-folder-trait}

A [!UICONTROL folder trait] is created automatically when you create a new folder in your taxonomy.

<!-- create-folder-trait.xml -->

1. Go to **[!UICONTROL Audience Data > Traits]** to navigate to the **Traits** dashboard.
1. [!UICONTROL Trait Storage] 在窗口中，将鼠标悬停在以下位置：

   * “所有特征”文本添加新的根级别文件夹。
   * 现有父文件夹，用于添加新的下级文件夹。
   ![](assets/folder_traits_create.PNG)

1. 单击“+”图标可创建此文件夹。请注意，在分类中最多可创建 2,000 个文件夹。请参阅[使用限制](../../features/administration/usage-limits.md)文档，以了解更多信息。
1. Name the folder and click **Save**. 例如，名为Electronics的文件夹将有一个名为“Electronics Folder Travical”的文件夹特征。您可以查看并在特征仪表板中选择新文件夹特征。
1. The new folder trait is automatically assigned to the [!DNL Audience Manager] generated data source. Your users with appropriate [!UICONTROL Role-Based Access Control ([!DNL RBAC])] permissions can change the data source in the edit folder trait workflow. See [Edit a Folder Trait](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Edit a Folder Trait {#edit-folder-trait}

Describes how you can edit a [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the **[!UICONTROL Actions]** column for the folder trait you want to edit.
1. 单击铅笔以编辑特征。

   ![](assets/folder_traits_edit_border.png)

1. **[!UICONTROL Edit]** 该工作流允许您更改文件夹特征的数据源。Select your desired data source and click **[!UICONTROL Save]**. Data sources are sorted numerically, by [!DNL DPID], in the drop-down box.

   If your company uses [!UICONTROL Role-Based Access Rights (RBAC)], you or your users need [access permissions](../../features/traits/about-folder-traits.md#role-based-access-controls) to traits data sources.

>[!NOTE]
>
>您不能直接重命名文件夹特征。[重命名其关联的存储文件夹](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) ，以更改文件夹特征的名称。

## Delete a Folder Trait {#delete-folder-trait}

删除特征所属的存储文件夹，删除文件夹特征。

<!-- delete-folder-trait.xml -->

1. **受众数据&gt;特征** 导航到 **特征** 仪表板。
1. [!UICONTROL Trait Storage] 在窗口中，通过将文件夹悬停在它上方并单击X图标来删除文件夹。

   ![步骤结果](assets/folder_traits_create.PNG)

>[!NOTE]
>
>如果在区段表达式中使用了文件夹特征，则无法删除文件夹特征。Navigate to the [trait view](../../features/traits/trait-details-page.md) section to see which segments use the folder trait. Then, click on the segment name to open the [segment summary view](../../features/segments/segment-summary-view.md), which allows you to remove traits from segment expressions.