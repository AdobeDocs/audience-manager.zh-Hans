---
description: 批量更新可让您在一个操作中编辑多个区段、特征、区段或特征文件夹元素。按照这些说明进行批量更新。
keywords: Baaam
seo-description: 批量更新可让您在一个操作中编辑多个区段、特征、区段或特征文件夹元素。按照这些说明进行批量更新。
seo-title: 批量更新
solution: Audience Manager
title: 批量更新
uuid: 22f1badd-a274-4d3 e-9957-a24 bf8 c1 d0 dc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Updates{#bulk-updates}

批量更新可让您在一个操作中编辑多个区段、特征、区段或特征文件夹元素。按照这些说明进行批量更新。

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具仅为方便起见而提供，并且仅作为好意提供。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI中](../../features/administration/administration-overview.md) 分配的CLUAC组权限在 [!DNL Audience Manager] 此中受支持 [!UICONTROL Bulk Management Tools]。

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the update headers for the item you want to edit.
1. Click the **[!UICONTROL Update]** tab.
1. 将更新标题粘贴到更新工作表的第一行。请注意以下事项：

   * 更新文件夹时，所有标题都是必需的。
   * 更新区段或特征时，您只需要区段ID(SID)和需要更改的标题元素。删除未使用的标题。

1. 根据标题标签，粘贴或键入要更改为相应列的数据。
1. 在工作表工具栏中，单击与要更新的项目匹配的更新按钮。
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. [!UICONTROL Results] 列返回JSON响应以获得成功操作。See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. 在输入数据之前，批量更新工作表应当类似于以下内容：

![](assets/update.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
