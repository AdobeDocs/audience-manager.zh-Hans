---
description: 通过批量创建，您可以通过单次操作构建多个数据源、派生的信号、区段、特征和其他项目。 按照以下说明进行批量创建请求。
seo-description: 通过批量创建，您可以通过单次操作构建多个数据源、派生的信号、区段、特征和其他项目。 按照以下说明进行批量创建请求。
seo-title: 批量创建
solution: Audience Manager
title: 批量创建
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# 批量创建{#bulk-create}

通过批量创建，您可以通过单次操作构建多个数据源、派生的信号、区段、特征和其他项目。 按照以下说明进行批量创建请求。

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[在UI中](../../features/administration/administration-overview.md) 分配的RBAC组 [!DNL Audience Manager] 权限将在中得 [!UICONTROL Bulk Management Tools]到。

>[!CAUTION]
>
>请勿在批量创建请求中混合使用对象类型。 每个对象的标头是唯一的，不能合并。 清除工作表，并对不同的项目发出单独的请求。

要批量创建对象，请打开[!UICONTROL Bulk Management Tools]工作表，然后：

1. 单击&#x200B;**[!UICONTROL Headers]**&#x200B;选项卡，并复制要添加项目的创建标题。
2. 单击&#x200B;**[!UICONTROL Create]**&#x200B;选项卡。
3. 将创建标题粘贴到更新工作表的第一行中。
4. 根据标题标签，将要更改的数据粘贴或键入到相应的列中。
5. 在工作表工具栏中，单击与您要更新的项目匹配的创建按钮。
此操作将打开[!UICONTROL Account Information]对话框。
6. 提供所需的[登录信息](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)并单击&#x200B;**[!UICONTROL Submit]**。

工作表会创建一个[!UICONTROL Results]列。 [!UICONTROL Results]列会返回成功操作的JSON响应。 有关示例，请参阅[REST API](../../api/rest-api-main/rest-api-main.md)。 在输入数据之前，批量创建的工作表应类似于以下示例。 请注意，此处未显示所有不同的创建选项。 其中包含此参数，可帮助您了解已完成的工作表的外观。

![](assets/cretetraits.png)

如果批量更新返回错误或失败，请参阅[批量管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
