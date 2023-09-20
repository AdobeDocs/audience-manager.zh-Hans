---
description: 批量删除功能允许您通过一次操作删除多个区段、特征、文件夹、派生的信号、数据源、模型和目标。 按照以下说明发出批量删除请求。
seo-description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, data sources, models, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-title: Bulk Delete
solution: Audience Manager
title: 批量删除
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---

# 批量删除{#bulk-delete}

批量删除功能允许您通过一次操作删除多个区段、特征、文件夹、派生的信号、数据源、模型和目标。 按照以下说明发出批量删除请求。

>[!IMPORTANT]
>
>批量管理工具不是官方支持的Adobe产品。 通过客户关怀团队提供的故障排除和支持将按具体情况处理。

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[RBAC组权限](../../features/administration/administration-overview.md) 分配于 [!DNL Audience Manager] UI在 [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>如果将区段映射到目标，则批量删除目标映射将会失败。 在尝试批量删除目标之前，请在用户界面中从该目标删除您的区段。 此外，特征和区段文件夹必须为空，您才能将其删除。

要删除多个项目，请打开 [!UICONTROL Bulk Management Tools] 工作表和：

1. 单击 **[!UICONTROL Headers]** 制表符并复制要添加的项目的“创建标题”。
2. 单击 **[!UICONTROL Delete]** 选项卡。
3. 将删除标题粘贴到更新工作表的第一行。
4. 在标题下方的列中粘贴或键入要删除的对象的ID。
5. 提供所需的 [登录信息](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 并单击 **[!UICONTROL Submit]**.

   工作表将创建 [!UICONTROL Results] 列。 此 [!UICONTROL Results] 列返回一条消息，指示该项是否已被删除，或返回一条错误消息。
在输入数据之前，批量更新工作表应当类似于以下内容：

![](assets/delete.png)

如果批量更新返回错误或失败，请参阅 [批量管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md).
