---
description: 批量创建允许您通过一次操作构建多个数据源、派生的信号、区段、特征和其他项目。 按照以下说明发出批量创建请求。
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: 批量创建
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# 批量创建{#bulk-create}

批量创建允许您通过一次操作构建多个数据源、派生的信号、区段、特征和其他项目。 按照以下说明发出批量创建请求。

>[!IMPORTANT]
>
>批量管理工具不是官方支持的Adobe产品。 通过客户关怀团队提供的故障排除和支持将按具体情况处理。

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[接受在](../../features/administration/administration-overview.md) UI中分配的[!DNL Audience Manager]RBAC组权限[!UICONTROL Bulk Management Tools]。

>[!CAUTION]
>
>请勿在批量创建请求中混合使用对象类型。 每个对象的标题都是唯一的，无法合并。 清除工作表，然后为不同的物料提出单独的请求。

若要批量创建对象，请打开[!UICONTROL Bulk Management Tools]工作表并：

1. 单击&#x200B;**[!UICONTROL Headers]**&#x200B;选项卡，并复制要添加项目的创建标头。
2. 单击&#x200B;**[!UICONTROL Create]**&#x200B;选项卡。
3. 将create headers粘贴到更新工作表的第一行。
4. 根据标题标签，将要更改的数据粘贴或键入到相应的列中。
5. 在工作表工具栏中，单击与您正在更新的项目相匹配的“创建”按钮。
此操作打开[!UICONTROL Account Information]对话框。
6. 提供所需的[登录信息](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)，然后单击&#x200B;**[!UICONTROL Submit]**。

工作表创建一个[!UICONTROL Results]列。 [!UICONTROL Results]列返回成功操作的JSON响应。 有关示例，请参阅[REST API](../../api/rest-api-main/rest-api-main.md)。 在输入数据之前，批量创建工作表应当类似于以下示例。 注意，此处不显示所有不同的创建选项。 包括此内容是为了帮助您了解填写的工作表是什么样的。

![](assets/cretetraits.png)

如果批量更新返回错误或失败，请参阅[批量管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
