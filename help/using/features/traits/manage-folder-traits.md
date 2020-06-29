---
description: 创建、编辑和删除文件夹特征。
keywords: Folder Trait;Folder Traits;folder traits;folder trait
seo-description: 创建、编辑和删除文件夹特征。
seo-title: 管理文件夹特征
solution: Audience Manager
title: 管理文件夹特征
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 9%

---


# 管理文件夹特征 {#manage-folder-traits}

创建、编辑和删除文件夹特征。

## 创建文件夹特征 {#create-folder-trait}

在分 [!UICONTROL folder trait] 类中创建新文件夹时，会自动创建一个文件夹。

<!-- create-folder-trait.xml -->

1. 转至 **[!UICONTROL Audience Data > Traits]** 导航至特 **征** 仪表板。
1. 在窗口 [!UICONTROL Trait Storage] 中，将鼠标悬停在：

   * 添加新根级别文件夹的“所有特征”文本。
   * 要添加新从属文件夹的现有父文件夹。
   ![](assets/folder_traits_create.PNG)

1. 单击“+”图标可创建此文件夹。请注意，在分类中最多可创建 2,000 个文件夹。请参阅[使用限制](../../features/administration/usage-limits.md)文档，以了解更多信息。
1. 命名文件夹，然后单击“ **保存**”。 例如，名为Electronics的文件夹将具有名为“Electronics文件夹特征”的文件夹特征。 您可以视图和选择特征仪表板中的新文件夹特征。
1. 新文件夹特征会自动分配给生 [!DNL Audience Manager] 成的数据源。 具有相应[!UICONTROL基于角色的访问控制()]权[!DNL RBAC]限的用户可以更改编辑文件夹特征工作流中的数据源。 请参 [阅编辑文件夹特征](../../features/traits/manage-folder-traits.md#edit-folder-trait)。

## 编辑文件夹特征 {#edit-folder-trait}

介绍如何编辑 [!UICONTROL folder trait]。

<!-- edit-folder-trait.xml -->

1. 在仪表板 [!UICONTROL Traits] 中，将指针悬 **[!UICONTROL Actions]** 停在要编辑的文件夹特征的列上。
1. 单击铅笔以编辑特征。

   ![](assets/folder_traits_edit_border.png)

1. 该工 **[!UICONTROL Edit]** 作流允许您更改文件夹特征的数据源。 选择所需的数据源并单击 **[!UICONTROL Save]**。 数据源在下拉框 [!DNL DPID]中按数字排序。

   如果公司使 [!UICONTROL Role-Based Access Rights (RBAC)]用特征数据源，您或您 [的用户需](../../features/traits/about-folder-traits.md#role-based-access-controls) 要访问权限。

>[!NOTE]
>
>不能直接重命名文件夹特征。 [重命名其关联的存储文](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) 件夹，以更改文件夹特征的名称。

## 删除文件夹特征 {#delete-folder-trait}

通过删除特征所属的存储文件夹，删除文件夹特征。

<!-- delete-folder-trait.xml -->

1. **受众数据>特征** ，以导航到 **特征** 仪表板。
1. 在窗口 [!UICONTROL Trait Storage] 中，将指针悬停在文件夹上并单击X图标，即可删除该文件夹。

   ![步骤结果](assets/folder_traits_create.PNG)

>[!NOTE]
>
>如果在段表达式中使用文件夹特征，则无法删除该特征。 导航到特 [征视图](../../features/traits/trait-details-page.md) 部分，查看哪些区段使用文件夹特征。 然后，单击区段名称以打开区段 [摘要视图](../../features/segments/segment-summary-view.md)，以便从区段表达式中删除特征。