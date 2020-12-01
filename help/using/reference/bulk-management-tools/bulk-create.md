---
description: 通过批量创建，您可以通过单个操作构建多个数据源、派生信号、段、特征和其他项。 按照以下说明进行批量创建请求。
seo-description: 通过批量创建，您可以通过单个操作构建多个数据源、派生信号、段、特征和其他项。 按照以下说明进行批量创建请求。
seo-title: 批量创建
solution: Audience Manager
title: 批量创建
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 2%

---


# 批量创建{#bulk-create}

通过批量创建，您可以通过单个操作构建多个数据源、派生信号、段、特征和其他项。 按照以下说明进行批量创建请求。

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[在UI](../../features/administration/administration-overview.md) 中分配的RBAC [!DNL Audience Manager] 组权限在中得到保 [!UICONTROL Bulk Management Tools]留。

>[!CAUTION]
>
>请勿在批量创建请求中混合对象类型。 每个对象的标头是唯一的，不能合并。 清除工作表，并对不同物料单独提出请求。

要批量创建对象，请打开[!UICONTROL Bulk Management Tools]工作表并：

1. 单击&#x200B;**[!UICONTROL Headers]**&#x200B;选项卡，并复制要添加的项目的创建标题。
2. 单击&#x200B;**[!UICONTROL Create]**&#x200B;选项卡。
3. 将创建的标题粘贴到更新工作表的第一行中。
4. 根据标题标签，粘贴或键入要更改的数据到相应的列。
5. 在工作表工具栏中，单击与要更新的项目匹配的创建按钮。
此操作打开[!UICONTROL Account Information]对话框。
6. 提供所需的[登录信息](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)并单击&#x200B;**[!UICONTROL Submit]**。

工作表会创建[!UICONTROL Results]列。 [!UICONTROL Results]列返回JSON响应，以获得成功的操作。 有关示例，请参见[REST API](../../api/rest-api-main/rest-api-main.md)。 在输入数据之前，批量创建工作表的外观应类似于以下示例。 注意，此处不显示所有不同的创建选项。 它包含在内，可帮助您了解完成的工作表的外观。

![](assets/cretetraits.png)

如果批量更新返回错误或失败，请参阅[批量管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
