---
description: 通过批量创建，您可以通过一次操作构建多个数据源、派生的信号、细分、特征和其他项目。按照这些说明进行批量创建请求。
seo-description: 通过批量创建，您可以通过一次操作构建多个数据源、派生的信号、细分、特征和其他项目。按照这些说明进行批量创建请求。
seo-title: 批量创建
solution: Audience Manager
title: 批量创建
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Create{#bulk-create}

通过批量创建，您可以通过一次操作构建多个数据源、派生的信号、细分、特征和其他项目。按照这些说明进行批量创建请求。

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具仅为方便起见而提供，并且仅作为好意提供。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI中](../../features/administration/administration-overview.md) 分配的CLUAC组权限在 [!DNL Audience Manager] 此中受支持 [!UICONTROL Bulk Management Tools]。

>[!CAUTION]
>
>请勿在批量创建请求中混合对象类型。每个对象的标题是唯一的，不能合并。清除工作表，并单独请求不同项目。

To create objects in bulk, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
1. Click the **[!UICONTROL Create]** tab.
1. 将创建标题粘贴到更新工作表的第一行。
1. 根据标题标签，粘贴或键入要更改为相应列的数据。
1. 在工作表工具栏中，单击与要更新的项目匹配的创建按钮。
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

The worksheet creates a [!UICONTROL Results] column. [!UICONTROL Results] 列返回JSON响应以获得成功操作。See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. 在输入数据之前，批量创建工作表应类似于以下示例。注意，此处不显示所有不同的创建选项。其中包括帮助您了解已完成的工作表的外观。

![](assets/cretetraits.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
