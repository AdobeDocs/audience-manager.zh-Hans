---
description: 通过批量更新，您可以在单次操作中编辑多个区段、特征、模型、数据源，以及区段或特征文件夹元素。 按照这些说明进行批量更新。
keywords: baam
seo-description: 通过批量更新，您可以在单次操作中编辑多个区段、特征、模型、数据源，以及区段或特征文件夹元素。 按照这些说明进行批量更新。
seo-title: 批量更新
solution: Audience Manager
title: 批量更新
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 2%

---

# 批量更新{#bulk-updates}

通过批量更新，您可以在单次操作中编辑多个区段、特征、模型、数据源，以及区段或特征文件夹元素。 按照这些说明进行批量更新。

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[在UI中](../../features/administration/administration-overview.md) 分配的RBAC组 [!DNL Audience Manager] 权限将在中得 [!UICONTROL Bulk Management Tools]到。

要进行批量更新，请打开[!UICONTROL Bulk Management Tools]工作表，然后：

1. 单击&#x200B;**[!UICONTROL Headers]**&#x200B;选项卡，并复制要编辑的项目的更新标题。
2. 单击&#x200B;**[!UICONTROL Update]**&#x200B;选项卡。
3. 将更新标题粘贴到更新工作表的第一行中。 请注意以下事项：

   * 更新文件夹时，需要使用所有标头。
   * 在更新区段或特征时，您只需要区段ID(SID)和需要更改的标头元素。 删除未使用的标头。

4. 根据标题标签，将要更改的数据粘贴或键入到相应的列中。
5. 在工作表工具栏中，单击与        要更新的项目。
此操作将打开[!UICONTROL Account Information]对话框。

6. 提供所需的[登录信息](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)并单击&#x200B;**[!UICONTROL Submit]**。

   工作表会创建一个[!UICONTROL Results]列。 [!UICONTROL Results]列会返回成功操作的JSON响应。 有关示例，请参阅[REST API](../../api/rest-api-main/rest-api-main.md)。 在输入数据之前，批量更新工作表应类似于以下内容：

![](assets/update.png)

如果批量更新返回错误或失败，请参阅[批量管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
