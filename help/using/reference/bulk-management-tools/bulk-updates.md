---
description: 通过批量更新，您可以在单个操作中编辑多个区段、特征、模型、数据源以及区段或特征文件夹元素。 按照以下说明进行批量更新。
keywords: baaam
seo-description: 通过批量更新，您可以在单个操作中编辑多个区段、特征、模型、数据源以及区段或特征文件夹元素。 按照以下说明进行批量更新。
seo-title: 批量更新
solution: Audience Manager
title: 批量更新
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# 批量更新{#bulk-updates}

通过批量更新，您可以在单个操作中编辑多个区段、特征、模型、数据源以及区段或特征文件夹元素。 按照以下说明进行批量更新。

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[在UI中分配的](../../features/administration/administration-overview.md) RBAC组权限 [!DNL Audience Manager] 在UI中被接受 [!UICONTROL Bulk Management Tools]。

要进行批量更新，请打开工作 [!UICONTROL Bulk Management Tools] 表并：

1. 单击选 **[!UICONTROL Headers]** 项卡，并复制要编辑的项目的更新标题。
2. Click the **[!UICONTROL Update]** tab.
3. 将更新标题粘贴到更新工作表的第一行中。 请注意以下事项：

   * 更新文件夹时，所有标题都是必需的。
   * 更新区段或特征时，您只需要区段ID(SID)和需要更改的标题元素。 删除未使用的标题。

4. 根据标题标签，粘贴或键入要更改的数据到相应的列。
5. 在工作表工具栏中，单击与要更新的项目匹配的更新按钮。
此操作将打开对 [!UICONTROL Account Information] 话框。

6. 提供所需的 [登录信息](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ，然后单击 **[!UICONTROL Submit]**。

   工作表会创建一 [!UICONTROL Results] 列。 该 [!UICONTROL Results] 列返回成功操作的JSON响应。 有关示 [例，请参阅](../../api/rest-api-main/rest-api-main.md) REST API。 在输入数据之前，批量更新工作表的外观应类似于以下内容：

![](assets/update.png)

如果批量更新返回错误或失败，请参阅批量 [管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
