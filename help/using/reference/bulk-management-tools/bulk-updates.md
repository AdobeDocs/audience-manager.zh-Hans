---
description: 批量更新允许您在一次操作中编辑多个区段、特征、模型、数据源以及区段或特征文件夹元素。 按照这些说明进行批量更新。
keywords: baaam
seo-description: A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: 批量更新
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# 批量更新{#bulk-updates}

批量更新允许您在一次操作中编辑多个区段、特征、模型、数据源以及区段或特征文件夹元素。 按照这些说明进行批量更新。

>[!IMPORTANT]
>
>批量管理工具不是官方支持的Adobe产品。 通过客户关怀团队提供的故障排除和支持将按具体情况处理。

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[RBAC组权限](../../features/administration/administration-overview.md) 分配于 [!DNL Audience Manager] UI在 [!UICONTROL Bulk Management Tools].

要进行批量更新，请打开 [!UICONTROL Bulk Management Tools] 工作表和：

1. 单击 **[!UICONTROL Headers]** 制表符，并复制要编辑的项目的更新标题。
2. 单击 **[!UICONTROL Update]** 选项卡。
3. 将更新标题粘贴到更新工作表的第一行。 请注意以下事项：

   * 更新文件夹时，需要所有标头。
   * 更新区段或特征时，您只需要区段ID (SID)和需要更改的标题元素。 删除未使用的标头。

4. 根据标题标签，将要更改的数据粘贴或键入到相应的列中。
5. 在工作表工具栏中，单击与要更新的项目匹配的更新按钮。
此操作将打开 [!UICONTROL Account Information] 对话框。

6. 提供所需的 [登录信息](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 并单击 **[!UICONTROL Submit]**.

   工作表将创建 [!UICONTROL Results] 列。 此 [!UICONTROL Results] 列返回成功操作的JSON响应。 请参阅 [REST API](../../api/rest-api-main/rest-api-main.md) 例如。 在输入数据之前，批量更新工作表应当类似于以下内容：

![](assets/update.png)

如果批量更新返回错误或失败，请参阅 [批量管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md).
