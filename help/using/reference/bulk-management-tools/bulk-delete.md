---
description: 通过批量删除，您可以通过一次操作删除多个区段、特征、文件夹、派生的信号和目标。按照这些说明进行批量删除请求。
seo-description: 通过批量删除，您可以通过一次操作删除多个区段、特征、文件夹、派生的信号和目标。按照这些说明进行批量删除请求。
seo-title: 批量删除
solution: Audience Manager
title: 批量删除
uuid: 679cde46-09fb-45c6-b84 d-47e00 e00 e0 a0 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Delete{#bulk-delete}

通过批量删除，您可以通过一次操作删除多个区段、特征、文件夹、派生的信号和目标。按照这些说明进行批量删除请求。

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具仅为方便起见而提供，并且仅作为好意提供。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI中](../../features/administration/administration-overview.md) 分配的CLUAC组权限在 [!DNL Audience Manager] 此中受支持 [!UICONTROL Bulk Management Tools]。

>[!NOTE]
>
>如果您的区段映射到目标，则目标映射的批量删除将失败。在尝试批量删除目标之前，从用户界面中删除该目标。此外，特征和区段文件夹必须为空，才能删除它们。

To delete multiple items, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
2. Click the **[!UICONTROL Delete]** tab.
3. 将删除标题粘贴到更新工作表的第一行。
4. 在标题下的列中粘贴或键入要删除的对象的ID。
5. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. [!UICONTROL Results] 列将返回一条消息，指示项目是否已被删除或错误消息。
在输入数据之前，批量更新工作表应当类似于以下内容：

![](assets/delete.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
