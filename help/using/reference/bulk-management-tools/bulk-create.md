---
description: 通过批量创建，您可以通过单个操作构建多个数据源、派生信号、段、特征和其他项目。 按照以下说明进行批量创建请求。
seo-description: 通过批量创建，您可以通过单个操作构建多个数据源、派生信号、段、特征和其他项目。 按照以下说明进行批量创建请求。
seo-title: 批量创建
solution: Audience Manager
title: 批量创建
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
translation-type: tm+mt
source-git-commit: 3051ca9f7c4039dafdfa01b89226c1fa8717e610

---


# 批量创建{#bulk-create}

通过批量创建，您可以通过单个操作构建多个数据源、派生信号、段、特征和其他项目。 按照以下说明进行批量创建请求。

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[在UI中分配的](../../features/administration/administration-overview.md) RBAC组权限 [!DNL Audience Manager] 在UI中被接受 [!UICONTROL Bulk Management Tools]。

>[!CAUTION]
>
>请勿在批量创建请求中混合对象类型。 每个对象的标题是唯一的，无法组合。 清除工作表，并对不同项目单独提出请求。

要批量创建对象，请打开工作 [!UICONTROL Bulk Management Tools] 表并：

1. 单击选 **[!UICONTROL Headers]** 项卡，然后复制要添加的项目的创建标题。
2. Click the **[!UICONTROL Create]** tab.
3. 将创建的标题粘贴到更新工作表的第一行中。
4. 根据标题标签，粘贴或键入要更改的数据到相应的列。
5. 在工作表工具栏中，单击与要更新的项目匹配的创建按钮。
此操作将打开对 [!UICONTROL Account Information] 话框。
6. 提供所需的 [登录信息](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ，然后单击 **[!UICONTROL Submit]**。

工作表会创建一 [!UICONTROL Results] 列。 该 [!UICONTROL Results] 列返回成功操作的JSON响应。 有关示 [例，请参阅](../../api/rest-api-main/rest-api-main.md) REST API。 在输入数据之前，批量创建工作表的外观应类似于以下示例。 注意，此处不显示所有不同的创建选项。 其中包括该组件，以帮助您了解完成的工作表的外观。

![](assets/cretetraits.png)

如果批量更新返回错误或失败，请参阅批量 [管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
