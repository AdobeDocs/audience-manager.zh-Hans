---
description: 批量删除允许您通过单个操作删除多个区段、特征、文件夹、派生信号、数据源、模型和目标。 请按照以下说明进行批量删除请求。
seo-description: 批量删除允许您通过单个操作删除多个区段、特征、文件夹、派生信号、数据源、模型和目标。 请按照以下说明进行批量删除请求。
seo-title: 批量删除
solution: Audience Manager
title: 批量删除
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# 批量删除{#bulk-delete}

批量删除允许您通过单个操作删除多个区段、特征、文件夹、派生信号、数据源、模型和目标。 请按照以下说明进行批量删除请求。

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[在UI中分配的](../../features/administration/administration-overview.md) RBAC组权限 [!DNL Audience Manager] 在UI中被接受 [!UICONTROL Bulk Management Tools]。

>[!NOTE]
>
>如果将区段映射到目标，则目标映射的批量删除将失败。 在尝试批量删除目标之前，在用户界面中从该目标中删除您的区段。 此外，特征和区段文件夹必须为空，然后才能删除它们。

要删除多个项目，请打开工 [!UICONTROL Bulk Management Tools] 作表并：

1. 单击选 **[!UICONTROL Headers]** 项卡，然后复制要添加的项目的创建标题。
2. Click the **[!UICONTROL Delete]** tab.
3. 将删除标题粘贴到更新工作表的第一行中。
4. 在标题下的列中粘贴或键入要删除的对象的ID。
5. 提供所需的 [登录信息](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ，然后单击 **[!UICONTROL Submit]**。

   工作表会创建一 [!UICONTROL Results] 列。 该 [!UICONTROL Results] 列返回一条消息，指示项目是否已删除或是错误消息。
在输入数据之前，批量更新工作表的外观应类似于以下内容：

![](assets/delete.png)

如果批量更新返回错误或失败，请参阅批量 [管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
